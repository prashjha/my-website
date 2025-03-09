---
title: "Load Balancing for Distributed Nonlocal Models Within Asynchronous Many-Task Systems"

authors:
- "Pranav Gadikar" 
- "Patrick Diehl"
- admin
author_notes:
- "Corresponding author"
date: "2021-06-24"
doi: "10.1109/IPDPSW52791.2021.00103"

# Schedule page publish date (NOT publication's date).
publishDate: "2021-06-24"

# Publication type.
publication_types: ["paper-conference"]

# Publication name and optional abbreviated publication name.
publication: "*2021 IEEE International Parallel and Distributed Processing Symposium Workshops (IPDPSW)*"
publication_short: ""

abstract: "In this work, we consider the challenges of developing a distributed solver for models based on nonlocal interactions. In nonlocal models, in contrast to the local model, such as the wave and heat partial differential equations, the material interacts with neighboring points on a larger-length scale compared to the mesh discretization. In developing a fully distributed solver, the interaction over a length scale greater than mesh size introduces additional data dependencies among the compute nodes and communication bottleneck. In this work, we carefully look at these challenges in the context of nonlocal models; to keep the presentation specific to the computational issues, we consider a nonlocal heat equation in a 2d setting. In particular, the distributed framework we propose pays greater attention to the bottleneck of data communication and the dynamic balancing of loads among nodes with varying compute capacity. For load balancing, we propose a novel framework that assesses the compute capacity of nodes and dynamically balances the load so that the idle time among nodes is minimal. Our framework relies heavily on HPX library, an asynchronous many-task run time system. We present several results demonstrating the effectiveness of the proposed framework."

# Summary. An optional shortened abstract.
summary: 

tags:
- Computational Science
- Algorithms
- Software
- Parallel Computing
featured: true

# links:
url_pdf: ''
url_code: ''
url_source: 'https://doi.ieeecomputersociety.org/10.1109/IPDPSW52791.2021.00103'
---