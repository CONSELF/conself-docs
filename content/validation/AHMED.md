---
title: AHMED
toc: true
weight: 1
---

## INTRODUCTION

In this page will be presented how to setup a wind tunnel virtual test on a car model. This is a typical application where the user wants to simulate a uniform velocity profile entering the tunnel from the inlet that reaches the vehicle. It is typically used to evaluate vehicle performances as aerodynamics coefficients. In this case, in order to explain how realistic simulations are carried out, wind tunnel floor will be modeled as a moving wall, with a translational velocity equal to the flow one.
The fluid will be modeled as incompressible and turbulent. An uniform velocity profile will be assigned at inlet. The ground floor will be a no-slip boundary that moves with the same velocity while top and lateral walls will be set as free-slip walls. The car surface will be modeled as a no-slip surface (adherence of the flow to the body) and at the outlet the reference pressure will be prescribed.

Aerodynamics coefficients are strictly related with car performances. They "measure" forces acting on the car body depending on motion and flow characteristics (speed, density, etc). In context like Formula 1 races, these evaluations are boosted to the limit of the available technology because gaining even few percentage points in aerodynamic efficiency means lower drag, that translates into higher speed, lower consumption, higher performances in general.
But even the common urban car, during design phase, underwent an important and accurate aerodynamics test session, in order to improve its external shape.
These measurements can be carried out via wind tunnel experiments or via CFD simulations. In what follows every step towards a CFD simulation of a generic car model inside a wind tunnel will be outlined.


