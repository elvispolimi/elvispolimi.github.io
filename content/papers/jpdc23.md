+++
title = "JDPC23"
aliases = ["paper"]
date = "2023-12-19"
author = "Elvis Lab"
showMetadata = false
+++

## GPU-optimized approaches to molecular docking-based virtual screening in drug discovery: A comparative analysis

Finding a novel drug is a very long and complex procedure. Using computer simulations, it is possible to accelerate the preliminary phases by performing a virtual screening that filters a large set of drug candidates to a manageable number. This paper presents the implementations and comparative analysis of two GPU-optimized implementations of a virtual screening algorithm targeting novel GPU architectures. This work focuses on the analysis of parallel computation patterns and their mapping onto the target architecture. The first method adopts a traditional approach that spreads the computation for a single molecule across the entire GPU. The second uses a novel batched approach that exploits the parallel architecture of the GPU to evaluate more molecules in parallel. Experimental results showed a different behavior depending on the size of the database to be screened, either reaching a performance plateau sooner or having a more extended initial transient period to achieve a higher throughput (up to 5x), which is more suitable for extreme-scale virtual screening campaigns.

## Reference

Link to paper: [https://doi.org/10.1016/j.jpdc.2023.104819](https://doi.org/10.1016/j.jpdc.2023.104819)
