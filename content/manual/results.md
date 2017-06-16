---
title: RESULTS
toc: true
weight: 6
---

CONSELF offers a web based application to postprocess results. Have a look at the following video to check out the most important features of this web application.

{{< youtube 00ZZvxKnQ6s >}}

</center>
Beside this tool, there are two more functionalities, highlighted in the picture: residual plot and results download. The first one displays the residuals of pressure and velocity fields obtained during the calculation, the latter instead allows to download the results in your local machine. This gives you access to advanced postprocessing functionalities with software such as [ParaView](http://www.paraview.org/download/), available for Unix, Windows and OSx systems.

{{% notice info %}}
The file you download is generally a ZIP file with the following information:
- *EnSight* folder: simulation results files in ensight format
- *ParaView* folder: simulation results files in VTK format
- *RotatingZone* folder: extraction of the rotating zone selected with volume modelling in VTK format
- *residuals* folder: text files with residuals tabulated values
- *yPlus* folder: text files with y+ tabulated values in all wall surfaces
- *wallShearStress* folder: text files with wall shear stress tabulated values in all wall surfaces 
- *residuals.png* image: residual plot
- *frequencies.csv* file: CSV file with all the frequencies calculated

All these data are available or not depending on the simulation you are running and on the settings you chose.
{{% /notice %}}