## TUTORIALS
In order to run the following tutorial please, download the geometry file from here: [Ahmed_bb.stl](http://docs.conself.com/files/Ahmed_bb.stl).

In this case, we are using the Ahmed which was described originally in “S.R. Ahmed, G. Ramm, Some Salient Features of the Time-Averaged Ground Vehicle Wake, SAE-Paper 840300, 1984” and it is use also nowadays as benchmark for test and CFD evaluations.

In order to start this tutorial, you have to go in your dashboard and create a new project, named in this case “Car Simulation”.

{{< figure src="/images/AhmedImage1.png" alt="For each case, you have to prepare 4 Steps: 'Geometry', 'Mesh', 'CFD', 'Results'." title="For each case, you have to prepare 4 Steps: 'Geometry', 'Mesh', 'CFD', 'Results'." class="figure-50" >}}

## GEOMETRY

#### FILE DATA

The Geometry can be “Upload” from your Computer or directly from your Onshape account. In both case you have to select the correct unit of measure, in this case  “Meters”.

{{< figure src="/images/AhmedImage2.png" alt="" title="" class="figure-50" >}}

#### BOUNDARY CREATION 1

Now, you have to create the boundaries. In this case, there is only one region, the “Car body”, so it is possible to select directly all the surfaces. Otherwise, you have to select the surfaces clicking on it.

{{< figure src="/images/AhmedImage3.png" alt="" title="" class="figure-50" >}}

#### BOUNDARY CREATION 2

After the region creation, it is possible to name it, in this case as “Car body”.
Each time, you have to click on “Next” to proceed.

{{< figure src="/images/AhmedImage4.png" alt="" title="" class="figure-50" >}}

#### DOMAIN

In this case, the fluid is external from the geometry, so, you have to create an external imaginary  rectangular as domain box for the calculus.
You have to assign a length for the positive and negative side.

**ATTENTION**: you have to use positive numbers also for the negative sides!


|Limits|DeltaX|DeltaY|DeltaZ|
|------|------|------|------|
|Bounding Box+|20|0|100|
|Bounding Box-|20|40|100|

{{< figure src="/images/AhmedImage5.png" alt="" title="" class="figure-50" >}}

#### CONFIRMATION

Now, you have to confirm your decision. And the case is submitted for the preparation.

{{< figure src="/images/AhmedImage6.png" alt="" title="" class="figure-50" >}}

Now, the geometry is preparing on the Cloud. If you want, you can also Shutdown the computer and wait until the finish of the simulation or work on other projects.

When the case is ready, you have to reopen it to start the mesh preparation.

{{< figure src="/images/AhmedImage7.png" alt="" title="" class="figure-50" >}}

## MESH

#### VOLUME MESH

Now, you have to select the previous step and assign a level of mesh uniformity. For this case 75% can be correct. The higher value, the better are the results, but the meshing and calculation time increases.

{{< figure src="/images/AhmedImage8.png" alt="" title="" class="figure-50" >}}

#### SURFACE REFINEMENT

For each surface you have to assign a Uniformity level and a Max Element Size, in accordance with this table. The Max Mesh Size has to be small in the surfaces more curved and irregular. At the same time, can be bigger if the surface is more regular or flat. As before, The higher value, the better are the results, but the meshing and calculation time increases.

{{< figure src="/images/AhmedImage9.png" alt="" title="" class="figure-50" >}}


|   |Uniformity Level [%]|Max Element Size [m]|
|---|--------------------|--------------------|
|Car_body|70|0.6|
|Boundingbox_xmin|30|1|
|Boundingbox_xmax|30|1|
|Boundingbox_ymin|30|1|
|Boundingbox_ymax|30|1|
|Boundingbox_zmin|30|1|
|Boundingbox_zmax|30|1|

#### BOUNDARY LAYER

For the boundary layer, you have to assign the First Cell Height, in accordance with this table and then Submit.

{{< figure src="/images/AhmedImage10.png" alt="" title="" class="figure-50" >}}


|   |Layers Number|First Cell Height [m]|
|---|-------------|---------------------|
|Car_body|0|0.25|
|Boundingbox_xmin|0|1|
|Boundingbox_xmax|0|1|
|Boundingbox_ymin|0|1|
|Boundingbox_ymax|0|1|
|Boundingbox_zmin|0|1|
|Boundingbox_zmax|0|1|

#### CONFIRMATION

Once again, you have to Confirm your choices.

{{< figure src="/images/AhmedImage11.png" alt="" title="" class="figure-50" >}}

As before, the simulation is submitted to the Cloud. Now, you can Shutdown your Computer or prepare other Projects.

## CFD

#### FLUID MODEL

Now, you have to set up the condition of the CFD Simulation, the Fluid Model, the Boundary Conditions, and the Simulation Settings. In this case, the Car is moving at 50 [m/s], so 180 [km/h] in the normal Air Condition.

The flow (air) has this this properties:

|Symbol|Variable|Unit|
|------|--------|----|
|𝝆|Density|1.225 [kg/m3]|
|𝝁|Dynamic Viscosity|0.00001851 [kg/(m*s]|
|𝝂|Kinematic Viscosity|0.0001511 [m2/s]|

Furthermore, in this case, the Pressure is like the Atmospheric Pressure and the Car is moving at 50 [m/s], it means 180 [km/h], along the Z-Axis.

|Symbol|Variable|Unit|
|------|--------|----|
|p|Pressure|101.325 [Pa]|
|UX|Velocity X-Axis|0 [m/s]|
|UY|Velocity Y-Axis|0 [m/s]|
|UZ|Velocity Z-Axis|0 [m/s]|

{{< figure src="/images/AhmedImage12.png" alt="" title="" class="figure-50" >}}

#### BOUNDARY CONDITIONS

Now, you have to set the Boundary Conditions. For stable Simulation, it is suggest the use of at least one Velocity and one Pressure. In this case, the Inlet Velocity is fixed to 50 [m/s] and the Outlet Pressure is the Atmospheric Pressure, it means 101,235 [Pa].

Furthermore, you have to assign the Hydraulic Diameter, that for Quadratic Inlet is like the Side Length.


|Boundary|Type|Data|
|--------|----|----|
|Car_body|WALL|No Slip|
|Boundingbox_xmin|WALL|No Slip|
|Boundingbox_xmax|WALL|No Slip|
|Boundingbox_ymin|WALL|No Slip|
|Boundingbox_ymin|WALL|No Slip|
|Boundingbox_zmax|Inlet - Velocity|U 50 [m/s], Dh 40 [m]|
|Boundingbox_zmin|Outlet - Pressure|101,235|

{{< figure src="/images/AhmedImage13.png" alt="" title="" class="figure-50" >}}

#### SIMULATION SETTINGS

Now, you have to to select the settings. This calculus is steady, it means the is not influenced by the time. As iteration number, for simplex geometry like this one, 100 Iteration is a good number. When you submit, the job is sent to the Cloud. Another important parameter is the numbre of processors used during the computation. This choice affects the credits used in the current simulation.

The Simulation stops when the maximum number of iteration is reached or the residual after the iteration are small enough.

**The non-commercial licence is limited up to 10**.

{{< figure src="/images/AhmedImage14.png" alt="" title="" class="figure-50" >}}

Once again, you have to Submit and Confirm your choices. Now, the Simulation is running on the Cloud and you can work on other Projects.

## RESULTS

#### CHECK RESULTS VALIDITY

First of all, you have to check the Residual History of your Simulation. If the Residuals converge to very low values, the Simulation ran correctly. If the Residual are high, you have to change the Simulation Settings or Run more Iterations.

{{< figure src="/images/AhmedImage15.png" alt="" title="" class="figure-50" >}}

#### RESULTS VISUALIZATION

Now, you can finally visualize your Results at the last Iteration.

{{< figure src="/images/AhmedImage16.png" alt="" title="" class="figure-50" >}}

#### VISUALIZATION TOOLS

If you want, you can see your Results directly on ConSelf or Download them. In order to visualize better your Results and the Flow, you can use some Tools, such as Slices, Clips, Stream Line, and so on.

##### SLICE CREATION

One option is the creation of Slice:

{{< figure src="/images/AhmedImage17.png" alt="" title="" class="figure-50" >}}

Using Slice, you can cut the Mesh with a Plane and easier visualize the Pressure
In this case, can be useful the creation of the Slice in the Middle of the Mesh:


|   | X | Y | Z |
|---|---|---|---|
|Origin|19.45|17.5|0|
|Normal|1|0|0|

{{< figure src="/images/AhmedImage18.png" alt="" title="" class="figure-50" >}}

##### STREAM LINES

Another option in the creation of  Stream Tracker. Normally, the StreamTracker are useful for the Velocity, in this case called “U”. Obviously, you can also change the Palette and Visualize it.

{{< figure src="/images/AhmedImage19.png" alt="" title="" class="figure-50" >}}

For more informations in the post-process, you can see also this [Video Tutorial](https://www.youtube.com/watch?v=00ZZvxKnQ6s). 


## CONCLUSIONS

Finally, you reached the End of this Tutorial and you know how to setup your own Simulation. CONSELF is available to any question you may have with our support service via email [support@consel.com](mailto:support@conself.com).

On the website [conself.com](https://conself.com) you can see other Video Tutorial and learn more about Simulations.

Enjoy and start your next own Simulation!




