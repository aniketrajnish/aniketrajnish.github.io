## [Matrix Calculator](https://makra.wtf/Matrix-Visualizer/) 
* A visusal matrix calculator that helps showcase the following concepts:
    * Basic operations like addition, subtraction, scalar & matrix multiplication, transpose, and inverse on matrices.
    * 3D transformations like scaling, rotation, and translation.
    * World Spcae Transformation, Object Space Transformation, Camera View Matrix, Projection Matrices and Model View Matrix.

* The calculator is built on top of my C# Matrix Library whose source code can be found [here](https://github.com/aniketrajnish/Matrix-Visualizer/tree/main/src/Matrix%20Visualizer/Assets/Scripts/Matrix).
* The GUI is developed using Unity3D and is deployed using WebGL and GitHub Pages. The source code for the whole project can be found [here](https://github.com/aniketrajnish/Matrix-Visualizer).

## [Triangle/Trigonometry Visual Calculator](https://github.com/aniketrajnish/Triangle-Calculator-PyQt)
* A triangle calculator that calculates the sides and angles of a triangle using:
    * SOH-CAH-TOA
    * Law of Sines, Law of Cosines
* The calculator is built on top of my python trigonometry library whose source code can be found [here](https://github.com/aniketrajnish/Triangle-Calculator-PyQt/blob/main/src/trig.py).
* It is built using PyQt5 and the packed executable can be found in the [Releases Section](https://github.com/aniketrajnish/Triangle-Calculator-PyQt/releases/tag/v001) of the repository.
* The triangles are visualized using the `QGraphicsView` and `QGraphicsScene` classes of PyQt5.

## [Quaternion Python Library](https://github.com/aniketrajnish/Quaternion-Calculator-PyQt/blob/main/src/quaternion.py)
* A python library that helps in performing quaternion operations like:
    * Addition, Subtraction, Scalar & Quaternion Multiplication
    * Conjugate, Inverse, Normalization, Negation, Angle-Axis Representation
    * Slerp, Point Transformation
* I plan to create a visual calculator for the same using PyQt5 similar to the Triangle Calculator.

## [C# Shader Math Library](https://github.com/aniketrajnish/4D-Engine-Unity/blob/main/4D%20Engine%20Unity/Assets/Scripts/Utils/Shader%20Math%20Utils/MakraMathUtils.cs)
* Gist of C# functions that adds on to the Unity.Mathematics library to add additional shader math functionality to it like:
    * dot2, ndot
    * union, intersection, difference
    * Fmod, 4D Transformations

## [HLSL Signed Distance Functions](https://github.com/aniketrajnish/4D-Engine-Unity/blob/main/4D%20Engine%20Unity/Assets/Shaders/Raymarcher/Include/DFs.cginc)
* Collection of HLSL definions of Signed Distance Functions representing various 4D implementation of shapes like:
    * Sphere, Torus, Capped Torus, Link, Plane, Cone, Infinite Cone, Hexagonal Prism, Triangular Prism, Capsule, Infinite Cylinder, Box, Rounded Box, Rounded Cylinder, Capped Cone
    * Box Frame, Solid Angle, Cut Sphere, Cut Hollow Sphere, Death Star, Round Cone, Ellipsoid, Rhombus, Octahedron, Pyramid, Quad, Triangle, Fractal
    * Tesseract, HyperSphere, DuoCylinder, Five-Cell, Sixteen-Cell
* Collection of SDFs for regular 3D shapes can also be found [here](https://github.com/aniketrajnish/Raymarching-Engine-Unity/blob/main/Assets/Shaders/Raymarcher/Include/DFs.cginc)

## [C# 4D Signed Distance Functions](https://github.com/aniketrajnish/4D-Engine-Unity/blob/main/4D%20Engine%20Unity/Assets/Scripts/Raymarching%20Engine/DFs.cs)
* Collection of C# analogs of the HLSL Signed Distance Functions for 4D shapes.
* These are just limited to the 4D shapes, will expand to regurlar 3D shapes soon.