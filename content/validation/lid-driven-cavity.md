---
title: Lid Driven Cavity
toc: true
weight: 2
---

## GEOMETRY

Input file from File:LidDriven.stp

### File data

* In *File units* select *Millimeters*
* In *Grouping Criteria STEP* select *By Curve Entity*

### Domain

* In *Flow Type* select *Internal*

## MESH2D

### Surface mesh

Complete this section by filling the input data according to the following table

|Boundary name|Uniformity level [%]|Max element size [m]|
|-------------|--------------------|--------------------|
|BC-Parte1FACE1|70|0.04|
|BC-Parte1FACE2|70|0.04|
|BC-Parte1FACE3|70|0.04|
|BC-Parte1FACE4|70|0.04|
|BC-Parte1FACE5|70|0.04|
|BC-Parte1FACE6|70|0.04|

## MESH3D

### Volume mesh

* In *Meshing algorithm* select *Hexahedral*
* Mesh size
	* Max element size [m]: *0.01*

### Boundary treatment

Complete this section by filling the input data according to the following table

|Boundary name|Layers Number|First cell height [m]|
|-------------|-------------|---------------------|
|BC-Parte1FACE1|0|1|
|BC-Parte1FACE2|0|1|
|BC-Parte1FACE3|0|1|
|BC-Parte1FACE4|0|1|
|BC-Parte1FACE5|0|1|
|BC-Parte1FACE6|0|1|

## CFD

### Fluid models

* In *Density model* select *Incompressible*
* In *Flow viscosity* select *Laminar*
* Fluid properties
	* rho [kg/m^3]: *1*
* Fluid initialization
	* Pressure [Pa]: *0*
	* Velocity X [m/s]: *0*
	* Velocity Y [m/s]: *0*
	* Velocity Z [m/s]: *0*
* Viscosity properties
	* Dynamic viscosity [kg/(m s)]: *0.01*

### Boundary conditions

Complete this section by filling the input data according to the following table

|Boundary name|bctypeA|P [Pa]|bctype|Vx [m/s]|bctype|Vy [m/s]|bctype|Vz [m/s]|
|-------------|-------|------|------|--------|------|--------|------|--------|
|BC-Parte1FACE1|Gradient|0|Value|0|Value|0|Value|0|
|BC-Parte1FACE2|Gradient|0|Value|0|Value|0|Value|0|
|BC-Parte1FACE3|Gradient|0|Value|0|Value|0|Value|0|
|BC-Parte1FACE4|Gradient|0|Value|1|Value|0|Value|0|
|BC-Parte1FACE5|Gradient|0|Gradient|0|Gradient|0|Gradient|0|
|BC-Parte1FACE6|Gradient|0|Gradient|0|Gradient|0|Gradient|0|

### Simulation settings

* In *Time evolution* select *Steady*
* Iteration number
	* Number Iteration: *5000*
* Output Frequency
	Save solution every [iterations]: *50*

## RESULTS

{{< figure src="/conself-docs/images/800px-VELOCITY-STREAMLINES_LID_CAVITY.png" alt="Velocity-Magnitude Lid Cavity" title="Velocity-Magnitude Lid Cavity" >}}

{{< figure src="/conself-docs/images/500px-Comparison_LID_DRIVEN.png" alt="Comparison Lid Driven" title="Comparison Lid Driven" >}}