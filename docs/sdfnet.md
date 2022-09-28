---
layout: default
---

## SDFNet: Boring 2D Flat images to fast-rendered 3D
<div align = center>
<a href="../files/sdfnet.png" data-lightbox="sdfnet" data-title="SDFNet"><img src="../files/sdfnet.png" style="width:50%"></a>
</div>

SDFNet aims to go from boring flat, 2D images to less boring Signed Distance Functions for representing them in 3D, for simple, symmetric shapes. It uses Neural Radiance Fields (NeRFs) and Constructive Solid Geometry to go from images to 3-Dimensional objects, to SDFs for the shapes.

We're deeply referencing the code accompanying the paper: [CSGNet: Neural Shape Parser for Constructive Solid Geometry, CVPR 2018](https://arxiv.org/abs/1712.08290). Also referenced is the paper on Neural Radiance Fields, whose code can be found [here](https://github.com/bmild/nerf).

### Week - 1

1. Discussed and formulated a brief plan of action and direction we would like the project to head to.
2. Concluded on working initially towards two directions- 
   * 3D reconstruction of objects from their 2D images
   * Improved implementation of Neural Rendering. 

### Week - 2

1. Identified and collected previous research work like [CSGNet](https://hippogriff.github.io/CSGNet/) and [Pixel2Mesh](https://nywang16.github.io/p2m/index.html) in the domains.
2. Formulated the Problem Statement - Improving CSGNet by adding more shape information, introducing color reconstruction, and creating a 2D image to 3D mesh pipeline.
3. Began the Iteration One of reconstruction of the 3D model of a bottle. This was integral in helping us understand the nitty gritty of and the subtle details that were missed in mere discussions and research overview.
4. Continued research work on the papers of Neural Rendering and Constructive Solid Geometry.

### Week - 3

1. Created a [dataset](https://drive.google.com/drive/folders/1QhGyF3J2KmQ43NiDzePNF9ne_9iHSgRk) using blender, developed the [model](https://colab.research.google.com/drive/1HBpZzwO55UoJX1YpubzkLNc-pvD0C2Th?ts=62eb973a) to predict the required dimensions from a 2D image. As the first iteration, although the results being sub-par (with a MSE ~16), it helped us identify the next direction to move forward, ie, we needed some method to extract the 3D information from the images before feeding it to the Neural Network.
2. Created a [repo](https://github.com/aniketrajnish/CS499-SDFNet) to collaborate. 
3. We began analyzing papers such as Pixel2Mesh for the above problem.
4. Continued reseach work on the papers of Neural Rendering.

### Week - 4

1. Implemented a SDF Renderer (built ground-up in Unity) to reconstruct images from the data provided by the first iteration model.
2. Identified new directions to progress, one being Pixel to Mesh followed by reconstruction using CSGNet, while also looking to explore the possibility of using the function within Neural Radiance Field for 3D reconstruction.

<table border="0">
 <tr>
    <td><video style="width:100%" autoplay muted loop>
  <source src="../files/bottle_dataset.mp4" type="video/mp4">  
  </video></td>
    <td><video style="width:100%" autoplay muted loop>
  <source src="../files/bottle_sdf.mp4" type="video/mp4">  
  </video></td>
 </tr>
 <tr>
    <td>Blender Dataset</td>
    <td>Rendered using the SDF Renderer</td>
 </tr>
</table>

### Week - 5
* Implemented operations in the renderer & sh

### Contact

To ask questions, please email any one of us: [Aniket](mailto:aniket.r@iitgn.ac.in), [Dhyey](mailto:dhyey.thummar@iitgn.ac.in), [Progyan](mailto:progyan.das@iitgn.ac.in) and [Shruhrid](mailto:shruhrid.banthia@iitgn.ac.in).
