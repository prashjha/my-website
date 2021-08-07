---
author: 'Prashant K. Jha'
date: 2021-08-06
title: 'Modular website - Separating kernel files and static files'
featured: true
draft: false
---

Recording the steps I went through to setup a separate website for class **COE 311K** within my own personal website.

## Hugo basic commands
Follow [hugo quickstart](https://gohugo.io/getting-started/quick-start/) tutorial to create the directory with basic website files. The key steps are
```sh
# create a directory named quickstart
hugo new site quickstart

# initialize git
cd quickstart
git init

# get theme
git submodule add <github theme repo> themes/<theme name>
```

The key steps in above tutorial is finding a right theme for the website. In my case, I selected [Book theme](https://hugo-book-demo.netlify.app/) which can be cloned from github from this [link](https://github.com/alex-shpak/hugo-book).

Themes are added as git submodule. For example, I added **book** theme as follows
```sh
git submodule add https://github.com/alex-shpak/hugo-book.git themes/book
```

## Use example files from the theme to start
Next step is to create a basic website. It is easier to start with the **example** website from the theme you have selected. 

In my case, I copied the relevant files in [exampleSite](https://github.com/alex-shpak/hugo-book/tree/master/exampleSite) to start the website. I considered
```sh
# clear the content directory
rm -r content

cp -a themes/book/exampleSite/content ./
```

Next, I modified the `config.toml` with only things I needed from `themes/book/exampleSite/config.toml`. My `config.toml` as of now has following:
```toml
baseURL = 'https://prashjha.github.io/'
title = 'COE 311K'
theme = 'book'

[menu]
# [[menu.after]]
[[menu.before]]
  name = "Prashant's Homepage"
  url = "https://prashjha.github.io/"
  weight = 1
```

In above, we have set up the name of website and theme. I have also added a menu to my homepage.

### Major modifications to make this website suitable for course
I then modified the files in `content/menu`, `content/docs`, and `content/posts` as per my requirement. After you figure out what do you need in the website, modifying the example files are easy. In my case, I needed menus and contents for syllabus and lectures. For this I modified the `content/docs` to create two directories; one for syllabus and other for lectures.

## Test the website
Run 
```sh
hugo server -D
```
and observe the website in realtime by opening the link [http://localhost:1313/](http://localhost:1313/). 

Once satisfies, you can create the html files for website by running
```sh
hugo -F
```
This command will create a `public` directly with all the necessary html files to render the website.

Checkout the [hugo tutorial](https://gohugo.io/getting-started/quick-start/)  for more details. 

## Keeping the html files as a submodule
In case you do not want to track the `html` files in `public` directory, you can 
1. Tell git to ignore `public` directory by creating .gitignore file and adding this line 
```sh
# Hugo
# ignore generated files
resources/
# ignore html files of the website (optional if want to track public directory separately)
public/
```

2. Create a github repository to host the `html` files. Suppose <quickstart-public-html> is the name of the github repo. In the beginning, initialize your repo as follows
```sh
cd public
git init
git add .
git commit -m "first commit"

# add github repo to this git using
git remote add origin  <REMOTE_URL> 

# push the first commit
git push origin master
```

3. Everytime `public` directory is modified, you can update the github repo as follows
```sh
git add . && git commit -m "your message" && git push origin master
```
