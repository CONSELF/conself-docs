---
title: MESH
toc: true
weight: 4
---

Mesh is the STEP required in order to define the mesh.

### Volume mesh

In this section the user is asked to define the mesh algorithm and the basic mesh feature.

- *Meshing algorithm*: drop down list from which the user has to select the meshing algorithm (see pictures below).
	- *Hexahedral*: by using this algorithm, a fully cartesian grid is obtained. Depending on the mesh dimension specifications on the boundaries, local grid refinements are applied to meet the resolution constraints. In case the boundary layer is active, a highly stretched prismatic mesh is added to the tetrahedral one in the vicinity of the boundary surfaces.
	- *Tetrahedral*: by using this algorithm, a fully tetrahedral mesh is obtained. In case the boundary layer is active, a highly stretched prismatic mesh is added to the tetrahedral one in the vicinity of the boundary surfaces.

- *Mesh smoothing*: uniformity level of the volume mesh assigned as a percentage.

{{< figure src="/images/HEXAMesh.png" alt="Hexahedral mesh" title="Hexahedral mesh" class="figure-50" >}}
{{< figure src="/images/Dolfin_mesh.png" alt="Tetrahedral mesh" title="Tetrahedral mesh" class="figure-50" >}}

### Surface Refinement

In this section it is possible to define mesh local refinement for each of the considered surfaces.

- *Boundary treatment*: selection of the boundary using an accordion menu.

- *Mesh uniformity*: percentage that defines how rapidly the basic elements dimension grows.

- *Maximum mesh size*: it defines the local mesh refinement (i.e. the element size) on the selected surface.

#### Advices

In order to choose correctly the *Maximum mesh size* it is important to run a convergence analysis.

### Boundary layer

In this section it is possible to activate the boundary treatment (i.e. boundary layer) for wall resolution in CFD simulations.

- *Boundary treatment*: selection of the boundary using an accordion menu.

- *Wall layers number*: number of wall layers to be extruded from the surface

- *First wall cell height*: value that ranges from $1\cdot e^{-6}\ [m]$ to $1\cdot e^6\ [m]$ and defines the dimension of the nearest cell to the wall in the normal direction.

{{< figure src="/images/TetraBL.png" alt="Representation of the two parameters used to define the boundary treatment" class="figure-50" >}}

{{% notice info %}}
First wall cell height and y+ are mutually influenced. Remember to decrease the cell height if y+ is above 300 for k-epsilon or 1 for other turbulence models.
{{% /notice %}}

After having completed this setup, the user can finalize the step by clicking on the *Submit* button. This will start the **Mesh** step application that will show up in the *Case in progress* section of the main *Simulation* page.

### Practice

More **information about** mesh quality is available in **[this](https://conself.com/blog/4-mesh-issues-poor-accuracy/) blog post** and **[this](https://conself.com/blog/what-is-boundary-layer-and-how-can-you-handle-it/)**.
