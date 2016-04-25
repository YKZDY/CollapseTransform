# Collapse-Transform

> 效果演示：https://vimeo.com/164052429

Overview:
-----

    该节点通过破碎输入的几何体，实现从几何体A到几何体B的变形。

    Collapse Transform会获取两个初始的输入对象：原始几何体A和目标几何体B。通过调节Percent参数，可以得到变形过程中任一时期的运动形态。第三输入端提供了一个可自定义的过度状态。

Tips:
-----

    几何体A和几何体B应有足够的重叠部分，来保证变形过程中可以得到平滑的运动过程。

    默认状态下接近几何体表面的碎块不能被完美的分割为方体。如需让几何体能尽可能的被破碎为方体，应提高Sample Offset的数值。但这同时会导致这部分碎块不能得到正确的运动状态，此时需启用Direction Constraint对碎块的运动进行约束。

Input:
-----

    Model A：原始几何体

    Model B：目标几何体

    Intermediate Bounding：一个可选的边界框几何体

Parameters:
-----

###Generate:

    Separation：破碎精度
	
    Seed：对于不同的随机种子值，会生成不同的变形过程。
	
    Direction Constraint：开启运动方向约束。
	
    Constraint Intensity：约束强度，用来修正表面碎块的运动状态。调高此值会导致运算速度变慢。绝大多数情况下，此值不应大于0.5，否则可能导致运算陷入死循环。
	
    Intermediate Type：
	
        From A：由原始几何体生成过度状态。
		
        From B：由目标几何体生成过度状态。
		
        Bounding Object：由第三输入端得到过渡状态。
		
    Intermediate Offset：当选择原始或目标几何体生成过渡状态时，这个参数用来给定一个偏移值来收缩几何体表面。
	
    Surface A Group：包含原始几何体表面的组名称。
	
    Intermediate Group：包含内部面的组名称。
	
    Surface B Group：包含目标几何体表面的组名称。
    
    Create Intermediate uv：为内部面生成uv。

    Pack Geometry：把每一个碎块打包到一个内嵌的packed primitive对象中。

###Action:

    Percent：变形进度的百分比。0代表原始几何体，1代表目标几何体。
	
    Duration：每个小方块从开始运动到消失所经历的时长。此参数是一个经验值。较高的值会导致大量小方块同时运动。较低的值更能体现出运动的次序，但会导致单个小方体运动速度过快。
	
###Sample:

    Sample A Offset：偏移原始几何体的破碎采样。
	
    Sample B Offset：偏移目标几何体的破碎采样。
	
    Constraint A Depth：将约束扩展到原始几何体内部，会使变形的状态更为平均，不恰当的提高此值会导致计算陷入死循环。
	
    Constraint B Depth：将约束扩展到目标几何体内部，会使变形的状态更为平均，不恰当的提高此值会导致计算陷入死循环。
	
> Author：Calven Gu

> E-mail：cz069069@outlook.com
