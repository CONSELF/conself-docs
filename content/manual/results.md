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
- *reactions.dat* file: DAT file with nodal reaction forces in all constraints. Moments are calculated from the origin: (0.0, 0.0, 0.0)

All these data are available or not depending on the simulation you are running and on the settings you chose. Once you download these files, it is possible to open them using one among the [post-processors]({{< ref "external-link.md#results-postprocessing" >}}) available on the market.

#### OUTPUT VARIABLES

When using both the online post-processor or the offline ones, you can use all the variables created by your simulation to analyze your results. These variables, which are depending on the application and settings you defined, are among the followings for a CFD simulation:

- **p**: normalized pressure in m²/s² for incompressible flows or pressure in Pa for compressible flows
- **static(p)**: static pressure in Pa for compressible flows
- **U**: velocity vector with components *Ux*, *Uy* and *Uz* in m/s
- **k**: turbulent kinetic energy in m²/s²
- **epsilon**: turbulent dissipation rate in m²/s³
- **omega**: turbulent dissipation frequency in Hz
- **nuTilda**: SpalartAllmaras' viscosity in m²/s
- **nut**: turbulent eddy viscosity in m²/s
- **alpha.fluidA**: fluid A volume concentration
- **s**: passive scalar
- **T**: temperature in K
- **yPlus**: y+ value for the first fluid cell. This variable is valid only on surfaces
- **wallShearStress**: normalized wall shear stress in m²/s². This variable is valid only on surfaces

In case of a MECH analysis instead you get access to the following range of variables:

- **stress**: stress tensor in Pa
- **strain**: strain tensor
- **displacement**: displacement in m
- **sigma von mises**: equivalent stress tension in Pa, calculated using the Von Mises criterion
- **nodal reaction**: nodal reaction in response to external loads

## PRACTICE

#### TO KNOW EVEN MORE

CONSELF is constantly producing more and more tutorials and guidelines to users so they can get benefits out of CFD/FEM simulations. In particular, referring to results post-processing, you can find a certain number of posts with guidelines and tutorials using [ParaView](https://www.paraview.org/), the post-processing software for which we guarantee 100% compatibility, directly on [this page](https://conself.com/blog/category/post-processing/).


