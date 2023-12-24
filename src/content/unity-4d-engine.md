A 4D Raymarching Engine for Unity that helps render 4D objects and has the following features:
* 20+ 4D shapes to choose from.
* Control over shape's dimensions and color.
* Control over shape's 3D translation and rotation.
* Supports ambient occlusion, lighting information, hard and soft shadows.
* Control over both global and local 4D translation and rotation.

I have made a 4D pacman game using this engine. You can check it out [here](https://makra.itch.io/pacman-4d-into-the-4th-dimension).<br>
If you want to learn more about what 4D is, check out [this](https://youtu.be/6Gim95bukm8?si=ROa28v9MgNcfmv7B) video that I made using this engine as the backend.

## Usage

**Importing the Package**
* Clone the repository or download the `.unitypackage` from the [Releases Section](https://github.com/aniketrajnish/4D-Engine-Unity/releases/tag/v001) and import it in your project. <br><br>
  ```
  git clone https://github.com/aniketrajnish/4D-Engine-Unity.git
  ```
* Import the [Unity.Mathematics](https://docs.unity3d.com/Packages/com.unity.mathematics@1.0/manual/index.html) package from the package manager.
* The package includes a pre-configured `Test` scene that serves as a reference. You can use this as a starting point for your project.
* If you want to setup a new scene by yourself, simply follow the steps outlined below.
 
**Setting up a scene**
* Open a new scene and add the `Raymarcher` component to the Main Camera.
* The `Raymarcher` script has the following parameters in the inspector:
  
  <table class="custom-table">
    <tr>
      <th>Category</th>
      <th>Variable</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><strong>General Settings</strong></td>
      <td>Shader</td>
      <td>Shader used for raymarching.</td>
    </tr>
    <tr>
      <td></td>
      <td>Sun</td>
      <td>Directional light in the scene.</td>
    </tr>
    <tr>
      <td></td>
      <td>Loop</td>
      <td>Repetition of structures in the raymarching shader.</td>
    </tr>
    <tr>
      <td><strong>4D Settings</strong></td>
      <td>W Pos</td>
      <td>Global W position in 4D space.</td>
    </tr>
    <tr>
      <td></td>
      <td>W Rot</td>
      <td>Global W rotation in 4D space.</td>
    </tr>
    <tr>
      <td><strong>Light Settings</strong></td>
      <td>Is Lit</td>
      <td>Toggle lighting calculations on/off.</td>
    </tr>
    <tr>
      <td></td>
      <td>Is Shadow Hard</td>
      <td>Toggle between hard and soft shadows.</td>
    </tr>
    <tr>
      <td></td>
      <td>Is AO</td>
      <td>Enable or disable Ambient Occlusion.</td>
    </tr>
    <tr>
      <td></td>
      <td>Light Col</td>
      <td>Color of the light.</td>
    </tr>
    <tr>
      <td></td>
      <td>Light Intensity</td>
      <td>Intensity of the light.</td>
    </tr>
    <tr>
      <td></td>
      <td>Shadow Intensity</td>
      <td>Intensity of shadows.</td>
    </tr>
    <tr>
      <td></td>
      <td>Shadow Min</td>
      <td>Minimum shadow distance.</td>
    </tr>
    <tr>
      <td></td>
      <td>Shadow Max</td>
      <td>Maximum shadow distance.</td>
    </tr>
    <tr>
      <td></td>
      <td>Shadow Smooth</td>
      <td>Smoothness of shadow edges.</td>
    </tr>
    <tr>
      <td></td>
      <td>AO Step</td>
      <td>Step size for AO calculation.</td>
    </tr>
    <tr>
      <td></td>
      <td>AO Intensity</td>
      <td>Intensity of AO.</td>
    </tr>
    <tr>
      <td></td>
      <td>AO Iteration</td>
      <td>Number of iterations for AO calculation.</td>
    </tr>
    <tr>
      <td><strong>Render Settings</strong></td>
      <td>Max Steps</td>
      <td>Maximum number of steps for raymarching.</td>
    </tr>
    <tr>
      <td></td>
      <td>Max Dist</td>
      <td>Maximum distance to raymarch before considering a hit.</td>
    </tr>
    <tr>
      <td></td>
      <td>Surf Dist</td>
      <td>Threshold for considering a hit in raymarching.</td>
    </tr>
  </table>

**Rendering a shape**
* After adding the `Raymarcher` component to the Main Camera, create an empty gameobject and add the `RaymarchRenderer` component to it.
* Click the `Create New Dimensions` button to create a scriptable object containing all the data about the shape's dimension that you can control using the custom editor for each shape.
* The `RaymarchRenderer` script has the following paramters in the inspector:
  
  <table class="custom-table">
    <tr>
      <th>Category</th>
      <th>Variable</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><strong>Default Inspector</strong></td>
      <td>Shape</td>
      <td>4D shape to be rendered.</td>
    </tr>
    <tr>
      <td></td>
      <td>Operation</td>
      <td>Operation to be performed (union, subtraction, intersection).</td>
    </tr>
    <tr>
      <td></td>
      <td>Color</td>
      <td>Color of the shape.</td>
    </tr>
    <tr>
      <td></td>
      <td>Rot W</td>
      <td>Local W rotation in 4D space.</td>
    </tr>
    <tr>
      <td></td>
      <td>Pos W</td>
      <td>Local W position in 4D space.</td>
    </tr>
    <tr>
      <td></td>
      <td>Blend Factor</td>
      <td>Currently not implemented.</td>
    </tr>
    <tr>
      <td></td>
      <td>Dimensions</td>
      <td>Scriptable Object holding the shape's dimension data.</td>
    </tr>
    <tr>
      <td><strong>Shape Dimensions</strong></td>
      <td>Dimension Props</td>
      <td>The dimension properties based on the chosen 4D shape.</td>
    </tr>
  </table>
  
## Contributing
Contributions to the project are welcome. Things that need work:
* Currently operations triggers global operation on the last object. Need to change it to local operations with the objects in proximity/chosen objects.
* Make a better collision detection system.
* Implement a system to blend different shapes.
* Implementing [n-dimensional rigid body dynamics](https://marctenbosch.com/ndphysics/).
  
## License
MIT License
