---
title: Car park ventilation
toc: true
weight: 1
---

## INTRODUCTION

In this page will be presented how to setup a car park smoke ventilation simulation.
The current case represent a general HVAC (heating ventilation and air conditioning). Closed car parks in fact suffer of at least two major issue every designer has to take into consideration: production of CO by cars smoke exhausts and high fire risk compared to many surrounding areas.
For these reasons, it is common habit to use a ventilation system with the dual purpose: maintaining low level of CO concentrations in standard conditions and guarantee a smoke free way out in a fire scenario. A modern tool to achieve this goal is represented by Jet Fans: a simple ventilation system located right below the ceiling that convey air, and thus smokes, towards an extractor fan, window or, generally speaking, opening of the car park.
In order to find out the best locations and positioning of such tools CFD represents a great choice: it allows an estimation of the air flows inside the car park. Furthermore, the capabilities of CFD software to predict heat and smoke production, allows to easily simulate the fire case scenario, otherwise impossible in the physical car park.
For the car park ventilation, the intention is the verification of the jet fans positioning across the car park. For this reason, it is possible to neglect small geometrical details, such as small pipes all over the car park, geometrical details of the Jet Fan itself (i.e. motor geometry). 
In this case, we have a Windows Open Air (Green) and a Ramp Outlet (Rosa). Furthermore, in order to move the Air, a Jet Fan is located quite in the middle of the Car Park. The Boundary Condition will be the Atmospheric Pressure for the Window and the Ramp, a negative Velocity for the Fans Suction and a Positive one for the Fans Pushing.

{{< figure src="/images/CarParkImage1.png" alt="" title="" class="figure-50" >}}

## TUTORIALS

