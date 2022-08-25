---
layout: default
---

## DES 499 - Jantar Mantar Reconstruction

As a part of this project course we're expected to create a physically precise interactive model of the various yantras at [Jantar Mantar](https://www.jantarmantar.org/) in Unity.  This project is being mentored by [Sameer Sahasrabudhe](https://iitgn.ac.in/faculty/design/sameer).

### 1.0 Week - 1
In the first week we were mostly expected to collect reference materials online as well as start working upon rough models of few of the Yantars (need not be physically accurate).
### 1.1 Reference Materials
* We collected a lot of Reference Materials and listed them [here](https://docs.google.com/document/d/1l8tKDSJfwaVZQedeRZSi7APF9uCLk7THDPQUlbR4L1Q/edit?usp=sharing).  
* Although, we couldn't find any document that depicted the exact dimensions of Jantar Mantar, but we did find a [website](https://www.jantarmantar.org/resources/Projects/SY-Model/Samrat-Yantra-Model-Templates.pdf) containing the paper model replica of jantar mantar.     
    
### 1.2 3D Models 
* Then we created rough models of the [Samrat Yantra](https://www.jantarmantar.org/learn/observatories/instruments/samrat/index.html) in Blender based on the resources we could procure.
* As the model didn't take CAD dimensions into account, it sure had some flaws that were pointed by Sameer Sir in our weekly meetings. Especially the fact that the base model wasn't symmetrical from both the sides.
* We were later expected to come up with dimensionally accurate models based on CAD and paper model replicas that we found.
    
<a href="../files/SamratYantraRough.png" data-lightbox="yantra" data-title="Rough Model of Samrat Yantra"><img src="../files/SamratYantraRough.png" style="width:100%"></a>     
  <table border="0">
  <tr>
  <td><a href="../files/Error1_SamratYantra.png" data-lightbox="yantra"data-title="Left Side - Base"><img src="../files/Error1_SamratYantra.png"style="width:100%"></a></td>
  <td><a href="../files/Error2_SamratYantra.png" data-lightbox="yantra"data-title="Right Side - Base"><img src="../files/Error2_SamratYantra.png"style="width:100%"></a></td>    
  </tr>
  <tr>
      <td>Left Side - Base</td>
      <td>Right Side - Base</td>
  </tr>
  </table> 
  *Not Symmetrical*   

### 1.3 Day & Night Cycles
 My job was to script the day & night cycles in Unity (need not be physically precise initially).
 * I used a Procedural Sky shader for skybox as it comes with a sun that mimics the directional light by default.
 * Then I bound the directional light's rotation and intensity, fog color and a clock to the day & night cycle. 

<video style="width:100%" autoplay muted loop>
  <source src="../files/day_night.mp4" type="video/mp4">  
</video>

### 2.0 Week - 2
In the next week we were assigned the task to come up with dimensionally accurate CAD models, labelling of Jantar Mantar Engineering Drawings, making of a paper prototype and 3D models of Jantar Mantar that we obtained online and adding a rough sundial model in Unity to check if the shadows casted by the day & night cycle are working properly. 

### 2.1 Accurate CAD Models
### 2.2 Labelling of Engineering Drawings
### 2.3 Making of Paper Prototype
### 2.4 Shadows in Unity