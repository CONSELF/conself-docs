---
title: Mesh
toc: true
weight: 4
---

Mesh is the STEP required in order to define the mesh.

## VOLUME MESH

In this section the user is asked to define the mesh algorithm and the basic mesh feature.

- *Meshing algorithm*: drop down list from which the user has to select the meshing algorithm (see pictures below).
	- *Hexahedral*: by using this algorithm, a fully cartesian grid is obtained. Depending on the mesh dimension specifications on the boundaries, local grid refinements are applied to meet the resolution constraints. In case the boundary layer is active, a highly stretched prismatic mesh is added to the tetrahedral one in the vicinity of the boundary surfaces.
	- *Tetrahedral*: by using this algorithm, a fully tetrahedral mesh is obtained. In case the boundary layer is active, a highly stretched prismatic mesh is added to the tetrahedral one in the vicinity of the boundary surfaces.

- *Mesh smoothing*: uniformity level of the volume mesh assigned as a percentage.

{{< figure src="/images/HEXAMesh.png" alt="Hexahedral mesh" title="Hexahedral mesh" class="figure-30" >}}
{{< figure src="/images/Dolfin_mesh.png" alt="Tetrahedral mesh" title="Tetrahedral mesh" class="figure-30" >}}

## SURFACE REFINEMENT

In this section it is possible to define mesh local refinement for each of the considered surfaces.

- *Boundary treatment*: selection of the boundary using an accordion menu.

- *Mesh uniformity*: percentage that defines how rapidly the basic elements dimension grows.

- *Maximum mesh size*: it defines the local mesh refinement (i.e. the element size) on the selected surface.

{{% notice info %}}
In order to choose correctly the *Maximum mesh size* it is important to run a convergence analysis.
{{% /notice %}}

## BOUNDARY LAYER

In this section it is possible to activate the boundary treatment (i.e. boundary layer) for wall resolution in CFD simulations. As showed in the following image, the boundary layer is a zone where the surface mesh is extruded in direction normal to the external surface. The user can here customize this type of extrusion by defining the number of cells to be extruded and the dimensions of the extrusion zone. This operation is fundamental when dealing with a CFD simulation since the quality of the results depends on the wall distance of the first fluid cell.

{{< figure src="/images/TetraBL.png" alt="Representation of the two parameters used to define the boundary treatment" class="figure-30" >}}

- *Boundary treatment*: selection of the boundary using an accordion menu.
- *Wall layers number*: number of wall layers to be extruded from the surface
- *First wall cell height*: value that ranges from $1\cdot e^{-6}\ [m]$ to $1\cdot e^6\ [m]$ and defines the dimension of the nearest cell to the wall in the normal direction.

{{% notice info %}}
First wall cell height and y+ are mutually influenced. Remember to decrease the cell height if y+ is above 300 for k-epsilon or 1 for other turbulence models. Several [y+ estimator](https://www.cfd-online.com/Tools/yplus.php) are available online to give guidelines about the wall cell dimension.
{{% /notice %}}

After having completed this setup, the user can finalize the step by clicking on the *Submit* button. This will start the **Mesh** step application that will show up in the *Case in progress* section of the main *Simulation* page.

## MESH QUALITY

Once the mesh step is completed, using the graphic interface it is possible to view the obtained grid. Mesh quality is reported with a certain number of variables which highlights problematic cells. The most common variables are:

* skewFaces

{{< figure src="/images/Skewness.png" alt="Skew face representation" class="figure-50" >}}

* nonOrthoFaces

{{< figure src="/images/aspectRatio.png" alt="Non orthogonal cells" class="figure-50" >}}

* highAspectRatioCells

{{< figure src="/images/Orthogonality.png" alt="High aspect ration visualization" class="figure-50" >}}

CONSELF automatically impose some fixed thresholds for all these problems. When this threshold is passed the cell is highlighted as low quality. The highlight mechanism is rather simple: all these variables are assigned a 0 value where no problem is present, 1 where the problem is present. In order to view the mesh zone where quality test fails it is necessary to filter and extract the problematic zone as described in this tutorial.

* Open the menu clicking on the **Pipeline** button
* select the solution file *system.foam*
* apply the **Threshold** filter under the menu identified by a *+* sign
* in the filter properties choose the quality variable (i.e. *skewFaces*) as parameter
* set the minimum and maximum threshold values as 0.5 and 1 and click on the small tick in the upper part of the filter property
* in the pipeline menu activate the visualization of the entire file *system.foam* and set *Opacity* value in its *Representation* property equal to 0.3

{{< youtube MnKwiDkBJBU >}}

## PRACTICE

#### TO KNOW EVEN MORE

CONSELF is constantly producing more and more tutorials and guidelines to users so they can get benefits out of CFD/FEM simulations. In particular, referring to meshing, you can find a certain number of posts by visiting [this page](https://conself.com/blog/category/meshing/).
