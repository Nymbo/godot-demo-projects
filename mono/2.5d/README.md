# 2.5D Demo Project with C#

This demo project shows a way to create a 2.5D game
in Godot by mixing 2D and 3D nodes. It also adds a
2.5D editor viewport for easily editing 2.5D levels.

Language: [C#](https://docs.godotengine.org/en/latest/tutorials/scripting/c_sharp/index.html) and a little bit of GDScript

Renderer: Compatibility

Note: There is a GDScript version available [here](https://github.com/godotengine/godot-demo-projects/tree/master/misc/2.5d).

## How does it work?

Custom node types are added in a Godot plugin to allow 2.5D objects. Node25D serves as the base for all 2.5D objects. Its first child must be a 3D Spatial, which is used to calculate its position. Then, add a 2D Sprite (or similar) to display the object.

Inside of Node25D, new structs called Basis25D and Transform25D are used to calculate the 2D position from the 3D position. For getting a 3D position, this project uses KinematicBody and StaticBody (3D), but these only exist for math - the camera is 2D and all sprites are 2D. You are able to use any Spatial node for math.

Several view modes are implemented, including top down, front side, 45 degree, isometric, and two oblique modes. To implement a different view angle, all you need to do is create a new Basis25D, use it in all your Node25D transforms, and of course create sprites to display that object in 2D.

The plugin also adds YSort25D to sort Node25D nodes, and ShadowMath25D for calculating a shadow (a simple KinematicBody that tries to cast downward).

## Screenshots

![Forty Five Degrees](../../misc/2.5d/screenshots/forty_five.png)

![Isometric](../../misc/2.5d/screenshots/isometric.png)

![Oblique Z](../../misc/2.5d/screenshots/oblique_z.png)

![Oblique Y](../../misc/2.5d/screenshots/oblique_y.png)

![Front Side](../../misc/2.5d/screenshots/front_side.png)

![Cube](../../misc/2.5d/screenshots/cube.png)

![2.5D Editor Viewport](../../misc/2.5d/screenshots/editor.png)

## Music License

`assets/mr_mrs_robot.ogg` Copyright &copy; circa 2008 Juan Linietsky, CC-BY: Attribution.
