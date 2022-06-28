+++
# Project title.
title = "Signal recovery from MRI"

# Date this page was created.
date = 2020-07-18T00:00:00

# Project summary to display on homepage.
summary = "Development of models for improved signal recovery and image reconstruction, and developement and application of new methods for optimal data acquisition with uncertain model parameters"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["computational oncology", "model inference", "MRI data", "HP MRI"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides = "example-slides"

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""


# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  #caption = "Tumor growth towards nutrient supplying vessel and angiogenesis"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++


# Activities

## 1. A mechanistic tumor growth model for HP MRI

The goals of this project are two-fold; 1) optimal experimental design for Hyperpolarized (HP) MRI formulation to obtain the optimal MRI scan parameters such that the information content of the data about the parameter of interest is increased, and 2) the development of PDE-based high-fidelity model for HP-MRI. Hyperpolarized (HP) 13C-Pyruvate MR imaging provides unique information about metabolic alterations indicative of the aggressiveness of certain cancer types. The information content of the HP-MRI data is fundamentally limited by the physics and chemistry of specific processes that take place at an atomic scale during a well-defined chemical reaction. The HP signal (magnetization of pyruvate and lactate) is a fixed resource established at the polarizer, naturally decays over time, and cannot be renewed after injection. The signal is further reduced with every radio-frequency excitation by the MR pulse sequence. A key parameter of interest recovered from HP-MRI measurements is the apparent pyruvate-to-lactate exchange rate, kPL, for measuring tumor metabolism. One of the key goals of this project is to formulate an Optimal Experimental Design (OED) problem to determine the MRI scan parameters that lead to data with increased information about the parameter of interest. The second goal of this project is to develop a high-fidelity model for HP-MRI. The high-fidelity model, if carefully constructed, can be closer to reality than existing pharmacokinetic models, which are spatially invariant. Further, using such high-fidelity models in the OED problem can lead to better MRI design parameters. 

In Fall 2020, Oden Institute, MD Anderson Cancer Center, and TACC signed an MOU to advance cancer research. This project on HP-MRI was selected as one of the five pilot projects under the joint initiative for 09/01/2020 - 08/31/2021.

We recently submitted an article, see [preprint]( {{< relref "publication/jha-2022-mutual" >}}), on optimal experimental design formulation for HP-MRI based on the mutual-information. 


