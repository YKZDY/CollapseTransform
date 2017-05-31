# Collapse-Transform

> Showreel：https://vimeo.com/164052429

Overview:
-----

    This asset can deform the first input geometry to the second one by collapse it into small boxes. By changing the 'Percent' parameter, you can get any transitional state of this deforming.

Tips:
-----

    There must be plenty overlap of two input geometrys.
    
    By default, the geometry's surface cannot be splited into ideal cubes. Turning up the 'Sample Offset' parameter can allow it to be closer to the perfect cubes. If you find some animation problems after you change this parameter, please try to turn up 'Direction Constraint' as well.

Input:
-----

    Model A：Original geometry

    Model B：Target geometry
    
    Intermediate Bounding：An optional bounding box geometry

Parameters:
-----

### Generate:

    Separation：The smallest distance between any two of the generated boxes.
	
    Seed：The random number seed used to generate the process of deforming.
	
    Direction Constraint：Enable direction constraint.
	
    Constraint Intensity：Used to correct the animation process. It should always small than 0.5, otherwise it will make the program into an endless loop.
	
    Intermediate Type：
	
        From A：Generate the intermediate state by first input geometry.
        From B：Generate the intermediate state by second input geometry.
        Bounding Object：Generate the intermediate state by the third input bounding box geometry.
		
    Intermediate Offset：When you use the first or the second geometry to generate the intermediate state, you can use this parameter to offset the original geometry surface.
	
    Surface A Group：The group containing any primitives in the first input.
	
    Intermediate Group：The group containing any primitives in the interior surfaces.
	
    Surface B Group：The group containing any primitives in the second input.
    
    Create Intermediate uv：Generate uv attribute for intermediate primitives.

    Pack Geometry：Pack every single box into a packed geometry.

### Action:

    Percent：The transform progress, zero representative the original geometry, one representative the target geometry.
	
    Duration：The lifetime of each temporary box.
	
### Sample:

    Sample A Offset：Offset of the sample for fracture the original geometry.
	
    Sample B Offset：Offset of the sample for fracture the target geometry.
	
    Constraint A Depth：Constraint the animation of the internal boxes, turning up this parameter might lead to an endless loop.
	
    Constraint B Depth：Constraint the animation of the internal boxes, turning up this parameter might lead to an endless loop.
	
> Author：Calven Gu

> E-mail：cz069069@outlook.com
