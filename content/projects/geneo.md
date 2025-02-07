+++
title = "Analysis of a multi-layered map access on GPUs"
aliases = []
date = "2024-03-13"
author = "Elvis Lab"
showMetadata = false
+++

In our laboratory we are the main mantainers and developers of LiGen, part of the [EXSCALATE](https://exscalate.com/) platform.
LiGen is an extreme-scale high-throughput virtual screening application for drug discovery.
This project involves the molecular docking part of the application, which place and evaluate the interaction strength of a ligand (drug candidate) against a target (the disease protein).
It has been used for the [largest](https://doi.org/10.1109/TETC.2022.3187134) virtual screening up to now.
LiGen has been developed in the context of two European Project: [Exscalate4COV](https://www.exscalate4cov.eu/) and [LIGATE](https://www.ligateproject.eu/).

Now we are interested in the integration of new machine learning module in LiGen.
In particular we are interested in [GENEOnet](https://arxiv.org/abs/2202.00451).
GENEOnet produces a set of 3D grid which has to be evaluated for each input ligand.
Since molecular docking is an embarrassingly parallel problem, it is an open research question which memory architecture is more efficient to access memory on external accelerator like GPUs.
It can be extended with a work on the analysis of GPUs tensor cores usage to perform operations, like reductions, for this access pattern. Like in this [publication](https://doi.org/10.1007/978-3-031-39698-4_41).

The project has to be done using C/C++, and it involves mainly interaction with high-end NVIDIA GPUs, which we can provide access, along with free courses and certifications from NVIDIA [DLI](https://www.nvidia.com/en-us/training/).
Also, the analysis and research of performance portability using other tools like SYCL or HIP can be an option.

### Contact Reference:
Accordi Gianmarco\
gianmarco.accordi@polimi.it

Palermo Gianluca\
gianluca.palermo@polimi.it

Gadioli Davide\
davide.gadioli@polimi.it