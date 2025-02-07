+++
title = "IPDPSW24"
aliases = ["paper"]
date = "2024-05-27"
author = "Elvis Lab"
showMetadata = false
+++

## ZSMILES: An Approach for Efficient SMILES Storage for Random Access in Virtual Screening

Virtual screening is a technique used in drug discovery to select the most promising molecules to test in a lab. To perform virtual screening, we need a large set of molecules as input, and storing these molecules can become an issue. In fact, extreme-scale high-throughput virtual screening applications require a big dataset of input molecules and produce an even bigger dataset as output. These molecules' databases occupy tens of TB of storage space, and domain experts frequently sample a small portion of this data. In this context, SMILES is a popular data format for storing large sets of molecules since it requires significantly less space to represent molecules than other formats (e.g., MOL2, SDF). This paper proposes an efficient dictionary-based approach to compress SMILES-based datasets. This approach takes advan-tage of domain knowledge to provide a readable output with separable SMILES, enabling random access. We examine the benefits of storing these datasets using ZSMILES to reduce the cold storage footprint in HPC systems. The main contributions concern a custom dictionary-based approach and a data preprocessing step. From experimental results, we can notice how ZSMILES leverage domain knowledge to compress ×1.13 more than state of the art in similar scenarios and up to 0.29 compression ratio. We tested a CUDA version of ZSMILES targetting NVIDIA's GPUs, showing a potential speedup of 7×.

## Reference

Link to paper: [https://doi.org/10.1109/IPDPSW63119.2024.00112](https://doi.org/10.1109/IPDPSW63119.2024.00112)