In order to run the following tutorial please, download the geometry file from here: [CarParkExample.stp](http://docs.conself.com/files/CarParkExample.stp). In order to start this tutorial, you have to go in your dashboard and create a new project, named in this case “Car Park Ventilation”.

{{< figure src="/images/CarParkImage2.png" alt="" title="" class="figure-50" >}}

For each case, you have to prepare 4 Steps: “Geometry”, “Mesh”, “CFD”, “Results”.

## GEOMETRY

#### FILE DATA

The Geometry can be “Upload” from your Computer or directly from your Onshape account. In both case you have to select the correct unit of measure, in this case  “Centimeters”. In order to create easily the regions for the Boundary Conditions, you have to Select and Hide the Top of the Geometry.

{{< figure src="/images/CarParkImage3.png" alt="" title="" class="figure-50" >}}

#### BOUNDARY CREATION 1

Now, you have to create the boundaries. In this case, there are 5 regions:

- Windows Open Air 
- Ramp Outlet
- Jet Fan Suction
- Jet Fan Pushing
- the rest

To check the scheme of the boundaries in the current geometry check the following image.

{{< figure src="/images/CarParkImage1.png" alt="" title="" class="figure-50" >}}

For the first four region, you have to: 

- Select the surfaces clicking on them
- Create Boundary
- Assign a Name
- Create it

{{< figure src="/images/CarParkImage4.png" alt="" title="" class="figure-50" >}}

Now, you can Click on Next. For the creation of the the remain region, see the next Step.

#### BOUNDARY CREATION 2

Now, if you Click on “Next”, a Warning will appear, because, some surfaces are not been selected. In this case, these surface will be merger together. This is a good trick, when you have some complex wall, like this on. So, you can click on “I am” and create the new region in a Click.

{{< figure src="/images/CarParkImage5.png" alt="" title="" class="figure-50" >}}

#### DOMAIN

In this case, the fluid is internal of the geometry. If you click on Submit, the Geometry will be submitted to the Cloud. If you want, you can also Shutdown the computer and wait until the finish of the simulation or work on other projects.

{{< figure src="/images/CarParkImage6.png" alt="" title="" class="figure-50" >}}

## MESH

When the case is ready, you have to reopen it to start the mesh preparation.

{{< figure src="/images/CarParkImage7.png" alt="" title="" class="figure-50" >}}

#### VOLUME MESH

Now, you have to select the previous step. In this step, you have to assign the level of the uniformity of the volume mesh. For this case 50% can be correct. The higher value, the better are the results, but the meshing and calculation time increases.

{{< figure src="/images/CarParkImage8.png" alt="" title="" class="figure-50" >}}

#### SURFACE REFINEMENT

For each surface you have to assign a Uniformity level and a Max Element Size, in accordance with this table.  The Max Mesh Size has to be smaller for smaller or more curved and irregular surfaces. At the same time, can be bigger if the surface is more regular or flat. As before, the higher value, the better are the results, but the meshing and calculation time increases.

{{< figure src="/images/CarParkImage9.png" alt="" title="" class="figure-50" >}}

|   |Uniformity Level [%]|Max Element Size [m]|
|---|--------------------|--------------------|
|Windows_Open_Air|70|0.1|
|Ramp_Outlet|70|0.1|
|Jet_Fan_Pushing|70|0.01|
|Jet_Fan_Sunction|70|0.01|
|Unselected_parts|70|0.1|

#### BOUNDARY LAYER

For the boundary layer, you have to assign the First Cell Height, in accordance with this table and then Submit.

{{< figure src="/images/CarParkImage10.png" alt="" title="" class="figure-50" >}}

|   |Layers Number|First Cell Height [m]|
|---|-------------|---------------------|
|Windows_Open_Air|0|1|
|Ramp_Outlet|0|1|
|Jet_Fan_Pushing|0|1|
|Jet_Fan_Sunction|0|1|
|Unselected_parts|0|1|

Now, you have to Confirm your Choices and the job is submitted to the Cloud. Now, you can Shutdown your Computer or prepare other Projects.

## CFD

#### FLUID MODEL

Now, you have to set up the condition of the CFD Simulation, the Fluid Model, the Boundary Conditions, and the Simulation Settings. In this case the Flow is incompressible and turbulent Air.

{{< figure src="/images/CarParkImage11.png" alt="" title="" class="figure-50" >}}

As Turbulence Model, the Spalart-Allmars can be chosen, and the Air has this properties:

|Symbol|Variable|Unit|
|------|--------|----|
|𝝆|Density|1.225 [kg/m3]|
|𝝁|Dynamic Viscosity|0.00001851 [kg/(m*s]|
|𝝂|Kinematic Viscosity|0.0001511 [m2/s]|

Furthermore, in this case, the Pressure is like the Atmospheric Pressure and the Flow is not moving.

|Symbol|Variable|Unit|
|------|--------|----|
|p|Pressure|101.325 [Pa]|
|UX|Velocity X-Axis|0 [m/s]|
|UY|Velocity Y-Axis|0 [m/s]|
|UZ|Velocity Z-Axis|0 [m/s]|

#### BOUNDARY CONDITIONS

Now, you have to set the Boundary Conditions.  For stable Simulation, it is suggest the use of at least one Velocity and one Pressure. In this case, the you have two Inlet Velocity (at the Jet Suction and Pushing equal to 10 [m/s]) and two Outlet Pressure (at the Open Windows and at the Ramp) equal to the Atmospheric Pressure, it means 101,235 [Pa]. Furthermore, you have to assign the Hydraulic Diameter, that for the Cylinder is like the normal Diameter, such as 4.22 [cm], 0.0422 [m]

|Boundary|Type|Data|
|--------|----|----|
|Windows_Open_Air|Outlet Pressure|101,235 [Pa]|
|Ramp_Outlet|Outlet Pressure|101,235 [Pa]|
|Jet_Fan_Pushing|Inlet - Velocity|U 10 [m/s], Dh 0.0422 [m]|
|Jet_Fan_Sunction|Inlet - Velocity|U -10 [m/s], Dh 0.0422 [m]|
|Unselected_parts|WALL|No Slip|

{{< figure src="/images/CarParkImage12.png" alt="" title="" class="figure-50" >}}

#### SIMULATION SETTINGS

Now, you have to to select the settings. This calculus is steady, it means the is not influenced by the time. As iteration number, for simplex geometry like this one, 1000 Iterations is a good number. When you submit, the job is sent to the Cloud. The Simulation stops when the maximum number of iteration is reached or the residual after the iteration are small enough.

**The non-commercial licence is limited up to 10**.

{{< figure src="/images/CarParkImage13.png" alt="" title="" class="figure-50" >}}

Once again, you have to Submit and Confirm your choices. Now, the Simulation is running on the Cloud and you can work on other Projects.

## RESULTS

#### CHECK RESULTS VALIDITY

First of all, you have to check the Residual History of your Simulation. If the Residuals converge to very low values, the Simulation ran correctly. If the Residual are high, you have to change the Simulation Settings or Run more Iterations.

{{< figure src="/images/CarParkImage14.png" alt="" title="" class="figure-50" >}}

#### RESULTS VISUALIZATION

Now, you can finally visualize your Results at the last Iteration.

{{< figure src="/images/CarParkImage15.png" alt="" title="" class="figure-50" >}}

#### VISUALIZATION TOOLS

If you want, you can see your Results directly on CONSELF or Download them. In order to visualize better your Results and the Flow, you can use some Tools, such as Slices, Clips, Stream Line, and so on.

{{< figure src="/images/CarParkImage16.png" alt="" title="" class="figure-50" >}}

##### SLICE CREATION

One option is the creation of Slice. Using Slice, you can cut the Mesh with a Plane and easier visualize the Velocity. In this case, can be useful the creation of a Slice in middle of the Fa. Using Slice, you can cut the Mesh with a Plane and easier visualize the Pressure. In this case, can be useful the creation of the Slice in the Middle of the Mesh:

|   | X | Y | Z |
|---|---|---|---|
|Origin|1144|45|-0.45|
|Normal|0|0|1|

{{< figure src="/images/CarParkImage17.png" alt="" title="" class="figure-50" >}}

##### SLICE 2

Now, you can change the Z value and see the Velocity at different Quotas.
(In this case, a Plane Position in a Z=-2 [m])

{{< figure src="/images/CarParkImage18.png" alt="" title="" class="figure-50" >}}

Or with different Normal, in this case Normal =[0,1,0].

{{< figure src="/images/CarParkImage19.png" alt="" title="" class="figure-50" >}}

For more informations in the post-process, you can see also this [Video Tutorial](https://www.youtube.com/watch?v=00ZZvxKnQ6s). 


## CONCLUSIONS

Finally, you reached the End of this Tutorial and you know how to setup your own Simulation. CONSELF is available to any question you may have with our support service via email [support@consel.com](mailto:support@conself.com).

On the website [conself.com](https://conself.com) you can see other Video Tutorial and learn more about Simulations.

Enjoy and start your next own Simulation!




