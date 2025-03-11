+++
title = "Porting of a kernel of a Molecular Docking miniapp"
aliases = []
date = "2025-03-11"
author = "Elvis Lab"
showMetadata = false
+++

In our laboratory we are the main mantainers and developers of LiGen, part of the [EXSCALATE](https://exscalate.com/) platform.
LiGen is an extreme-scale high-throughput virtual screening application for drug discovery that aims at estimating the interaction strenght between a ligand, i.e. a candidate drug, and a protein that represents the disease.
To enable fast prototyping and evaluating new technologies, we also written a small miniapp based on autodock named [muDock](https://github.com/elvispolimi/muDock).

The goal of this project is to port the kernel that implements a genetic algorithm to estimate the 3D displacement of a molecule using [Google Highway](https://github.com/google/highway).
Also, the analysis and research of performance portability using other tools like SYCL or HIP can be an option.

### Contact Reference:
Accordi Gianmarco\
gianmarco.accordi@polimi.it

Palermo Gianluca\
gianluca.palermo@polimi.it

Gadioli Davide\
davide.gadioli@polimi.it
