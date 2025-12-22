---
title: "PeriDEM -- High-fidelity modeling of granular media consisting of deformable complex-shaped particles"

authors:
- admin
author_notes:
- "Corresponding author"
date: "2025-12-19"
doi: '10.21105/joss.07525'

# Schedule page publish date (NOT publication's date).
publishDate: "2025-12-19"

# Publication type.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "*Journal of Open Source Software*"
publication_short: "JOSS"

abstract: "Accurate simulation of granular materials under extreme mechanical conditions, such as crushing, fracture, and large deformation, remains a significant challenge in geotechnical, manufacturing, and mining applications. Classical discrete element method (DEM) models typically treat particles as rigid or nearly rigid bodies, limiting their ability to capture internal deformation and fracture. The PeriDEM library, first introduced by Jha et al. (2021), addresses this limitation by modeling particles as deformable solids using peridynamics, a nonlocal continuum theory that naturally accommodates fracture and significant deformation. Inter-particle contact is handled using DEM-inspired local laws, enabling realistic interaction between complex-shaped particles. Implemented in C++, PeriDEM is designed for extensibility and ease of deployment. It relies on a minimal set of external libraries, supports multithreaded execution, and includes demonstration examples involving compaction, fracture, and rotational dynamics. The framework facilitates granular-scale simulations, supports the development of constitutive models, and serves as a foundation for multi-fidelity coupling in real-world applications."

# Summary. An optional shortened abstract.
summary: ''

tags:
- Granular Media
- Particle Breakage
- Contact Mechanics
- Discrete Element Method
- Peridynamics
- Fracture Mechanics
featured: true

# links:
url_pdf: 'https://doi.org/10.21105/joss.07525'
url_code: 'https://github.com/prashjha/PeriDEM'
url_source: 'https://joss.theoj.org/papers/10.21105/joss.07525'
---