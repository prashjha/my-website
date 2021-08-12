---
author: 'Prashant K. Jha'
date: 2021-08-06
title: 'Modular website - Separating kernel files and static files'
featured: true
draft: false
---



I am currently using [hugo](https://gohugo.io) to create website. I found the process to be overall simple and straightforward. The process of setting up a new website includes: 
1. selecting an appropriate theme from [hugo themes list](https://themes.gohugo.io/)
2. use the example website files that come with a theme (usually themes are hosted in the github and from the github you can grab the corresponding example website files)
3. customize the example website files as required
4. test the website by first building in your computer using `hugo server` command:
```sh
hugo server -D
```
this spins up the website in the localhost [http://localhost:1313/](http://localhost:1313/). You can open a browser and go to this localhost and view your website
5. create website html files using the hugo build command:
```sh
hugo -F
```
or explicitly specify to hugo that the website is ready for production (note: this is required if you link google analytics tag with the website)
```sh
HUGO_ENV="production"  hugo -F
```
6. finally, you need to push all the files in `public` directory to the corresponding github repository that you have created to host the website. You can also specify to hugo if you want to build the html files in directory other than `public` by adding below to the `config.toml` file:
```toml
publishDir = 'docs'
```

> This blog is also for my reference. 

> Disclaimer: some of the steps may not be efficient! 

# Separate hugo website files and generated html files
I prefer to keep the generated html files to render the website and the website files that hugo used to generate html files **separate**. There are two ways to achieve this:

## Method 1
Host the website files (files that hugo will use to create html files) in one github repo, say `WebsiteBase`, and host the html files in another repo, say `WebsiteStatic`. 

The steps are as follows:

### Step 1
We first create a `WebsiteBase` containing your example website. Since we don't want to **track** `public` directory inside `WebsiteBase`, we add the following line to `.gitignore` file:
```sh
public
```

### Step 2
Next, we go to `public` directory inside `WebsiteBase` (public directory is not tracked and public directory will be **created** when you **build** the website using `hugo -F` command). Inside `public` directory, if this is a first time, create a git repo 
```sh
# we assume that we are inside `public` directory
git init
git add . && git commit -m "first commit"
```
Next, suppose you have already created a new repository called `WebsiteStatic` in github, you can add the remote url to your public directory as follows
```sh
# inside `public` directory
git remote add origin https://github.com/<your username>/WebsiteStatic.git
```
and push the code to github
```sh
git branch -M main
git push origin main

# alternatively, if you prefer, you can keep the master as your `main` branch 
# and push master to the remote
# git push origin master
```

### Step 3
Modify the files of `WebsiteBase` as required and push the changes to `WebsiteBase` repository. Next, rebuild the website to take the modification in effect using `hugo -F` command. This will update `public` directory inside `WebsiteBase`. You then update the `WebsiteStatic` as follows:
```sh
# assuming that you are inside `WebsiteBase` repo root directory
cd public
git add . && git commit -m "update"
# we assume that `public` directory is initialized with `WebsiteStatic` repo (step 2)
git push origin main -f
```

In above we have used flag `-f` (i.e. force push) because `public` repository may not have the same files as remote repo `WebsiteStatic` (this may happen if you use to different computers to update the website). And since we do not care much about the commit history of `WebsiteStatic`, we simply force push the updates to remote repo.

### Optional - Automate the website update using circle-ci
In updating a website, the main part is updating the website files in `WebsiteBase` (for example, adding new blog, new publication, new project, etc.). After `WebsiteBase` is updated, the next step is to run hugo to rebuild the website and update the remote repo `WebsiteStatic` that hosts the html files. This second step can be automated using [circle-ci](https://circleci.com/) in the github. 

The idea is that we update the files of `WebsiteBase` and push the code to github and let circle-ci do the rest. For example, I may want to update the blog file [content/blog/modular-website/index.md](https://github.com/prashjha/my-website/blob/main/content/blog/modular-website/index.md). Suppose you have modified the files and pushed the updates to `WebsiteBase` repo in github.

Next, to trigger circle-ci to do the rest, you first need to create a circle-ci config file inside, i.e., `<WebsiteBase root>/.circleci/config.yml`, with the instruction to build the website using hugo. For example, [my circle-ci config file](https://github.com/prashjha/my-website/blob/main/.circleci/config.yml) looks like this:
```yml
version: 2
jobs:
  build:
    docker:
      - image: klakegg/hugo:0.87.0-ext-ubuntu
    steps:
      - run:
          name: "Run Hugo"
          command: |
            apt-get update
            apt-get install -y git
            # pull website repo
            git clone https://github.com/prashjha/my-website.git
            cd my-website
            # within this repo, pull html file repo
            git clone https://github.com/prashjha/prashjha.github.io.git public
            # build website
            HUGO_ENV="production"  hugo -F
            # commit to website repo
            cd public
            git config user.email "pjha.sci@gmail.com"
            git config user.name "Prashant K. Jha"
            git add .
            git commit --allow-empty -m "update" 
            # Push quietly to prevent showing the token in log
            git push -q https://${G_TOKEN}@github.com/prashjha/prashjha.github.io.git main
```
In above, I use docker image that contains hugo `klakegg/hugo:0.87.0-ext-ubuntu`. Steps in `steps -> run` should be obvious. We first clone `WebsiteBase` (which in my case is named `my-website`) and then clone the `WebsiteStatic` (which in my case is name `prashjha.github.io`) inside `public` directory. We then build the website using `hugo -F` command. This updates `public` directory. We then push the updates to `WebsiteStatic`. 

So far you have created `config.yml` that instructs circle-ci. Next, you need to go to your account in [circle-ci](https://circleci.com/). (Create account in circle ci using your github account). Inside circle-ci, you have to add the project `WebsiteBase` for continuous integration. 

> With steps above, everytime you will update `WebsiteBase`, circle-ci will use the instructions in `config.yml` and update your `WebsiteStatic` automatically. 

## Method 2 (use submodule)
Alternatively, you could store the subset of the website files in a different repository and store the rest of the website files along with the hugo generated html files in one website. 

I opted for this method for the [COE 311K course website](https://prashjha.github.io/COE-311K-website/). I have created a github repo to store the class related files such as lecture notes, assignments, projects, syllabus, etc., see [COE 311K](https://github.com/prashjha/COE-311K). And, I host the website files and the html files in this repo: [COE 311K website](https://github.com/prashjha/COE-311K-website). 

The class repo [COE 311K](https://github.com/prashjha/COE-311K) contains some of the website files needed to generate the website. For example, [syllabus page](https://prashjha.github.io/COE-311K-website/docs/syllabus/) in the website is based on the markdown file [_index.md](https://github.com/prashjha/COE-311K/blob/main/syllabus/_index.md) stored in the syllabus directory of the class repo [COE 311K](https://github.com/prashjha/COE-311K). Similarly, the lecture page of the website is based on the markdown files in the `lectures` directory of the class repo [COE 311K](https://github.com/prashjha/COE-311K). 

I am outlining the steps I used to create the class website (rough outline) with modular structure explained above:

### Step 1
Except the files which I expect to change often, rest are contained in the website repo [COE 311K website](https://github.com/prashjha/COE-311K-website). To connect this repo with the class repo [COE 311K](https://github.com/prashjha/COE-311K), we use `submodule` command. We add repo [COE 311K](https://github.com/prashjha/COE-311K) within a repo [COE 311K website](https://github.com/prashjha/COE-311K-website) as follows:
```sh
# assuming inside the root of repo `COE 311K website`
git submodule add https://github.com/prashjha/COE-311K.git
```
Next, I have created a symlink of files in syllabus, lectures, etc. of [COE 311K](https://github.com/prashjha/COE-311K) inside the `content` directory of the repo [COE 311K website](https://github.com/prashjha/COE-311K-website). 

### Step 2
Now that [COE 311K website](https://github.com/prashjha/COE-311K-website) repository has the correct submodule and the symlinks are created to connect the class repository files with the website files, we can build the website using `hugo -F`. 

In my case, since I already use `prashjha.github.io` repository to render my main website, the repository [COE 311K website](https://github.com/prashjha/COE-311K-website) can only be used to render the `github pages`. And, last time I checked, `github pages` requires the html files either in the `root` directory of the repository or the `docs` directory. Since we do not want to corrupt the root directory of repo by generating html files in the root, the alternative is to ask `hugo` to generate the html files inside the `docs` directory. This can be done by adding the line below to the `config.toml` file:
```sh
publishDir = 'docs'
```
So, when we run `hugo -F`, the html files will be generated inside the `docs` directory. 

We rebuild the website and push it to the repository. In this case, the website repository will contain all the files (including the html files). 

### Optional - Automate the website update using circle-ci
Similar to the method 1, we can automate some of the steps. More often modified files are in the class repository [COE 311K](https://github.com/prashjha/COE-311K) so when this is updated, we can use the circle-ci to update the class website repository [COE 311K website](https://github.com/prashjha/COE-311K-website). The circle-ci config file in [COE 311K](https://github.com/prashjha/COE-311K) repository looks like:
```yml

version: 2
jobs:
  build:
    docker:
      - image: klakegg/hugo:0.87.0-ext-ubuntu
    steps:
      - run:
          name: "Run Hugo"
          command: |
            apt-get update
            apt-get install -y git
            # pull website repo
            git clone https://github.com/prashjha/COE-311K-website.git
            cd COE-311K-website
            # update course repo
            git submodule update --init COE-311K
            cd COE-311K
            git checkout main
            git pull 
            # build website
            cd ..
            hugo -F
            # commit to website repo
            git config user.email "pjha.sci@gmail.com"
            git config user.name "Prashant K. Jha"
            git add .
            git commit --allow-empty -m "update" 
            # Push quietly to prevent showing the token in log
            git push -q https://${G_TOKEN}@github.com/prashjha/COE-311K-website.git main
```
The steps are more or less similar to method 1 except now that we have submodule inside the website repository and we need to update the submodule before building the code. The submodule is updated in these steps:
```sh
git submodule update --init COE-311K
cd COE-311K
git checkout main
git pull 
```
We then build the website and update the remote. 
