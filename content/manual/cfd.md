---
title: CFD
toc: true
weight: 5
---

This step is actually common to a certain number of different applications. The instruction mentioned in this page are completely defining all these applications, even though some limitations may occur in some of them, consisting in a reduced number of possible choices availability.

## FLUID MODELS

The first section is about defining the fluid models, turbulence and density in particular.

- *Flow type*: drop down list from which the user has to select the flow type
	- *Incompressible*: to simulate incompressible fluids like water, oil or air at low velocity.
	- *Compressible*: to simulate compressible ideal-fluids like air or gas in general

- *Turbulence*: drop down list from which the user has to select the turbulence model
	- *Laminar*: to simulate viscous flows in laminar regime
	- *k-epsilon*: to model turbulence via the two equations *k-epsilon* model ([reference](http://turbmodels.larc.nasa.gov/ke-chien.html))
	- *k-omega SST*: to model turbulence via the two equations *k-omega SST* model ([reference](http://turbmodels.larc.nasa.gov/sst.html))
	- *SA*: to model turbulence via the one equation *Spalart-Allmaras* model ([reference](http://turbmodels.larc.nasa.gov/spalart.html))

- *Fluid properties*: specification of the fluid properties parameters
- *Fluid initialization*: definition of the initial condition for the fluid variables

{{% notice info %}}
Properties and parameters to insert vary with the *Flow Type*.
{{% /notice %}}

- *Turbulence initialization*: definition of the initial condition for the turbulent variables

We report here the most common initialization for the turbulent variables

- Turbulent kinetic energy: $k = \cfrac{3}{2} \left( \overline{u} \cdot I \right)^{2}$

- Turbulent dissipation rate: $\varepsilon = \cfrac{0.09 k^{1.5}}{l}$

- Specific dissipation rate: $\omega = \cfrac{\sqrt{k}}{l}$

- Turbulent kinematic eddy viscosity: $\nu_{t} = \sqrt{\cfrac{3}{2}} \overline{u} \cdot I l$

where $I$ is the turbulence intensity (suggested between 1% and 10%) and l is the turbulence length scale, approximated with the hydraulic diameter $D_h$.

{{% notice info %}}
Properties and parameters to insert vary with the *turbulence model*
{{% /notice %}}

## SPECIAL SECTION

*[To be completed ...]*

## BOUNDARY CONDITIONS

The boundary conditions are the fundamental stage of the CFD simulations. CONSELF gives you a multiple choice of boundaries, each of which is target for the peculiar application you are currently using. Here you are a brief summary of what you are required to insert.

{{< figure src="/images/BC_selection.png" alt="Velocity inlet boundary condition application to selected boundary \"asmo\"" title="Velocity inlet boundary condition application to selected boundary \"asmo\"" class="figure-30" >}}

In this section it is possible to specify the boundary condition to apply to the flow. For instance, it is possible to define an inlet, an outlet or a wall. In order to do that the user has to specify for each flow variable its value (or gradient) at a specific boundary.

- *Boundary condition*: drop down list from which the user has to select every surface of which the geometry (and the bounding box) is composed in order to assign boundary conditions to it.

- *BC TYPE list*: a list of available boundary conditions to be assigned to every surface. Every choice of this list gives access to a certain number of parameters to be defined in order to process it correctly.

**In order to get hints and details about boundary conditions you may encounter check [this page]({{< ref "boundary-conditions.md" >}}).**

{{% notice info %}}
By default every surface is assigned an adiabatic no-slip wall boundary condition.
{{% /notice %}}

## SIMULATION SETTINGS

- *Time scheme*: drop down list from which the user has to select which type of simulation they want to perform in terms of behavior in time
	- *Transient*: to setup a simulation where the focus is on how the flow changes in time, i.e. the quantities of interest are variable fluctuations over time
	- *Steady*: to setup a simulation where the focus is on the final flow configuration, i.e. the converged steady solution that does not change anymore

In case *Transient* scheme is chosen

- *Timestep*: time accuracy defining the requested temporal resolution.
- *Final time*: defines the final simulation time.
- *Output frequency*: rules how often simulation results are saved.

In case *Steady* scheme is chosen

- *Number of iterations*: number of iterations performed by the CFD solver. The higher the number, the more accurate the solution.
- *Output frequency*: specifies how often simulation results are saved for the visualization.

After these options you have the possibility to select the number of cores used to run the simulation. Using the dropdown menu you can pick the number of cores you are using to run the simulation. In general, a higher number of cores allows you to get the results in a shorter amount of time.

After completion of all fields, the user can finalize the step clicking on *Submit* button. This will start the **CFD** step application that will appear in the *Case in progress* section of the main *Simulation* page.

{{% notice info %}}
The CFD step usually requires a high number of iterations (few thousands) in order to produce accurate results.
{{% /notice %}}

## RUNTIME RESIDUALS AND CONVERGENCE

While the CFD analysis is running you can check in realtime the progress of your CFD analysis by using the residual plot. This plot returns the residual values for pressure and velocities whilst the simulation is actually proceeding. These residuals represent a fundamental parameter when running a steady case simulation: to monitor the convergence they should keep decreasing while the iterations proceeds, until they reach a threshold value of 10^-4 which actually stops the simulation. For a steady case instead they do not have a convergence threshold, since the simulation proceeds until the specified final time is encountered.

To access the residual graph just click on this icon.

{{< figure src="/images/ProgressBarResiduals.png" alt="Progress bar" title="Progress bar" class="figure-80">}}

A new image pops-up with the residual plot of the simulation. This image is updated in real-time, so if you wait few minutes and click it again you are going to see what has happened meanwhile in the calculation. When the simulation is completed the residual plot of a steady case should look like the following one. The reason of the spike you see after about 1000 iterations is in the simulation process. CONSELF runs in fact two separate simulations for every CFD submitted:

1. First order CFD simulation. Very stable but with low accuracy.
1. Second order CFD simulation. Initialized from the precursor first order CFD simulation, is much more accurate.

{{< figure src="/images/residuals.png" alt="Residuals plot of p (pressure), U (velocity)" title="Residuals plot of p (pressure), U (velocity)" class="figure-30" >}}

## PRACTICE

#### TO KNOW EVEN MORE

CONSELF is constantly producing more and more tutorials and guidelines to users so they can get benefits out of CFD/FEM simulations. In particular, referring to CFD analysis, you can find a certain number of posts by visiting [this page](https://conself.com/blog/category/cfd/).

