A fast GPU-accelerated raymarching engine for Unity with support for over 28 primitives (including fractals, n-dimensional objects, volumetric clouds) and set operations (Union, Subtract, Intersect). Includes a custom interface for manipulating shader parameters through the editor.<br>

## Updates
**v002**
* The engine now stores the dimensions of the shapes as scriptable objects, to keep multiple instances of same shape persistant across sessions.
* Added support for Ambient Occlussion, Hard/Soft Shadows and various render setting exposed for the users to play around with.
* Download the `.unitypackage` [here](https://github.com/aniketrajnish/Raymarching-Engine-Unity/releases/tag/v002).

## Rendering the shapes provided

**1. Using an Image Effect Shader**
* Attach `Raymarcher.cs` to the Main Camera and `RaymarchRenderer.cs` to an empty gameobject.
* Drag the `ImageEffectRaymarcher.shader` in Shader field of `Raymarcher.cs` in inspector and direction light to the Sun's transform field.
* Click on `Create New Dimensions` in the `RaymarchRenderer.cs` to create a scriptable object to hold the dimesnion data of the shapes.
* You can control the following settings for the raymarching using the `Raymarcher` component-

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
* You can control the following properties of the individual shapes using the `RaymarchRenderer` componnent-
  <table class="custom-table">
    <tr>
      <th>Category</th>
      <th>Variable</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><strong>Default Inspector</strong></td>
      <td>Shape</td>
      <td>Shape to be rendered.</td>
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
      <td>Create New Dimensions</td>
      <td>Button to create new dimenion scriptable object for the shape</td>
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

## Rendering a custom shape
* Append the distance function of the shape in `DFs.cginc` like
    ```
    float sdShape(float3 p, // dimension parameters)	
    {
        // distance function here
    }
    ```   
* Append the distance function created above in `GetDist()` in the `ImageEffectRaymarcher.shader`.
    ```
    float GetDist(Shape shape, float3 p) {
        switch (shape.shapeIndex) {
        case n:
            return sdShape(float3 p, // dimension parameters);
        }
    }
    ```
* Add the shape data in the scriptable object `ShapeDimensions.cs`
  ```
  public float shapeDimension = default dimenison
  ```
* Add the shape in Shape enum in `RaymarchRenderer.cs` 
    ```
    public enum Shape {
        // shape name
    };  
    ```
* Make the dimension array in `Helpers.cs` to be sent as a compute buffer to the Raymarching shader.
    ```
    public static vector12 GetDimensionVectors(int i)
    {
        //dimension vector12 object
    }
    ```
* Finally make a custom editor for your shape in the `PropertiesEditor.cs`
    ```
    public override void OnInspectorGUI()
    {
        base.OnInspectorGUI();
        RaymarchRenderer renderer = (RaymarchRenderer)target;        
         
        if (GUILayout.Button("Create New Dimensions"))
           renderer.dimensions = CreateShapeDimensionsAsset();
         
        if (renderer.dimensions == null)
           return;
    
        switch (renderer.shape)
        {
            //property editor here
        }
    }
    ``` 



