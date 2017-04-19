---
title: CONSELF simulation process
toc: true
weight: 2
---

Using CONSELF means entering a new mindset, a new philosophy of simulating. Therefore, in order to be able to read and understand the following tutorials, bear in mind the following key definitions:

**Simulation**: a mathematical procedure that allows to reproduce in a virtual environment - software - a physical behavior. Compared to laboratory tests, it is a quicker and cheaper process. Ultimately, simulations help engineers validate the hypothesis behind every design phase.

**Case**: any single test performed by using a simulation system.

**Step**: any single phase the user has to accomplish in order to run a complete case simulation.

Although each CASE simulation depends on the users' needs, CONSELF defines an identical path for every simulation. This path is divided into the following STEPS:

1. Geometry
2. Mesh
3. CFD
4. Results

Obviously, in order to perform a certain STEP all previous ones must be completed. Furthermore, it is possible to run multiple STEP from the same precursor (i.e. run multiple CFD by using the same mesh). For this reason, when starting a new STEP it is always required to link it to a precursor, as shown in the picture.

{{< figure src="/images/Step_selection.png" alt="Selection of a precursor MESH 2D step when starting a MESH 3D one" title="Selection of a precursor MESH 2D step when starting a MESH 3D one" >}}

In the present manual, each of these steps are accurately described and displayed, with examples taken form CONSELF-run tutorials.

### Case Management

After having logged in, the CONSELF dashboard appears on screen. On the menu on the left side, the last entry is the **Simulations** tab. Click on it to be redirected to the simulations front page, shown in the following figure. There are three main sections: two in the upper part and one in the bottom part of the figure.

- *Creation of new case*: the case name has to be inserted in the edit box and must be no longer than 255 characters.
- *Application selection* drop-down menu. This menu defines the application to be used in the current case among the available ones.
- *Create* button redirects the user to [Section A]({{< ref "geometry.md#file-data" >}}) of the GEOMETRY step of the newly created case.

|Field name|Application name|Main features|
|----------|----------------|-------------|
|CFD|GENERAL|Compressible and incompressible with steady and transient features.|
|CFD|TURBO - SRF PUMPS|Single reference frame (rotating) incompressible flow. Steady simulation for pumps.|
|CFD|OIL&GAS - FLOW WITH PARTICLES|Incompressible flow with with solid particles transported.|
|CFD|OIL&GAS - MULTIPHASE FLOW|Incompressible flow of two inmiscible species.|
|CFD|HVAC - JET FANS|CO and FIRE scenarios for indoor car park simulations.|
|MECH|STATIC|Mechanical simulation using an isotropic linear elastic material.|

{{% notice info %}}
Type the first part of the application name to filter the available choices.
{{% /notice %}}

{{< figure src="/images/CarSimulationCaseCreation.png" alt="Definitions of the zones in which the user interface is divided" title="Definitions of the zones in which the user interface is divided" >}}

- *Selection of case*: the user can open a previously created case from the drop-down list.
	- *Open* button redirects the user to the section/step where they left the last time that particular case was edited.

- *Cases in progress*: all running simulations are shown in a table with the following details
	- *Case name*: as inserted by the user during the creation
	- *Step*: the step that is running in that moment
	- *Progress*: both progress and percentage bars show the completion status for a given step
	- *ETA*: estimated time remaining to the end of the current step

### Disk Management

{{< figure src="/images/Storage_page.png" alt="Disk management interface with reference to the area of the screen and the information displayed" title="Disk management interface with reference to the area of the screen and the information displayed" >}}

CONSELF provides also cloud storage to save your remote cases. The storage availability may be different according to the plan you activate in our store. It is possible to check the space available on the disk and manage old cases.

### CONSELF step by step

CONSELF guides you through the simulation literally step by step; in fact, in order to complete a simulation, the user has to go through several steps, each of which fulfills a precise task. Given the high flexibility of this method, users, less experienced as well, may take advantage of this philosophy of work: they have the ability to control the process, start over or modify what had previously been done. When a CASE is opened, a STEP interface is accessed, as shown in the picture below.

{{< figure src="/images/General_STEP_page.png" alt="General STEP page" >}}

The application is generally divided into two sides:

- *Left side*: current step options to be defined by the user

- *Right side*: view of the simulation results up to the current step

It is fundamental to note the button (GREEN or RED) on the top right of the page named *Steps completed*. By clicking it is possible to access a summary of performed steps with error messages, settings used and other information useful to keep improving your simulation. We recommend to **check the [error](:Errors "wikilink")** to have a quick overview of the most common error and their solution.
