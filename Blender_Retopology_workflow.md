# Blender Retopology Workflow - [source video](https://www.youtube.com/watch?v=X2GNyEUvpD4)
## Initial Setup
### For a cleaner viewport, turn off several UI components:

![](/BlenderRetopologyWorkflow/Retopo_Blender_Interface_Setup01.png)

### F4 > preferences > Add-ons
#### Turn on Mesh: Bsurfaces GPL Edition

![](/BlenderRetopologyWorkflow/BlenderRetopoAdd-onBsurfaces.jpg)

#### Enable Mesh: F2

![](/BlenderRetopologyWorkflow/BlenderRetopoAdd-onF2.jpg)

#### Enable Mesh: LoopTools

![](/BlenderRetopologyWorkflow/BlenderRetopoAdd-onLoopTools.jpg)

#### With Retopo target object (High-Res) selected, Press N to open sidebar Edit > Bsurfaces > Initialize (Add BSurface mesh)

![](/BlenderRetopologyWorkflow/BlenderRetopoAdd-onBsurfacesInitialize.jpg)

#### This will Automatically:
* create an empty object (BSurfaceMesh)
* Add ShrinkWrap modifier
* Annotate enabled
* Snap to surface - Faces

#### Now you can start drawing strokes for new topology

![](/BlenderRetopologyWorkflow/BlenderRetopoAnnotateAddSurface.jpg)

#### Change surface options in the Operator Panel
![](/BlenderRetopologyWorkflow/BlenderRetopoAnnotateAddSurfaceOptions.jpg)

#### For easier visibility enable In Front (always draws above target mesh)
![](/BlenderRetopologyWorkflow/BlenderRetopoAnnotateAddSurfaceInFront.jpg)

#### Enable Add Mirror and other modifiers (for symmetrical models) Adds:
* Mirror modifier < *Keep*
* ~~Subdivision Surface modifier~~ < *Remove*
* ~~Solidify Modifier~~ < *Remove*

![](/BlenderRetopologyWorkflow/BlenderRetopoAnnotateAddMirrorandothermodifiers.jpg)

#### Edit mode functionality now works and sticks to the surface.
If far side of the mirrored geometry gets too noisy:
* Shading > Options > Backface Culling
![](/BlenderRetopologyWorkflow/BlenderRetopoBackfaceCulling.jpg)
* Disable Mirror Modifier display in the modifier panel

To make the Shrinkwrap modifier work better change the Method to Project and enable Negative
![](/BlenderRetopologyWorkflow/BlenderRetopoShrinkwrapMethod.jpg)

## BSurface Retopo options
### Methods to add geometry:
1. Make sure everything is deselected by pressing Alt + A
	* Hold down D to temporarily enable annotate tool
	* start drawing more strokes for geometry sections 
	* press Add Surface button
2. Edit Mode > Edges
	* Select an Edge
	* Draw strokes for new geometry that will connect to selected edge
	* press Add Surface button
3. Standard Blender tools
	* E = Extrude
	* Select edge > Hold down Ctrl & Right-Click along mesh to extrude to the position of your mouse.	
	* Ctrl + R = add new loops
	* Remove loops > Select loop > Ctrl + X = dissolve them
	* GG = slide edges or vertices

#### Useful tips:
* Draw strokes in the same direction or geo will flip
* Hold down D RMB click to erase strokes
	* Or Hold down Annotate tool button and select Annotate Eraser

## F2 addon
Select vertice in corner of what you want to be a new row and press F to pull it out into a new face. Can repeat action by clicking next corner vertice and pressing F again.

![](/BlenderRetopologyWorkflow/BlenderRetopoF2addnewface.jpg)

## LoopTools
N Panel > Edit > LoopTools
With a circular edge loop selected use Circle to reshape it to a perfect circle

![](/BlenderRetopologyWorkflow/BlenderRetopoLoopToolsCircle.jpg)

**Relax:** just as it says, smooths out selected points

**Space:** make edges along edge loop all have the same distance between points.

## Tips
* Periodically duplicate and apply the ShrinkWrap modifier to get rid of floating point strangeness if noticed.
	* Duplicate ShrinkWrap Modifier
	* Apply First one in the list

* Enable and disable ShrinkWrap modifier to see if there are points floating away from the surface. If so Duplicate and Apply.

* If you do things like insert loop the shrinkwrap modifier will apply the new points to the surface but only while the modifier is active. This and the Snap to Faces can fight sometimes which is why applying the modifier is helpful.

* AutoMerge is enabled by default which is useful most of the time by welding points that are close together. If it becomes a nuisance you can change the threshold or turn it off. 

![](/BlenderRetopologyWorkflow/BlenderRetopoShrinkwrapAutoMerge.jpg)

* If creating new faces on the backside somewhere and normals are flipped
	* Hover over a single vertice and press L to select island
	* Ctrl + Shift + N to flip normals
## Workflow
Start by defining important features with patches of loops - keeping the resolution low.

![](/BlenderRetopologyWorkflow/BlenderRetopoWorkflow01.jpg)

After done with first pass of retopology you can clean up with Sculpt Mode > Slide Relax tool (turn strength down)

![](/BlenderRetopologyWorkflow/BlenderRetopoSculptRelax.jpg)

[README](README.md)













