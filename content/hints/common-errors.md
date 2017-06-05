---
title: Common Errors
toc: true
weight: 3
---

After each STEPS has been performed, it is possible to check its results by clicking on the steps summary button. This will report a summary table where RED items are problematic steps. For each problem an error message, with a brief description and suggested action is reported. For the sake of clarity, we report a more detailed description of the problem and the suggested solution to make even easier to our customers the web-application.
 
{{< figure src="/images/STEPS_completed.png" alt="STEPS completed" class="figure-80" >}}

## Common GEOMETRY errors

<table>
	<tbody>
		<tr>
			<th>Error message</th>
			<th>Step</th>
			<th>Fix</th>
		</tr>
		<tr>
			<td>
				<strong>Open surfaces in internal flow are not allowed (Define an external flow for this type of geometry)</strong>
			</td>
			<td>
				GEOMETRY
			</td>
			<td>Open surfaces must always be contained within a closed fluid volume. For this reason every time one is detected we must assure we are in an external flow type before proceeding.</td>
		</tr>
	</tbody>
</table>

## Common MESH errors

<table>
	<tbody>
		<tr>
			<th>Error message</th>
			<th>Step</th>
			<th>Fix</th>
		</tr>
		<tr>
			<td>
				<strong>Mesh too coarse (Use smaller mesh sizes to increase refinement)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>The refinement levels chosen returns a mesh division too coarse. This, beside giving problem in CFD/FEM analysis, is unacceptable. Generate a new mesh with higher refinement in all surfaces.</td>
		</tr>
		<tr>
			<td>
				<strong>Stop Tetrahedral meshing since surface mesh is overlapping. (If possible use Hexahedral meshing)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>Overlapping surfaces in input geometry file. Remember to simplify them as explained in <a href="http://docs.conself.com/hints/input-cad-files/">Input CAD Files</a>. For IGES files, try also the <i>STEP / IGES file healing</i> to sew faces into a single solid.</td>
		</tr>
		<tr>
			<td>
				<strong>Error in STL surface meshing (Check for STL consistency)</strong>
				<hr>
				<strong>STL/OBJ file corrupted (Use STEP files for better geometry representation and portability)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>
				Irregular STL/OBJ file uploaded. This may be due to non watertight models, very elongated triangles, etc. Try exporting a STEP or IGES file if possible.
				<figure><img src="/images/Stl2_720.png"><figcaption><h4>If triangles overlap, the definition of a unique volume is not possible. In such a case try using HEXAHEDRAL mesh if possible.</h4></figcaption></figure>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Meshing phase failure: high aspect ratio face (check your input geometry file at location: x = xxxxxx y = yyyyyy z = zzzzzz)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>A face with a high aspect ration (very long triangle) has been detected. This type of shapes, beside resulting difficult to mesh, may lead to problematic elements shapes. It is recommended to check with your preferred CAD software the faces near to the location given in the error message.</td>
		</tr>
		<tr>
			<td>
				<strong>Meshing failed on boundary(ies): <i>BC names</i> (Try STEP/IGES Cleaning Tool with tolerance X.XXX and check geometry at [x,y,z] = X.XX, Y.YY, Z.ZZ)</strong>
				<hr>
				<strong>Wall meshing failed (Use a smaller mesh size or try STEP/IGES Fix Tool with tolerance X.XXX and check geometry at [x,y,z] = X.XX, Y.YY, Z.ZZ)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>Meshing algorithm fails because of troubles with a certain surface. CONSELF provides a STEP/IGES cleaning tool which allows to try and fix the STEP file. It is recommended to use it with the tolerance given in the error message before proceeding any further.</td>
		</tr>
		<tr>
			<td>
				<strong>BL Extension needs to be reduced too much to avoid surface mesh overlap (Increase surface mesh refinement or deactivate boundary layer)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>
				Surface mesh triangles are overlapping and this cause a failure. In order to solve this problem you have three possibilities:
				<ul>
					<li>Try a new mesh without boundary layer (CFD only)</li>
					<li>Use an HEXA mesh with or without boundary layer (CFD only)</li>
					<li>Check your input file for solid compenetration</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Open cells found in the mesh. (Use smaller mesh sizes to increase refinement)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>The current refinement used is too coarse to represent the geometry file. This generates open cells and others meshing failures. In order to fix it generate a new mesh with a higher refinement (i.e. reduce the surface element dimension).</td>
		</tr>
		<tr>
			<td>
				<strong>Meshing out of memory (reduce wall refinement)</strong>
				<hr>
				<strong>Failure in HEXA cut cells creation: out of memory (reduce wall refinement)</strong>
				<hr>
				<strong>Failure in preparing HEXA mesh (contact support@conself.com)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>The current setup in meshing results into a very large number of elements. This requires more RAM than currently installed on the machine. Either reduce the number of elements in current mesh or choose a plan that gives you access to machines with more RAM available.</td>
		</tr>
		<tr>
			<td>
				<strong>Stop Tetrahedral meshing since surface mesh is not consistent. (If possible use Hexahedral meshing)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>
				Another problem related with surface meshing. In general this is due to incorrect input geometry file (i.e. problem with surfaces). Solution to this problem are multiple:
				<ul>
					<li>Try using hexahedral mesh if possible</li>
					<li>Define different refinement on surfaces</li>
					<li>Trying running the Step healing tool</li>
					<li>Modify your geometry file</li>
				</ul>
			</td>
		</tr>
		<tr>
			<td>
				<strong>Tetrahedral volume meshing failed (If possible use Hexahedral meshing or increase surface refinement by reducing <strong>mesh size</strong> parameter)</strong>
			</td>
			<td>
				MESH
			</td>
			<td>If refinement levels are highly different between surfaces (difference &gt; 10^2) this error may occur. Use a more uniform elements dimension in all surfaces.</td>
		</tr>
	</tbody>
