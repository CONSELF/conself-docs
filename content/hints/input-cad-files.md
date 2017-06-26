---
title: Input CAD Files
toc: true
weight: 1
---

The generation of a CAD file is one of the most important parts of any CFD simulation. CONSELF can handle multiple geometry types in order to help the user during his task. At the same time, it is recommendable to follow some basics tricks in order to be confident about the final result of the simulation and avoid geometry errors and mesh inconsistencies.

## Create fluid volumes

In order to run a CFD simulation you have to generate the **volume of fluid**. In other words you have to model the geometry occupied by the fluid and not by the solid. Compared to standard modelling, *CFD usually requires the negative of the solid model*. The following tutorials shows th generation of the volume flow that surrounds a simple impeller for HVAC simulation.

{{< youtube zqbSQJEEYXU >}}

## Simplify your geometry

*Remove all features and edges which are smaller than 0.1% times the maximum size of your 3D model*. Small parts, in fact, have a minimum influence to your simulation results but, on the other hand, they often are very difficult to mesh. The general suggestion is to remove these feature, as also highligted by the following tutorials.


{{< youtube Xqt5kwURJG0 >}}

## Avoid edges

**Avoid narrow angles** by creating fillets with a radius of, at least, 0.1% times the maximum size of your 3D model. Very often, this CFD restriction is also a structural problem when actually making the prototype.

{{< figure src="/images/NarrowAngles.png" alt="Narrow Angles" class="figure-30" >}}

## Colors are helpful

At the beginning of every GEOMETRY step, regardless we are about to run a CFD or a MECH simulations, we have to define the surface groups which are later used to impose boundary conditions or wall refinement. To speed up this process, CONSELF can read colors used in input files and use these colors to define surface groups.

{{< figure src="/images/GeometryColors.png" alt="Geometry Colors" class="figure-30" >}}

## Assembly files?

Even though CONSELF can handle assembly file, keep in mind that both FEM and CFD simulations are not meant to simulate complex systems. In general assembly files for these analysis are composed by a limited number of parts (max. 5) which interact one another. If your file is actually bigger than this probably you are wrongly considering the simulation capabilities and it may be worth a while contacting our support team.

{{< figure src="/images/Assembly.png" alt="Assembly.png" class="figure-30" >}}