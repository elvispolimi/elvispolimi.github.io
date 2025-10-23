+++
title = "Improve Flexible Docking"
aliases = []
author = "Elvis Lab"
date = "2025-10-23"
showMetadata = false
+++

A recent work named [tldr;](https://pubs.acs.org/doi/full/10.1021/acs.jcim.1c00368) introduced a novel scheme to compute the strain enerfy of a molecule, i.e. how much a molecule is relaxed.
To achieve this goal it provides, for each chemical bond that can alter the shape of the molecule, the most preffered angles.

The goal of this project is to use these information in the open source molecular docking application [muDock](https://github.com/elvispolimi/muDock).
In the current implementation muDock uses a genetic algorithm to dock a molecule inside a protein.
In this project the student is expeceted to change how the genetic algorithm behaves by including the information from the state of the art.
Part of the experiment is to evaluate the difference in the quality between the current method and the new one.

### Contact Reference

Accordi Gianmarco\
<gianmarco.accordi@polimi.it>

Palermo Gianluca\
<gianluca.palermo@polimi.it>

Gadioli Davide\
<davide.gadioli@polimi.it>
