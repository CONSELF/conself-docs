---
title: MECH
toc: true
weight: 5
---

This step is actually common to a certain number of different applications. The instruction mentioned in this page are completely defining all these applications, even though some limitations may occour in some of them, consisting in a reduced number of possible choices availability.

## MECHANICAL MODELS

The first section someone has to define in a static mechanical simulation regards the mechanical model. This is a system of hypothesis that link calculated displacement with stress and shear. The models available are:

- *Mechanical model*: dropdown menu with all the choices
	- *Isotropic linear elastic*: isotropic matherial with linear relation between stress and shear: $ \sigma = E \cdot \varepsilon $
	- *Isotropic linear elastic (large displacement)*: isotropic matherial with linear relation between stress and shear. Displacement are not negligigle considering the matherial elasticity.

For each of the choices made in the mechanical model, it is then necessary the definition of the matherial properties such as:

- $\rho$ density
- $\nu$ poisson ration
- $E$ Young modulus

## BODY FORCE

In this section it is possible to insert a body force, a force acting on the whole volume we are simulating. Among the possible choices you have:

- *None*: no body force is applied
- *Centrifugal force*: the whole body is considered in rotation.
	- *Rotating point* represents the centre of the rotation
	- *Rotating axis* is the axis along which the body is rotating
	- *Rotating speed* is the rotational speed

## BOUNDARY CONDITIONS

Similarly to what happens in CFD simulations, it is now necessary to insert a mixed of boundary conditions in order to define the external loads and constraints. To do so, CONSELF web applications gives you the opportunity to use the following boundaries:

- **CONSTRAINT - Free**: simple boundary condition where neither constraints nor loads are applied.
- **CONSTRAINT - Fixed**: possibility to define a constraint boundary condition. The constraint can be applied through a combinations of constraints along the X, Y and Z axis. It is user responsability the definition of a fully constraint system to avoid liabilities.
- **LOAD - Force**: load application as a distributed force in N/mm². The force direction is specified by the user by the definition of the three components along the X, Y and Z axis.
- **LOAD - Pressure**: load application of a pressure in Pa. The pressure generates a force which is always orthogonal to the surface.

{{% notice info %}}
Before running a MECH simulation make sure you are limiting al possible liabilities in all directions. If this condition is not satisfied you are going to get an error from the application.
{{% /notice %}}

## SIMULATION SETTINGS

In simulation settings the user interface requires a set of numerical parameters. In particular:

- **Iterations number**: definition of the number of iterations required to complete the simulation
- **Output frequency**: the frequency we are using to save an output visualization file
- **Cores number**: the number of cores required to run the simulation

{{% notice info %}}
The **iterations number**, and consequently, the **output frequency** are useful parameters when dealing with non-linear simulations. A higher number of iterations helps the solver to achieve a complete level of convergence.
{{% /notice %}}

## RUNTIME RESIDUALS AND CONVERGENCE

Since MECH analysis can be non-linear (i.e. large displacement analysis), the FEA assumes an iterative process to calculate the results. As usual, it is possible to monitor real-time the residuals calculated after each iteration by clicking on the appropriate button of the progress bar.

{{< figure src="/images/ProgressBarResiduals.png" alt="Progress bar" title="Progress bar" class="figure-80">}}

The residual plot consists of two different graphs: the top one represents the residuals of the algebric method to solve the linear system of equations whilst the bottom one is the number of inner iterations made to achieve the level of residuals. In a correct analysis the residuals should always be below 10^-6, whilst the inner iterations number can be up to 20.

{{< figure src="/images/residualsMECH.png" alt="Residuals of MECH analysis" title="Residuals of MECH analysis" class="figure-30" >}}

## PRACTICE

#### TO KNOW EVEN MORE

CONSELF is constantly producing more and more tutorials and guidelines to users so they can get benefits out of CFD/FEM simulations. In particular, referring to MECH analysis, you can find a certain number of posts by visiting [this page](https://conself.com/blog/category/fea/).

