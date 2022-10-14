---
title: "Residual-based error correction for neural operator accelerated infinite-dimensional Bayesian inverse problems"
date: 2022-10-06
publishDate: 2022-10-06
authors: ["Lianghao Cao", "Thomas O\'Leary-Roseberry", "Prashant K. Jha", "J. Tinsley Oden", "Omar Ghattas"]
publication_types: ["3"]
abstract: "We explore using neural operators, or neural network representations of nonlinear maps between function spaces, to accelerate infinite-dimensional Bayesian inverse problems (BIPs) with models governed by nonlinear parametric partial differential equations (PDEs). Neural operators have gained significant attention in recent years for their ability to approximate the parameter-to-solution maps defined by PDEs using as training data solutions of PDEs at a limited number of parameter samples. The computational cost of BIPs can be drastically reduced if the large number of PDE solves required for posterior characterization are replaced with evaluations of trained neural operators. However, reducing error in the resulting BIP solutions via reducing the approximation error of the neural operators in training can be challenging and unreliable. We provide an \textit{a priori} error bound result that implies certain BIPs can be ill-conditioned to the approximation error of neural operators, thus leading to inaccessible accuracy requirements in training. To reliably deploy neural operators in BIPs, we consider a strategy for enhancing the performance of neural operators, which is to correct the prediction of a trained neural operator by solving a linear variational problem based on the PDE residual. We show that a trained neural operator with error correction can achieve a quadratic reduction of its approximation error, all while retaining substantial computational speedups of posterior sampling when models are governed by highly nonlinear PDEs. The strategy is applied to two numerical examples of BIPs based on a nonlinear reaction--diffusion problem and deformation of hyperelastic materials. We demonstrate that posterior representations of the two BIPs produced using trained neural operators are greatly and consistently enhanced by error correction."
featured: true
publication: "*arXiv preprint arXiv:2210.03008*"
url_source: "https://arxiv.org/abs/2210.03008"
tags:
- Neural Operators
- Neural Networks
- Computational Modeling
- Bayesian Inverse Problems
- Mechanics
---

