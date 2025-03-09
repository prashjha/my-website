---
title: "Finite Element Convergence for State-Based Peridynamic Fracture Models"

authors:
- admin
- "Robert Lipton"
author_notes:
- ''
- "Corresponding author"
date: "2020-03-01"
doi: "10.1007/s42967-019-00039-4"

# Schedule page publish date (NOT publication's date).
publishDate: "2020-03-01"

# Publication type.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "*Communications on Applied Mathematics and Computation*"
publication_short: "CAMC"

abstract: "We establish the a priori convergence rate for finite element approximations of a class of nonlocal nonlinear fracture models. We consider state-based peridynamic models where the force at a material point is due to both the strain between two points and the change in volume inside the domain of the nonlocal interaction. The pairwise interactions between points are mediated by a bond potential of multi-well type while multi-point interactions are associated with the volume change mediated by a hydrostatic strain potential. The hydrostatic potential can either be a quadratic function, delivering a linear force–strain relation, or a multi-well type that can be associated with the material degradation and cavitation. We first show the well-posedness of the peridynamic formulation and that peridynamic evolutions exist in the Sobolev space $H^2$. We show that the finite element approximations converge to the $H^2$ solutions uniformly as measured in the mean square norm. For linear continuous finite elements, the convergence rate is shown to be $C_t \\Delta t + C_s h^2∕\\epsilon^2$, where $\\epsilon$ is the size of the horizon, $h$ is the mesh size, and $\\Delta t$ is the size of the time step. The constants $C_t$ and $C_s$ are independent of $\\Delta t$ and $h$ and may depend on $\\epsilon$ through the norm of the exact solution. We demonstrate the stability of the semi-discrete approximation. The stability of the fully discrete approximation is shown for the linearized peridynamic force. We present numerical simulations with the dynamic crack propagation that support the the- oretical convergence rate."

# Summary. An optional shortened abstract.
summary: ''

tags:
- Numerical Methods
- Numerical Analysis
- Mechanics
- Peridynamics
- Fracture Mechanics
- Finite Element Method
featured: true

# links:
url_pdf: ''
url_code: ''
url_source: 'https://doi.org/10.1007/s42967-019-00039-4'
---