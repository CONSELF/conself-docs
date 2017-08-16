---
title: CFD boundary Conditions
toc: true
weight: 2
---

For your CFD simulation CONSELF provides a very high number of different settings. In general the boundary available are grouped in few types:

* **INLET** -> flow inlet into the system
* **OUTLET** -> flow outlet
* **IN/OUT** -> boundaries that can define both an inlet or outlet (surface normal vectors are positive if inlet, negative when outlet)
* **WALL** -> solid walls of the system

Starting from this raw classification, each boundary is specialized and gives a number of feature to the user to reproduce reality as accurately as possible. Remember that some of these boundary conditions are available according to the application you are using and also to the [fluid model]({{< ref "cfd.md#fluid-models" >}}) chosen.

Once you select the appropriate boundary for your models, a certain number of inputs are required, such as pressure values, velocities, temperatures, etc. Using this page you can have a complete list of all these options with hints to choose correct values.
 
{{% notice info %}}
WALL boundaries highly affect the quality of your simulation, in combination with wall refinement and the turbulence model. Guidelines about an appropriate selection are given in <a href="https://conself.com/blog/y-what-is-it-and-how-can-i-use-it">this blog post</a>.
{{% /notice %}}

<table>
	<tbody>
		<tr>
			<th>Boundary</th>
			<th>Description</th>
		</tr>

