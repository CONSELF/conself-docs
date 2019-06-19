---
title: Standard ASTM F2996-13 - Hip Femoral Stem
toc: true
weight: 1
---

## INTRODUCTION

In this page we will show you how to set up a static structural analysis of non-modular metallic orthopedic hip femoral stems.

The CONSELF application *STANDARD » ASTM F2996-13 – Hip* allows the user to simulate the hip stem designs for the prediction of the static implant stresses and strains. This application follows the requirements and considerations of the ASTM F2996-13 standard practice for the calculation of stresses and strains seen on a femoral hip stem when loaded in a manner described in the ISO 7206-4 (2010) standard.

The CONSELF application *STANDARD » ASTM F2996-13 – Hip* can be used to establish the worst case within a family of implant sizes in order to provide efficiencies in the amount of physical testing to be conducted.

## TUTORIAL

In order to run the following tutorial, please download the geometry file from here: [Hip Stem Design - ASTM F2996-13.stp](/files/Hip Stem Design - ASTM F2996-13.stp) (597 KB).

For this tutorial, we are using a geometry file based on the representative hip stem model provided by the ASTM Committee F04 on Medical and Surgical Materials and Devices: [link](https://www.astm.org/COMMITTEE/F04.htm).

To start the tutorial, you have to log in to the CONSELF Platform and create a new *Case* to be named *“Hip Stem Testing”*.


{{< figure src="/images/std-astm-f2996-13-hip/01 Case.png" alt="For each Case, you have to prepare 4 steps: Geometry, Mesh, Mech and Results." title="For each Case, you have to prepare 4 steps: Geometry, Mesh, Mech and Results." class="figure-50" >}}

## GEOMETRY

The geometry of the hip stem shall be previously prepared (using a CAD modeler software or an online CAD system such as Onshape) as described in ASTM F2996-13:

1. The femoral stem axis shall be initially aligned with the X axis, pointing from proximal to distal direction.
2. The hip stem trunnion shall be extended or truncated to reproduce the femoral head offset.
3. The hip stem shall be rotated following ISO 7206-4 (2010), depending on the distance CT between the center of femoral head C and the most distal point of the stem T.
4. The hip stem shall be first cut at a distance from the center of the femoral head as described in ISO 7206-4 (2010). This first cut represents the level to which stresses and strains shall be evaluated.
5. The hip stem shall be cut again 10 mm below the first cut. This second cut represent the level below which all faces shall be constrained. Constraining the stem in this manner ensures that excessive erroneous stresses are not generated at the region of interest due to the influence of rigid fixation.

For the geometry analyzed in this tutorial, the hip stem length was into the category 120mm < CT ≤ 250mm, and the femoral head offset was coincident with the center of the circular area at the proximal tip of the trunnion (that is, no trunnion extension or contraction was considered).

#### FILE DATA

You have to upload the geometry from your computer or directly from your Onshape account, then select the correct unit of measure, in this case *Millimeters*.

{{< figure src="/images/std-astm-f2996-13-hip/02 Geometry.png" alt="" title="" class="figure-50" >}}

#### BOUNDARY CREATION

You have to create the boundaries for the uploaded geometry. In this case, there are 6 regions of interest:  

* LOAD
* CONSTRAINT
* NECK
* DRIVER HOLE 
* POTTING LEVEL 
* FREE 

The scheme of the boundaries for the geometry used in this tutorial is illustrated in the following image: 

{{< figure src="/images/std-astm-f2996-13-hip/03 Boundaries scheme.png" alt="" title="" class="figure-30" >}}

For each boundary, you have to: 

* Select the surfaces by clicking on them 
* *Create Boundary*
* Assign a name to the boundary 
* *Create*

{{< figure src="/images/std-astm-f2996-13-hip/04 Boundary creation.png" alt="" title="" class="figure-50" >}}

After having created all the boundaries, you can click on *Next* to proceed. 

#### DOMAIN

For structural analysis, the simulation type can be *Internal* only. To proceed, you have to click on *Submit*, choose a name for the *Geometry* step and confirm the submission. 

{{< figure src="/images/std-astm-f2996-13-hip/05 Geometry submission.png" alt="" title="" class="figure-50" >}}

Now, the geometry is preparing on the cloud. In the meanwhile, you can work on other projects or even shutdown your computer until the geometry is finally prepared. 

## MESH

When the case is ready, you have to reopen it to start the *Mesh* step. 

{{< figure src="/images/std-astm-f2996-13-hip/06 Geometry completed.png" alt="" title="" class="figure-50" >}}

#### VOLUME MESH

You have to select the previous *Geometry* step and assign the level of uniformity of the volume mesh. For this case, 75% is a good value. The higher the value, the better the numerical results, but the meshing and calculation time increases. 

{{< figure src="/images/std-astm-f2996-13-hip/07 Mesh Volume.png" alt="" title="" class="figure-50" >}}

#### SURFACE REFINEMENT

For each boundary previously defined, you have to assign a uniformity level and a max element size, in accordance with this table. The max element size has to be smaller for smaller or more curved and irregular surfaces, and where high stress and strain gradients are expected. At the same time, the max element size can be bigger if the surface is more regular or flat. As before, the higher the value, the better the numerical results, but the meshing and calculation time increases.

{{< figure src="/images/std-astm-f2996-13-hip/08 Mesh Surface.png" alt="" title="" class="figure-50" >}}


|Boundary|Uniformity Level [%]|Max Element Size [m]|
|--------|--------------------|--------------------|
|LOAD|85|0.001|
|CONSTRAINT|85|0.001|
|NECK|85|0.0005|
|DRIVER HOLE|85|0.0005|
|POTTING LEVEL|85|0.0005|
|FREE|85|0.001|

To proceed, you have to click on *Submit*, choose a name for the *Mesh* step and confirm the submission.

{{< figure src="/images/std-astm-f2996-13-hip/09 Mesh Submission.png" alt="" title="" class="figure-50" >}}

Now, the mesh is preparing on the cloud. In the meanwhile, you can work on other projects or even shutdown your computer until the mesh is finally prepared. 

## MECH

When the case is ready, you have to reopen it to start the *Mech* step, where you have to set up the conditions of the Mechanical Model, the Boundary Conditions and the Simulation settings.

### MECHANICAL MODEL

You have to select the previous *Mesh* step and the Mechanical model, that for this application can be *Isotropic linear elastic* only. Then, you have to insert the Solid properties, these values can be usually obtained from the material certification data.

For this case, we use the titanium alloy Ti-6Al-4V with following material properties: 

* Density - ρ: 4420 kg/m³ 
* Poisson coefficient ν: 0.3
* Young Modulus – Y: 113700 MPa 

{{< figure src="/images/std-astm-f2996-13-hip/10 Mechanical Model.png" alt="" title="" class="figure-50" >}}

#### BOUNDARY CONDITIONS

For each boundary previously defined, you have to assign a Boundary Condition type and the relative data, in accordance with the following table. 

{{< figure src="/images/std-astm-f2996-13-hip/11 Boundary conditions.png" alt="" title="" class="figure-50" >}}

|Boundary|Type|Data|
|--------|----|----|
|LOAD|LOAD - Force|Fx = 2300 N; Fy = 0 N; Fz = 0 N|
|CONSTRAINT|CONSTRAINT - Fixed||
|NECK|CONSTRAINT - Free||
|DRIVER HOLE|CONSTRAINT - Free||
|POTTING LEVEL|CONSTRAINT - Free||
|FREE|CONSTRAINT - Free||

For the geometry analyzed in this tutorial, the hip stem length was into the category 120mm < CT < 250mm, so a load of magnitude F = 2300 N along the X-axis was applied to the end circular face of the hip stem trunnion, in order to produce a statically equivalent bending moment to a load applied through the femoral head center.  

The loading of the hip stem was applied such that the magnitude and direction were identical to that defined in ISO 7206-4 (2010). 

#### SIMULATION SETTINGS

You have to select the iterations number and the output frequency to save the solutions results. For a simple geometry like the one analyzed in this case, 1 iteration is a good value. Another parameter you have to choose is the number of cores to be used during the computation. This choice affects the credits used in the current simulation. To proceed, you have to click on *Submit*, choose a name for the *Mech* step and confirm the submission. 

{{< figure src="/images/std-astm-f2996-13-hip/12 Simulation Settings.png" alt="" title="" class="figure-50" >}}

Now, the simulation is running on the cloud. In the meanwhile, you can work on other projects or even shutdown your computer until the simulation is completed.

## RESULTS

When the case is ready, you have to reopen it to start the *Results* step.

#### CHECK RESULTS VALIDITY

First you have to check the residuals history of your simulation. If the residuals converge to very low values, the simulation ran correctly. If the residuals are high, you have to change the simulation settings or run more Iterations.

{{< figure src="/images/std-astm-f2996-13-hip/13 Results residuals.png" alt="" title="" class="figure-50" >}}

#### RESULTS VISUALIZATION

Now, you can finally visualize your results at the last Iteration. If you want, you can see your results directly on CONSELF or download them.

{{< figure src="/images/std-astm-f2996-13-hip/14 Results visualization.png" alt="" title="" class="figure-50" >}}

The measure of interest for this case are the strain and von Mises stress at the Neck, Driver Hole and Potting Level regions.

{{< figure src="/images/std-astm-f2996-13-hip/15 Results Neck.png" alt="" title="" class="figure-50" >}}

{{< figure src="/images/std-astm-f2996-13-hip/16 Results Driver Hole.png" alt="" title="" class="figure-50" >}}

{{< figure src="/images/std-astm-f2996-13-hip/17 Results Potting Level.png" alt="" title="" class="figure-50" >}}

## CONCLUSIONS

Finally, you reached the end of this tutorial and you know how to setup your own simulation. CONSELF is available to any question you may have with our support service via email [support@consel.com](mailto:support@conself.com).

On the website [conself.com](https://conself.com) you can see other video tutorial and learn more about simulations.

Enjoy and start your next own simulation!

## REFERENCES 

* ASTM F2996-13 – Standard Practice for Finite Element Analysis (FEA) of Non-Modular Metallic Orthopaedic Hip Femoral Stems 

* ISO 7206-4 (2010) Implant for Surgery – Partial and Total Hip Joint Prostheses – Part 4: Determination of Endurance Properties and Performance of Stemmed Femoral Components 




