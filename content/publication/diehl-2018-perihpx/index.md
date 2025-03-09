---
title: "An Asynchronous and Task-Based Implementation of Peridynamics Utilizing HPX—the C++ Standard Library for Parallelism and Concurrency"

authors:
- "Patrick Diehl" 
- admin
- "Hartmut Kaiser" 
- "Robert Lipton" 
- "Martin Levesque"
author_notes:
- "Corresponding author"
date: "2020-12-04"
doi: "10.1007/s42452-020-03784-x"

# Schedule page publish date (NOT publication's date).
publishDate: "2020-12-19"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ["article-journal"]

# Publication name and optional abbreviated publication name.
publication: "*SN Applied Sciences*"
publication_short: ""

abstract: "On modern supercomputers, asynchronous many task systems are emerging to address the new architecture of computational nodes. Through this shift of increasing cores per node, a new programming model with focus on handling of the fine-grain parallelism with increasing amount of cores per computational node is needed. Asynchronous Many Task (AMT) run time systems represent a paradigm for addressing the fine-grain parallelism. They handle the increasing amount of threads per node and concurrency. HPX, a open source C++ standard library for parallelism and concurrency, is one AMT which is conforming to the C++ standard. Motivated by the impressive performance of asynchronous task-based parallelism through HPX to N-body problem and astrophysics simulation, in this work, we consider its application to the Peridynamics theory. Peridynamics is a non-local generalization of continuum mechanics tailored to address discontinuous displacement fields arising in fracture mechanics. Peridynamics requires considerable computing resources, owing to its non-local nature of formulation, offering a scope for improved computing performance via asynchronous task-based parallelism. Our results show that HPX-based peridynamic computation is scalable, and the scalability is in agreement with the theory. In addition to the scalability, we also show the validation results and the mesh convergence results. For the validation, we consider implicit time integration and compare the result with the classical continuum mechanics (CCM) (peridynamics under small deformation should give similar results as CCM). For the mesh convergence, we consider explicit time integration and show that the results are in agreement with theoretical claims in previous works."

# Summary. An optional shortened abstract.
summary: ''

tags:
- Peridynamics
- Fracture Mechanics
- Software
featured: false

# links:
# - name: ""
#   url: ""
url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: 'https://doi.org/10.1007/s42452-020-03784-x'
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