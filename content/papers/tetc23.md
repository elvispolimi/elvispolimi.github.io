+++
title = "TETC23"
aliases = ["paper"]
date = "2023-05-31"
author = "Elvis Lab"
showMetadata = false
+++

## EXSCALATE: An Extreme-Scale Virtual Screening Platform for Drug Discovery Targeting Polypharmacology to Fight SARS-CoV-2

The social and economic impact of the COVID-19 pandemic demands a reduction of the time required to find a therapeutic cure. In this paper, we describe the EXSCALATE molecular docking platform capable to scale on an entire modern supercomputer for supporting extreme-scale virtual screening campaigns. Such virtual experiments can provide in short time information on which molecules to consider in the next stages of the drug discovery pipeline, and it is a key asset in case of a pandemic. The EXSCALATE platform has been designed to benefit from heterogeneous computation nodes and to reduce scaling issues. In particular, we maximized the accelerators’ usage, minimized the communications between nodes, and aggregated the I/O requests to serve them more efficiently. Moreover, we balanced the computation across the nodes by designing an ad-hoc workflow based on the execution time prediction of each molecule. We deployed the platform on two HPC supercomputers, with a combined computational power of 81 PFLOPS, to evaluate the interaction between 70 billion of small molecules and 15 binding-sites of 12 viral proteins of SARS-CoV-2. The experiment lasted 60 hours and it performed more than one trillion ligand-pocket evaluations, setting a new record on the

## Reference

Link to paper: [https://doi.org/10.1109/TETC.2022.3187134](https://doi.org/10.1109/TETC.2022.3187134)