<tr>
<td><center>IN/OUT - Total pressure</center></td>
<td>Total pressure inlet and outlet condition
<hr>
<ul>
<li>p [Pa] - Total pressure</li>
<li>Φ [%] - Fluid-A volume concentration</li>
</ul>
</tr>
</td>
<tr>
<td><center>IN/OUT - Velocity</center></td>
<td>Inlet and outlet velocity - Velocity vector normal to the surface (use negative value for outflow)
<hr>
<ul>
<li>U [m/s] - Velocity</li>
<li>Dₕ [m] - Hydraulic diameter</li>
<li>s [unit/m³] - Passive scalar value</li>
</ul>
</tr>
</td>
<tr>
<td><center>IN/OUT - Velocity fixed temperature</center></td>
<td>Inlet and outlet velocity with specified temperature - Velocity vector normal to the surface
<hr>
<ul>
<li>U [m/s] - Velocity</li>
<li>T [K] - Temperature</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>IN/OUT - Velocity vector</center></td>
<td>Inlet and outlet velocity where the user specifies the velocity vector
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>Dₕ [m] - Hydraulic diameter</li>
<li>s [unit/m³] - Passive scalar value</li>
</ul>
</tr>
</td>
<tr>
<td><center>IN/OUT - Velocity vector fixed temperature</center></td>
<td>Inlet and outlet velocity where the user specifies the velocity vector and the temperature
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>T [K] - Temperature</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>IN/OUT - Volume flow</center></td>
<td>Inlet and outlet condition with prescribed volume flow (use negative value for outflow)
<hr>
<ul>
<li>Q [m³/s] - Volume flow</li>
<li>Dₕ [m] - Hydraulic diameter</li>
<li>s [unit/m³] - Passive scalar value</li>
</ul>
</tr>
</td>
<tr>
<td><center>IN/OUT - Volume flow fixed temperature</center></td>
<td>Inlet and outlet condition with prescribed volume flow and temperature (use negative value for outflow)
<hr>
<ul>
<li>Q [m³/s] - Volume flow</li>
<li>T [K] - Temperature</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>INLET - Absolute velocity</center></td>
<td>Inlet velocity - Velocity vector is specified in an absolute reference frame
<hr>
<ul>
<li>Uabsx [m/s] - Absolute velocity X</li>
<li>Uabsy [m/s] - Absolute velocity Y</li>
<li>Uabsz [m/s] - Absolute velocity Z</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>INLET - Cylindrical velocity</center></td>
<td>Inlet velocity in a cylindrical reference frame
<hr>
<ul>
<li>Centre X [m] - Centre X</li>
<li>Centre Y [m] - Centre Y</li>
<li>Centre Z [m] - Centre Z</li>
<li>Axis X - Normalized axis X</li>
<li>Axis Y - Normalized axis Y</li>
<li>Axis Z - Normalized axis Z</li>
<li>U axial [m/s] - Axial velocity</li>
<li>U radial [m/s] - Radial velocity</li>
<li>ω [rpm] - Rotational velocity</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>INLET - Relative velocity</center></td>
<td>Inlet velocity - Velocity vector is specified in a relative reference frame
<hr>
<ul>
<li>Urelx [m/s] - Relative velocity X</li>
<li>Urely [m/s] - Relative velocity Y</li>
<li>Urelz [m/s] - Relative velocity Z</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>INLET - Total pressure</center></td>
<td>Total pressure inlet condition
<hr>
<ul>
<li>pₜ [Pa] - Total Pressure</li>
<li>Dₕ [m] - Hydraulic diameter</li>
<li>s [unit/m³] - Passive scalar value</li>
</ul>
</tr>
</td>
<tr>
<td><center>INLET - Velocity</center></td>
<td>Inlet velocity - Velocity vector normal to the surface
<hr>
<ul>
<li>U [m/s] - Velocity</li>
<li>Φ [%] - Fluid-A volume concentration</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>INLET - Velocity and particles</center></td>
<td>Inlet velocity with specified inlet particles
<hr>
<ul>
<li>U [m/s] - Fluid velocity</li>
<li>Uxₚ [m/s] - Particles velocity X</li>
<li>Uyₚ [m/s] - Particles velocity Y</li>
<li>Uzₚ [m/s] - Particles velocity Z</li>
<li>Mₚ [kg] - Particles total mass</li>
<li>Dₚ [m] - Particles dimension</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>INLET - Velocity vector</center></td>
<td>Inlet velocity where the user specifies the velocity vector
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>Φ [%] - Fluid-A volume concentration</li>
<li>Dₕ [m] - Hydraulic diameter</li>
</ul>
</tr>
</td>
<tr>
<td><center>OUTLET - Pressure</center></td>
<td>Outlet condition for pressure - Backscatter flow is denied
<hr>
<ul>
<li>p [Pa] - Absolute pressure</li>
</ul>
</tr>
</td>
<tr>
<td><center>OUTLET - Velocity</center></td>
<td>Outlet velocity - Velocity vector normal to the surface
<hr>
<ul>
<li>U [m/s] - Velocity</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - Adiabatic no slip</center></td>
<td>No slip adiabatic wall
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - Fire location</center></td>
<td>No slip wall with imposed temperature gradient
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>s [unit/(s·m²)] - Passive scalar production</li>
<li>q [W/m²] - Heat flux</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - No slip</center></td>
<td>No slip adiabatic wall
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - No slip fixed temperature</center></td>
<td>No slip wall with imposed temperature
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>T [K] - Temperature</li>
<li>s [unit/(s·m²)] - Passive scalar production</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - No slip rough wall</center></td>
<td>No slip rough wall
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>Ks [m] - Sand-grain roughness height</li>
<li>Cs - Roughness constant</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - No slip with heat flux</center></td>
<td>No slip wall with imposed heat flux per surface unit
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>q [W/m²] - Heat flux</li>
<li>s [unit/(s·m²)] - Passive scalar production</li>
<li>∇T [K/m] - Temperature gradient</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - No slip with heat power</center></td>
<td>No slip wall with imposed global heat flux
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>Q [W] - Heat power</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - No slip with passive scalar production</center></td>
<td>No slip wall with imposed CO production
<hr>
<ul>
<li>Ux [m/s] - Velocity X</li>
<li>Uy [m/s] - Velocity Y</li>
<li>Uz [m/s] - Velocity Z</li>
<li>s [unit/(s·m²)] - Passive scalar production</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - Rotating</center></td>
<td>Rotating adiabatic wall
<hr>
<ul>
<li>Centre X [m] - Centre X</li>
<li>Centre Y [m] - Centre Y</li>
<li>Centre Z [m] - Centre Z</li>
<li>Axis X - Normalized axis X</li>
<li>Axis Y - Normalized axis Y</li>
<li>Axis Z - Normalized axis Z</li>
<li>ω [rpm] - Rotational velocity</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - Rotating no slip</center></td>
<td>Rotating adiabatic wall
<hr>
<ul>
<li>ω [rpm] - Relative rotational speed</li>
</ul>
</tr>
</td>
<tr>
<td><center>WALL - Rotating no slip rough wall</center></td>
<td>No slip rotating rough wall
<hr>
<ul>
<li>ω [rpm] - Relative rotational speed</li>
<li>Ks [m] - Sand-grain roughness height</li>
<li>Cs - Roughness constant</li>
</ul>
</tr>
</td>
	</tbody>
</table>
