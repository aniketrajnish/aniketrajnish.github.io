## Polygon Collider Optimizer

<table class="custom-table">
  <tr>
    <td><a href="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/62a658c3-487c-4d80-b303-b96a74804a99" data-lightbox="polygon-collider-optimizer" data-title="">
    <img src="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/62a658c3-487c-4d80-b303-b96a74804a99" alt="Original Sprite">
    </a>
    </td>
    <td><img src="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/cc114920-5bcd-4f06-81ad-9df9a176055d" alt="Unity Polygon Collider"></td>
    <td><img src="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/dfd8c63e-11ed-4a74-a2e1-45e2829f017e" alt="Optimized Polygon Collider"></td>
  </tr>
  <tr>
    <td style="text-align:center;">Original Sprite</td>
    <td style="text-align:center;">Unity Polygon Collider</td>
    <td style="text-align:center;">Optimized Polygon Collider</td>
  </tr>
  <tr>
    <td style="text-align:center;"><strong>Path Count</strong></td>
    <td style="text-align:center;"><em>213 paths</em></td>
    <td style="text-align:center;"><em>23 paths</em></td>
  </tr>
</table>

The tool uses a [C# implementation](https://www.codeproject.com/Articles/18936/A-C-Implementation-of-Douglas-Peucker-Line-Appro) of the Ramer Douglas Peucker Algorithm to smooth the polylines and reduce the number of paths created by a Polygon Collider in Unity.

## Usage
* Download the `collideroptimizationpackage_2d_v004.unitypackage` package from the [Releases](https://github.com/aniketrajnish/Unity-Collider-Optimizer/releases/).
* Import all the assets from the package in your unity project.
* Attach the `PolygonColliderOptimizer.cs` script on your 2D sprite.
* Adjust the `optimizationFactor` to control the amount of optimzation you need. 
* Run the performance comparision test on your machine by cloning the project & going to the `Polygon Collider Optimization Test` scene in Unity.

## Mesh Collider Optimizer 

<table class="custom-table">
  <tr>
    <td><img src="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/e23b8db9-c301-41b1-8ef0-31b2216057d6" alt="Original Mesh"></td>
    <td><img src="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/7a88b61c-2c35-40df-a181-23e7d0d7c05c" alt="Unity Mesh Collider"></td>
    <td><img src="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/06a5fb01-3c08-4a1c-bb82-2b30a534693e" alt="Optimized Mesh Collider"></td>
  </tr>
  <tr>
    <td style="text-align:center;">Original Mesh</td>
    <td style="text-align:center;">Unity Mesh Collider</td>
    <td style="text-align:center;">Optimized Mesh Collider</td>
  </tr>
  <tr>
    <td style="text-align:center;"><strong>Triangles Count</strong></td>
    <td style="text-align:center;"><em>9132 tris</em></td>
    <td style="text-align:center;"><em>2416 tris</em></td>
  </tr>
</table>

The tool uses the [Computational Geometry Unity Library](https://github.com/Habrador/Computational-geometry) by Erik Nordeus 🐐 to perfrom the Quadric Error Metric simplification on the shared mesh of the mesh collider.

#### Usage
* Download the `collideroptimizationpackage_3d_v004.unitypackage` package from the [Releases](https://github.com/aniketrajnish/Unity-Collider-Optimizer/releases/).
* Import all the assets from the package in your unity project.
* Attach the `MeshColliderOptimizer.cs` script on your 2D sprite.
* Choose the connecting mode between _Fast, Precise, and No._
* Adjust the `optimizationFactor` to control the amount of optimzation you need.
* Choose the mesh style to be _Soft, Hard or both_.
* **Warning:** Choosing the "Fast" mode would likely lead to errors, Precise mode is recommended for most of the meshes.
* Run the performance comparision test on your machine by cloning the project & going to the `Mesh Collider Optimization Test` scene in Unity.

## Updates
* Added the functionality to save and load the optimized colliders as assets.
* Fixed the refresh bug.
<center>
<video autoplay loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
  <source src="https://github.com/aniketrajnish/Unity-Collider-Optimizer/assets/58925008/ba42c61c-4ea1-419d-bf81-324304a218b8" type="video/mp4">
</video>
</center>

## Contribution
Contributions to the project are welcome. Currently working on converting the QEM algorithm to a couroutine to stop the main Unity thread from freezing.
<br>
<br>

## Known Bugs
* ~~If a prefab is made out of a gameobject having Polygon Collider Optimizer, it keeps refreshing itself.~~ **[FIXED]**
* Choosing Hard Edge Mesh Style decreases the number of triangles but induces additional vertices (doesn't affect the performance).