---
title: Results
toc: true
weight: 6
---

## RESULTS POST-PROCESSING

Once the CFD/FEA simulation is completed, we are forwarded to the result analysis part of the application. In here it is possible to:

- Check the simulation convergence
- Check the output frequency for the modal/frequency analysis
- Download the results file locally to your computer.

Furthermore, it is possible to post-process the results directly from your browser using the functionalities provided. Check out the following tutorial to see a simple postprocessing of a common case.

{{< youtube 00ZZvxKnQ6s >}}

## DOWNLOADS

The file you download is generally a ZIP file with the following information:

- *EnSight* folder: simulation results files in ensight format
- *ParaView* folder: simulation results files in VTK format
- *RotatingZone* folder: extraction of the rotating zone selected with volume modelling in VTK format
- *residuals* folder: text files with residuals tabulated values
- *yPlus* folder: text files with y+ tabulated values in all wall surfaces
- *wallShearStress* folder: text files with wall shear stress tabulated values in all wall surfaces 
- *residuals.png* image: residual plot
- *frequencies.csv* file: CSV file with all the frequencies calculated

All these data are available or not depending on the simulation you are running and on the settings you chose. Once you download these files, it is possible to open them using one among the [post-processors]({{< ref "external-link.md#results-postprocessing" >}}) available on the market.

## PRACTICE

#### TO KNOW EVEN MORE

CONSELF is constantly producing more and more tutorials and guidelines to users so they can get benefits out of CFD/FEM simulations. In particular, referring to results post-processing, you can find a certain number of posts with guidelines and tutorials using [ParaView](https://www.paraview.org/), the post-processing software for which we guarantee 100% compatibility, directly on [this page](https://conself.com/blog/category/post-processing/).


