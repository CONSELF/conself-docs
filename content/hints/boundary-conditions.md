---
title: Boundary Conditions
toc: true
weight: 2
---

The table below report an overview of available boundary conditions and specifications. The description specifies the application and the restriction of the boundary conditions.
 
{{% notice info %}}
Boundary availability depends on the application you are currently using.
{{% /notice %}}

<table>
	<tbody>
		<tr>
			<th>Boundary</th>
			<th>Description</th>
		</tr>
		<tr>
			<td>
				INLET - Absolute velocity
			</td>
			<td>
				Inlet velocity - Velocity vector is specified in an absolute reference frame
				<hr>
				<ul>
					<li>Uabsx [m/s] - Absolute velocity X</li>
					<li>Uabsy [m/s] - Absolute velocity Y</li>
					<li>Uabsz [m/s] - Absolute velocity Z</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Cylindrical velocity
			</td>
			<td>
				Inlet velocity in a cylindrical reference frame
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
			</td>
		</tr>
		<tr>
			<td>
				INLET - Relative velocity
			</td>
			<td>
				Inlet velocity - Velocity vector is specified in a relative reference frame
				<hr>
				<ul>
					<li>Urelx [m/s] - Relative velocity X</li>
					<li>Urely [m/s] - Relative velocity Y</li>
					<li>Urelz [m/s] - Relative velocity Z</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Total pressure
			</td>
			<td>
				Total pressure inlet condition - valid also for outlet condition
				<hr>
				<ul>
					<li>p₀ [Pa] - Total Pressure</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Velocity
			</td>
			<td>
				Inlet velocity - Velocity vector normal to the surface (use negative value for outflow)
				<hr>
				<ul>
					<li>U [m/s] - Velocity</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
					<li>Φ [%] - Fluid-A concentration</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Velocity and particles
			</td>
			<td>
				Inlet velocity with specified inlet particles
				<hr>
				<ul>
					<li>U [m/s] - Fluid velocity</li>
					<li>Uxp [m/s] - Particles velocity X</li>
					<li>Uyp [m/s] - Particles velocity Y</li>
					<li>Uzp [m/s] - Particles velocity Z</li>
					<li>Mp [kg/s] - Particles mass flow</li>
					<li>Dp [m] - Particles dimension</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Velocity fixed temperature
			</td>
			<td>
				Inlet velocity with specified temperature - Velocity vector normal to the surface
				<hr>
				<ul>
					<li>U [m/s] - Velocity</li>
					<li>T [K] - Temperature</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Velocity vector
			</td>
			<td>
				Inlet velocity where the user specifies the velocity vector
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
					<li>Φ [%] - Fluid-A concentration</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Velocity vector fixed temperature
			</td>
			<td>
				Inlet velocity where the user specifies the velocity vector and the temperature
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>T [K] - Temperature</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				INLET - Volume flow
			</td>
			<td>
				Inlet condition with prescribed volume flow (use negative value for outflow)
				<hr>
				<ul>
					<li>Q [m³/s] - Volume flow</li>
					<li>Dₕ [m] - Hydraulic diameter</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				OUTLET - Pressure
			</td>
			<td>
				Outlet condition for pressure - Backscatter flow is denied
				<hr>
				<ul>
					<li>p [Pa] - Pressure</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - Adiabatic no slip
			</td>
			<td>
				No slip adiabatic wall
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - Fire fixed temperature
			</td>
			<td>
				No slip wall with prescribed temperature
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>CO [kg/(s·m²)] - CO production</li>
					<li>T [K] - Temperature</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - Fire heat flux
			</td>
			<td>
				No slip wall with imposed temperature gradient
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>CO [kg/(s·m²)] - CO production</li>
					<li>T [K/m] - Temperature gradient</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - Fire location
			</td>
			<td>
				No slip wall with imposed temperature gradient
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>CO [kg/(s·m²)] - CO production</li>
					<li>q [W/m²] - Heat flux</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - No slip
			</td>
			<td>
				No slip adiabatic wall
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - No slip fixed temperature
			</td>
			<td>
				No slip wall with imposed temperature
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>T [K] - Temperature</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - No slip rough wall
			</td>
			<td>
				No slip rough wall
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>Ks [m] - Sand-grain roughness height</li>
					<li>Cs - Roughness constant</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - No slip with CO production
			</td>
			<td>
				No slip wall with imposed CO production
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>CO [kg/(s·m²)] - CO production</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - No slip with heat flux
			</td>
			<td>
				No slip wall with imposed heat flux per surface unit
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>q [W/m²] - Heat flux</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - No slip with heat power
			</td>
			<td>
				No slip wall with imposed global heat flux
				<hr>
				<ul>
					<li>Ux [m/s] - Velocity X</li>
					<li>Uy [m/s] - Velocity Y</li>
					<li>Uz [m/s] - Velocity Z</li>
					<li>Q [W] - Heat power</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - Rotating
			</td>
			<td>
				Rotating adiabatic wall
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
			</td>
		</tr>
		<tr>
			<td>
				WALL - Rotating no slip
			</td>
			<td>
				Rotating adiabatic wall
				<hr>
				<ul>
					<li>ω [rpm] - Relative rotational speed</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				WALL - Rotating no slip rough wall
			</td>
			<td>
				No slip rotating rough wall
				<hr>
				<ul>
					<li>ω [rpm] - Relative rotational speed</li>
					<li>Ks [m] - Sand-grain roughness height</li>
					<li>Cs - Roughness constant</li>
				</ul>
			</td>
		</tr>
	</tbody>
</table>