</table>

## Common CFD errors

<table>
	<tbody>
		<tr>
			<th>Error message</th>
			<th>Step</th>
			<th>Fix</th>
		</tr>
		<tr>
			<td>
				<strong>Maximum number of iterations exceeded after $iter iterations (check your mesh quality and increase its refinement)</strong>
				<hr>
				<strong>Floating point exception after XX iterations (check your mesh quality and increase its refinement)</strong>
			</td>
			<td>
				CFD
			</td>
			<td>Poor mesh quality or wrong boundary condition lead to a diverging simulation. Check the mesh quality and in case use a different level of refinement to get a better mesh quality. More <strong>information about</strong> mesh quality is available in <strong><a rel="nofollow" class="external text" href="https://conself.com/blog/4-mesh-issues-poor-accuracy/">this</a> blog post</strong> and <strong><a rel="nofollow" class="external text" href="https://conself.com/blog/what-is-boundary-layer-and-how-can-you-handle-it/">this</a></strong></td>
		</tr>
		<tr>
			<td>
				<strong>No OUTLET BC detected (insert one OUTLET boundary condition in a new CFD step)</strong>
			</td>
			<td>
				CFD
			</td>
			<td>Since we must <strong>specify pressure in at least one surface</strong>, CONSELF forces the definition of an outlet boundary condition. Create a new CFD step and define at least one surface as OUTLET.</td>
		</tr>
	</tbody>
</table>

## Common MECH errors

<table>
	<tbody>
		<tr>
			<th>Error message</th>
			<th>Step</th>
			<th>Fix</th>
		</tr>
		<tr>
			<td>
				<strong>Singular matrix detected (insert one CONSTRAINED boundary condition in a new MECH step)</strong>
			</td>
			<td>
				MECH
			</td>
			<td>In static analysis we must guarantee our <strong>part to be at least isostatic</strong>. Make sure you are using at least one CONSTRAINT - FIXED boundary.</td>
		</tr>
		<tr>
			<td>
				<strong>Singular matrix detected (Use CONSTAINT-FREE boundary in "bc_name" in a new MECH step)</strong>
			</td>
			<td>
				MECH
			</td>
			<td>You are not limiting any degree of freedom in a CONSTRAINT - FIXED boundary. Make sure you re-run a new MECH step with a CONSTRAINT - FREE in that particular boundary.</td>
		</tr>
		<tr>
			<td>
				<strong>Singular matrix detected (make sure you avoid movement in X, Y and Z directions with constraint boundaries)</strong>
			</td>
			<td>
				MECH
			</td>
			<td>One of the degree of freedom (translations in X, Y and Z directions) is not limited with the current configuration.</td>
		</tr>
	</tbody>
</table>

## Common TOOLS errors

<table>
	<tbody>
		<tr>
			<th>Error message</th>
			<th>Tool</th>
			<th>Fix</th>
		</tr>
		<tr>
			<td>
				<strong>Wrong data in CSV format.(Use one line for every point with x_coo,y_coo,z_coo for example: 0.3,0.4,1.2 )</strong>
			</td>
			<td>
				PointsToTria
			</td>
			<td>
				Error in input file definition for this particular tool. Every input CSV file has to be made by three columns as follows:
				<ul>
					<li>coor_x_1,coor_y_1,coor_z_1</li>
					<li>coor_x_2,coor_y_2,coor_z_2</li>
					<li>coor_x_3,coor_y_3,coor_z_3</li>
					<li>...</li>
				</ul>
			</td>
		</tr>
	</tbody>
</table>
