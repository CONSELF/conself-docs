---
title: Simulation Process
toc: true
weight: 2
---

## INTRODUCTION

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

{{< figure src="/images/Step_selection.png" alt="Selection of a precursor MESH step when starting a CFD one" title="Selection of a precursor MESH step when starting a CFD one" >}}

In the present manual, each of these steps are accurately described and displayed, with examples taken form CONSELF-run tutorials.

#### CASE MANAGEMENT

After having logged in, the CONSELF dashboard appears on screen. On the menu on the left side, the last entry is the **Simulations** tab. Click on it to be redirected to the simulations front page, shown in the following figure. There are three main sections: two in the upper part and one in the bottom part as also highlighted by the following image.

{{< figure src="/images/CarSimulationCaseCreation.png" alt="Definitions of the zones in which the user interface is divided" title="Definitions of the zones in which the user interface is divided" class="figure-50" >}}

When defining a new case, the user is requested a certain number of inputs:

- *Case name*: the case name has to be inserted in the edit box and must be no longer than 255 characters.
- *Application selection* drop-down menu. This menu defines the application to be used in the current case among the available ones. The following table clearly shows the currently available applications and the simulation feature the user access when using it.

|Sector|Application name|Main features|
|----------|----------------|-------------|
|CFD|GENERAL|Compressible and incompressible with steady and transient features.|
|CFD|TURBO - SRF PUMPS|Single reference frame (rotating) incompressible flow. Steady simulation for pumps.|
|CFD|OIL&GAS - FLOW WITH PARTICLES|Incompressible flow with with solid particles transported.|
|CFD|OIL&GAS - MULTIPHASE FLOW|Incompressible flow of two inmiscible species.|
|CFD|HVAC - PASSIVE SCALAR TRANSPORT|Passive scalar transport for compressible and incompressible flows.|
|MECH|STATIC - LINEAR ELASTIC|Mechanical simulation using an isotropic linear elastic material.|
|MECH|DYNAMIC - FREQUENCY|Modal analysis of an isotropic linear elastic material.|

- *Create* button redirects the user to the [GEOMETRY]({{< ref "geometry.md" >}}) step of the created case.

{{% notice info %}}
Type the first part of the application name to filter the available choices.
{{% /notice %}}

On the right handside, it is possible to access previously created simulation which have not been erased yet. All the data are in fact stored using the cloud [space available]({{< ref "simulation-process.md#disk-management" >}}) according to your cloud account.

- *Selection of case*: the user can open a previously created case from the drop-down list.
	- *Open* button redirects the user to the section/step where they left the last time that particular case was edited.

The bottom part of this page is actually peculiar because it gives quite a few information about the steps which are submitted to the system to be processed.

{{< figure src="/images/ProgressBar.png" alt="Progress bar" title="Progress bar" class="figure-80">}}

- *Case name*: as inserted by the user during the creation
- *Step type*: the step that is running in that moment
- *Step name*: the name assigned to the running step
- *State*: Status of the current step. It can be one among
	- PREPARED -> Process is waiting for the system to start it
	- RUNNING -> Process is running
- *Progress*: both progress and percentage bars show the completion status for a given step
- *ETA*: estimated time remaining to the end of the current step
- *Operations*: functionalities to interact with the running process and in particular:
	- Residuals button -> Check the residuals graph of the running step (only for CFD and MECH steps)
	- Stop button -> Stop the execution of the current process

It is important to note that there is no limit of number of contemporary running steps a user can have, as long as there are sufficient credits.

#### DISK MANAGEMENT

CFD and FEM simulations are quite expencive in terms of storage resources. According to the subscription you are using, a limit is applied to the storage available to your user. If you filled the amount of storage available it is possible to:

- [Download]({{< ref "results.md#downloads" >}}) the results of completed case in your local machine
- Erase old cases which are no more in use.

Under the **storage** page, the user can find analytical data about his storage usage. At the same time it is possible to delete old cases by selecting them one by one. In this way you are removing non necessary data and you can free more storage space for future cases.

{{< figure src="/images/Storage_page.png" alt="Disk management interface with reference to the area of the screen and the information displayed" title="Disk management interface with reference to the area of the screen and the information displayed" class="figure-50">}}


## CONSELF STEP BY STEP

CONSELF guides you through the simulation literally step by step; in fact, in order to complete a simulation, the user has to go through several steps, each of which fulfills a precise task. Given the high flexibility of this method, users, less experienced as well, may take advantage of this philosophy of work: they have the ability to control the process, start over or modify what had previously been done. When a CASE is opened, a STEP interface is accessed, as shown in the picture below.

{{< figure src="/images/General_STEP_page.png" alt="General STEP page" class="figure-50" >}}

The application is generally divided into two sides:

- *Left side*: current step options to be defined by the user
- *Right side*: view of the simulation results up to the current step

A fundamental part of the application is given by the *Steps completed* button, which gives access to a detailed summary table of the performed steps within the current case. After clicking this button a new windows pops-up with one row for every step submitted in the current case.

{{< figure src="/images/SimulationStep.png" alt="Summary table of all the performed steps within a single case." class="figure-80" >}}

The data available for each step are:

- *Step Type*: type of the performed step
- *Operations*: a set of functionalities to interact with the current step
	- *View settings*: opens the settings used
	- *Reload settings*: reload the settings defined in the current step in a new one. This option is only available if we are now in a new step with the same tipe as the one we want to reload.
	- *Initialize CFD*: initialize a new CFD step from the results of a previous one. This option is only available if we are now in a new CFD step.
	- *View problems*: in case of *ERROR* or *WARNING*, it opens a new pop-up window where the user can visualize where the problem was.
- *Step name*: name assigned to the current step. To edit the name double click this field.
- *Result code*: result code obtained after the execution is completed. It can be one among
	- *SUCCESS*
	- *ERROR*
	- *WARNING*
- *Result message*: communication and suggestion of action to take in case of *ERROR* or *WARNING*.

To discover the resolution of the most common error experienced when using CONSELF web-application check the [error page]({{< ref "common-errors.md" >}}).
