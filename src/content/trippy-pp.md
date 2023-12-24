 A trippy post-processing and render feature for Unity's URP based on [Sobel Filter Edge Detection](https://en.wikipedia.org/wiki/Sobel_operator). I wrote this so that the next time I get high, I would work on projects with this ON :] 

## Usage
* Download the `.unitypackage` from the [Releases Section](https://github.com/aniketrajnish/TrippyPostProcessing-Unity/releases/tag/v001).
  * `Trippy_PP_min_v001.1.unitypackage` just contains the backend for the post-processing.
  * `Trippy_PP_all_v001.1.unitypackage` contains the backend as well as a demo scene with the implementation for reference.
* Open/Create a new URP Unity project.
* Import the package into the project.
* Enable the Trippy Renderer Feature in your URP Renderer (generally in `Assets/Settings` folder) by adding the `Trippy Renderer Feature` to the Renderer Features.
* Control the Renderer Feature's properties by adding a `Global Volume` component to your scene.
* Add `Makra/Trippy` override to the Volume component. The custom post-processing contains the following components-    
  <table class = "custom-table">
    <tr>
      <th>Name</th>
      <th>Description</th>
    </tr>
    <tr>
      <td>Enable Effect</td>
      <td>Toggles the effect on or off.</td>
    </tr>
    <tr>
      <td>Intensity</td>
      <td>Intensity of the Trippy effect.</td>
    </tr>
    <tr>
      <td>Edge Color</td>
      <td>Color of the edges.</td>
    </tr>
    <tr>
      <td>Edge Width</td>
      <td>Width of the edges.</td>
    </tr>
    <tr>
      <td>Base Color</td>
      <td>Base color of the environment.</td>
    </tr>
    <tr>
      <td>Use Gradient</td>
      <td>Toggles if a gradient texture is used as the edge color.</td>
    </tr>
    <tr>
      <td>Gradient Tex</td>
      <td>The gradient texture to be used.</td>
    </tr>
  </table>

* If you wanna have some fun consider adding the `TrippyVolumeAnimator.cs` script to the Volume component ;)
  <center>
  <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="https://github.com/aniketrajnish/TrippyPostProcessing-Unity/assets/58925008/c0dd9c55-ced7-45ee-85c3-e9a21e509cb7" type="video/mp4">
  </video>
  </center>

## Contributing
Contributions to the project are welcome. Currently working on:
* A better algorithm for edge width calculation. 
  
## License
MIT License
