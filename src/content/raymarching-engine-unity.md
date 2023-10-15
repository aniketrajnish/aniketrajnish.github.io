A fast GPU-accelerated raymarching engine for Unity with support for over 28 primitives (including fractals, n-dimensional objects, volumetric clouds) and set operations (Union, Subtract, Intersect). Includes a custom interface for manipulating shader parameters through the editor.<br>

## Rendering the shapes provided

**1. Using an Image Effect Shader**
* Attach `Raymarcher.cs` to the Main Camera and `RaymarchRenderer.cs` to an empty gameobject and set the properties and type of shape to render in the inspector.
* Drag the `ImageEffectRaymarcher.shader` in Shader field of `Raymarcher.cs` in inspector and direction light to the Sun's transform field.

**2. Using an Unlit Shader**
* Append the following lines in `Raymarcher` class of `Raymarcher.cs`
```
 private void Awake()
 {
     GetComponent<MeshRenderer>().material = _raymarchMaterial;
 }
 private void OnEnable()
 {
     EditorApplication.update += OnUpdate;
 }   
 private void OnUpdate()
 {
     RaymarchRender();
     EditorApplication.QueuePlayerLoopUpdate();
 } 
 private void Update()
 {
     RaymarchRender();
 }
 private void OnDisable()
 {
     EditorApplication.update -= OnUpdate;
     foreach (var buffer in disposable)
     {
         buffer.Dispose();
     }
 }
 
 // Append this in RaymarchRender function
 void RaymarchRender()
 {  
     for (int i = 0; i < renderers.Count; i++)
     {
         if (renderers[i] == GetComponent<RaymarchRenderer>())            
             _raymarchMaterial.SetInt("rank", i);
     }
 }
```
* Attach `RaymarchRenderer.cs` and `Raymarcher.cs` to a gameobject having a mesh renderer and set the properties and type of shape to render in the inspector.
* Drag the `Raymarcher.shader` in Shader field of `Raymarcher.cs` in inspector and direction light to the Sun's transform field. 

## Rendering a custom shape

* Append the distance function of the shape in `DFs.cginc` like
```
float sdShape(float3 p, // dimension parameters)	
{
    // distance function here
}
```   
* Append the distance function created above in `GetDist()` in `Raymarcher.shader` (if using the unlit shader) or in the `ImageEffectRaymarcher.shader` (if using the Image Effect shader).
```
float GetDist(Shape shape, float3 p) {
    switch (shape.shapeIndex) {
    case n:
        return sdShape(float3 p, // dimension parameters);
    }
}
```
* Add the shape in Shape enum and create a struct for its default dimension parameters in `RaymarchRenderer.cs`. 
```
public enum Shape {
    // shape name
};
public struct shapeDimensions
{
   // default shape dimensions;
};
```
* Make the dimension array in `Helpers.cs` to be sent as a compute buffer to the Raymarching shader.
```
public static vector12 GetDimensionVectors(int i)
{
    //dimension array
}
```
* Finally make a custom editor for your shape in the `PropertiesEdior.cs`
```
public override void OnInspectorGUI()
{
    base.OnInspectorGUI();
    EditorGUILayout.Space();
    EditorGUILayout.LabelField("Dimensions", EditorStyles.boldLabel);
    RaymarchRenderer rr = (RaymarchRenderer)target;
    switch ((int)rr.shape)
    {
        //property editor here
    }
}
```



