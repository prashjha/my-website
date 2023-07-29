---
title: "Corrector Operator to Enhance Accuracy and Reliability of Neural Operator Surrogates of Nonlinear Variational Boundary-Value Problems"
date: 2023-06-21
publishDate: 2023-06-21
authors: ["Prashant K Jha", "J. Tinsley Oden"]
publication_types: ["3"]
abstract: "This work focuses on developing methods for approximating the solution operators of a class of parametric partial differential equations via neural operators. Neural operators have several challenges, including the issue of generating appropriate training data, cost-accuracy trade-offs, and nontrivial hyperparameter tuning. The unpredictability of the accuracy of neural operators impacts their applications in downstream problems of inference, optimization, and control. A framework is proposed based on the linear variational problem that gives the correction to the prediction furnished by neural operators. The operator associated with the corrector problem is referred to as the corrector operator. Numerical results involving a nonlinear diffusion model in two dimensions with PCANet-type neural operators show almost two orders of increase in the accuracy of approximations when neural operators are corrected using the proposed scheme. Further, topology optimization involving a nonlinear diffusion model is considered to highlight the limitations of neural operators and the efficacy of the correction scheme. Optimizers with neural operator surrogates are seen to make significant errors (as high as 80 percent). However, the errors are much lower (below 7 percent) when neural operators are corrected following the proposed method. "
featured: true
publication: "*arXiv preprint arXiv:2306.12047 (To appear in CMAME)*"
url_source: "https://arxiv.org/abs/2306.12047"
tags:
- Neural Networks
- Neural operators
- Variational Formulation
- Partial Differential Equations
- Topology Optimization
- Computational Methods
---

| ![](files/movie.gif) | 
| :----: | 
| *Topology optimization of the diffusivity field in a nonlinear diffusion model. Neural operator and neural operator with corrector employed as a surrogate of the forward model.* |

| ![](files/result.png) | 
| :----: | 
| *Comparing the optimizers of the topology optimization problem for different cases (1) true forward model, (2) neural operator surrogate of the forward model, and (3) neural operator with corrector.* |
