---
title: 'Computational methods for nonlocal models'

summary: 'Develop efficient and parallel computational methods for class of nonlocal models such as Peridynamics and nonlocal diffusion equations'

# Data
date: '2022-01-01'

# authors: ['Prashant K. Jha']
tags: ['Peridynamics', 'Nonlocal Methods', 'Multiphysics', 'Numerical Method']

# Is this a featured? (true/false)
featured: false

image:
  caption: 'NLMech library welcome page. https://github.com/nonlocalmodels/NLMech'
  focal_point: 'Smart'
---

Develop efficient and parallel computational methods for class of nonlocal models such as Peridynamics and nonlocal diffusion equations

# Activities

## 1. Google Summer of Code 2020
Towards the development of a massively parallel computational library for peridynamics and other nonlocal models, together with P. Diehl, we prepared a computational problem where the goal was to develop a massively parallel library for the simple 2D nonlocal heat equation. See the rough description of the [problem](https://github.com/nonlocalmodels/nonlocalheatequation/blob/master/description/problem_description.pdf). This project was sponsored by Google in Google Summer of Code 2020 and was assigned to student P. Gadikar (IIT Madras). Pranav's work is open source and can be found [here](https://github.com/nonlocalmodels/nonlocalheatequation). Conference paper on proposed load balancing algorithm is in this link [GSoC 2020 conference paper]( {{< relref "publication/gadikar-2021-nonlocal" >}}).

## 2. NLMech library
We have launched peridynamics code [NLMech](https://github.com/nonlocalmodels/NLMech) that utilizes [HPX](https://github.com/STEllAR-GROUP/hpx) library for efficient multi-threading computation. We aim to make the NLMech library more user-friendly and easily extensible in the coming days. Our future goals are to 

- develop a fully parallel library following some of the key ideas and algorithms from our GSoC 2020 work

- implement Quasistatic discretization

The paper with P. Diehl briefly describing the open-source library is currently under review in JOSS (Journal of Open Source Software). The review of the code and paper is open and can be seen live [here](https://github.com/openjournals/joss-reviews/issues/2898).
