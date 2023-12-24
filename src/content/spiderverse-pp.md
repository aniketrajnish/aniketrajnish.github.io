Spiderverse-inspired stylized post-processing effect for Unreal Engine and Unity.
 
## Usage
**Unity**
* Download the `.unitypackage` from the [Releases Section](https://github.com/aniketrajnish/StylizedPostProcess-Unreal-Unity/releases/tag/v001-unity).
* Open/Create a new URP Unity project.
* Import the package into the project.
* Enable the Stylized Renderer Feature in your URP Renderer (generally in `Assets/Settings` folder) by adding the `Stylized Renderer Feature` to the Renderer Features.
* Control the Renderer Feature's properties by adding a `Global Volume` component to your scene.
* Add `Makra/Stylized PP` override to the Volume component. The custom post-processing contains the following components-
  
  <table class="custom-table">
    <tr>
      <th>Property</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><strong>Threshold</strong></td>
      <td>Minimum brightness for the effect to be applied.</td>
    </tr>
    <tr>
      <td><strong>Intensity</strong></td>
      <td>Strength/Brightness of the effect.</td>
    </tr>
    <tr>
      <td><strong>Scatter</strong></td>
      <td>How much screen space the effect occupies.</td>
    </tr>
    <tr>
      <td><strong>Dots Density</strong></td>
      <td>Density of the benday dots.</td>
    </tr>
    <tr>
      <td><strong>Dots Cutoff</strong></td>
      <td>Cutoff value of benday dots.</td>
    </tr>
    <tr>
      <td><strong>Scroll Velocity</strong></td>
      <td>Velocity of the dots scrolling over the screen.</td>
    </tr>
  </table>

* You can use the Unity Project in `src/UnityStylizedPP` for reference.
  <center>
  <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="https://github.com/aniketrajnish/SpiderVersePostProcess-Unreal-Unity/assets/58925008/5b4cba4b-7982-4098-b80e-482948f007dc" type="video/mp4">
  </video>
  </center>

**Unreal Engine**
* Download the Unreal Project from the [Releases Section](https://github.com/aniketrajnish/SpiderVersePostProcess-Unreal-Unity/releases/tag/v001-unreal).
* Use the map in the Unreal Project as a reference.
* To implement the stylized post-processing in your project, migrate the `Content/StylizedPP` from the project you downloaded above to your Unreal Project.
* Add a `PostProcessVolume` component to the level.
* Make sure that `Infinite Extent` is checked in the Post Process Volume Settings.
* Assign the `M_PP_Stylized_Inst` material to the Post Process Materials.
* Control the post process properties by going to thet `M_PP_Stylized_Inst` and changing the following parameters-
  
  <table class="custom-table">
    <tr>
      <th>Property</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><strong>Benday Clip</strong></td>
      <td>Minimum brightness for the effect to be applied.</td>
    </tr>
    <tr>
      <td><strong>Density Benday</strong></td>
      <td>Density of the benday dots.</td>
    </tr>
    <tr>
      <td><strong>Density Line</strong></td>
      <td>Density of the hatching lines.</td>
    </tr>
    <tr>
      <td><strong>Direction Benday</strong></td>
      <td>Direction of Benday Pattern.</td>
    </tr>
    <tr>
      <td><strong>Direction Line</strong></td>
      <td>Direction of Hatching Pattern.</td>
    </tr>
    <tr>
      <td><strong>Spec Mult</strong></td>
      <td>Intensity and spread of specular highlights.</td>
    </tr>
  </table>

* To create a stencil mask for the benday dots to be applied only on specific objects, go to project settings and change the `Custom Depth-Stencil Pass` to `Enabled with Stencil`.
* In the mesh that you want to render the benday dots upon, enable the `Render CustomDepth Pass` option and change the `Custom Stencil Value` to 1. 
  <center>
  <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="https://github.com/aniketrajnish/SpiderVersePostProcess-Unreal-Unity/assets/58925008/040f165c-beb3-4eb2-b466-0c11bd1f2c14" type="video/mp4">
  </video>
  </center>

## Contributing
Contributions to the project are welcome. Currently working on:
* Fixing glitches with persistent shadows in UE5.
* Add hatching lines to the shadows in Unity.
  
## License
MIT License
