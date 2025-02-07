+++
title = "Porting of an Holographic Application on GPUs"
aliases = []
date = "2024-03-13"
author = "Elvis Lab"
showMetadata = false
+++

In this repository is available [SLM-3dPointCloud](https://github.com/ppozzi/SLM-3dPointCloud/tree/master).
SLM-3dPointCloud is a Python library for generating 3d point cloud holograms, with phase only spatial light modulators, in real time through a GPU implementation.
It is of particular interests the Random Superposition algorithm available in the application.

The project consists in the porting of this application using C/C++ from python, and the optimization of CUDA kernel already available in the application.
The project involves mainly interaction with high-end NVIDIA GPUs, which we can provide access, along with free courses and certifications from NVIDIA [DLI](https://www.nvidia.com/en-us/training/).
Also, the analysis and research of performance portability using other tools like SYCL or HIP can be an option.

### Contact Reference:
Accordi Gianmarco\
gianmarco.accordi@polimi.it

Palermo Gianluca\
gianluca.palermo@polimi.it

Gadioli Davide\
davide.gadioli@polimi.it