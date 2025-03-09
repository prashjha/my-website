---
title: 'nonlocalheatequation'

summary: 'Implementation of a distributed nonlocal heat equation solver with load balancing'

# Data
date: '2021-02-09'

# authors: ['Prashant K. Jha']
tags: ['Nonlocal Modeling', 'Distributed Computing']

# Is this a featured? (true/false)
featured: false
---

# Code information

Github link: [nonlocalheatequation](https://github.com/nonlocalmodels/nonlocalheatequation)

Documentation: [nonlocalheatequation documentation](https://nonlocalmodels.github.io/nonlocalheatequation/documentation/)

Contributors: 

- Pranav Gadikar (Indian Institute of Technology Madras)

- Patrick Diehl (Louisiana State University)

- Prashant K. Jha

# Notes

This is a **Google Summer of Code 2020** project. In this work, we carefully looked the challenges in development of distributed solvers for nonlocal interaction based models such as nonlocal diffusion equation and peridynamics. We propose methods to efficiently handle the increased data dependency (due to large-scale interaction) and balancing the load to minimize cpu idle time. For more details, see [arXiv preprint]({{< relref "publication/gadikar-2021-nonlocal" >}}). Lead developer of the project is Pranav Gadikar.
