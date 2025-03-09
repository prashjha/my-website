---
title: "Nodal finite element approximation of peridynamics"

authors:
- admin
- Patrick Diehl
- Robert Lipton
author_notes:
- "Corresponding author"
date: "2024-03-11"
doi: "10.1016/j.cma.2024.117519"

# Schedule page publish date (NOT publication's date).
publishDate: "2024-03-11"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "*Computer Methods in Applied Mechanics and Engineering*"
publication_short: "CMAME"

abstract: "This work considers the nodal finite element approximation of peridynamics, in which the nodal displacements satisfy the peridynamics equation at each mesh node. For the nonlinear bond-based peridynamics model, it is shown that, under the suitable assumptions on an exact solution, the discretized solution associated with the central-in-time and nodal finite element discretization converges to the exact solution in $L^2$ norm at the rate $C_1 \\Delta t + C_2 h^2/\\epsilon^2$. Here, $\\Delta t$, $h$, and $\\epsilon$ are time step size, mesh size, and the size of the horizon or nonlocal length scale, respectively. Constants $C_1$ and $C_2$ are independent of $h$ and $\\Delta t$ and depend on the norms of the exact solution. Several numerical examples involving pre-crack, void, and notch are considered, and the efficacy of the proposed nodal finite element discretization is analyzed."

# Summary. An optional shortened abstract.
summary: In this work, nodal finite element discretization is detailed. 

tags:
- Finite Element Methods
- Peridynamics
- Fracture Mechanics
- Numerical Analysis
featured: true

# links:
# - name: ""
#   url: ""
url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: 'https://doi.org/10.1016/j.cma.2024.117519'
url_video: ''

# # Featured image
# # To use, add an image named `featured.jpg/png` to your page's folder. 
# image:
#   caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/jdD8gXaTZsc)'
#   focal_point: ""
#   preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ''
---