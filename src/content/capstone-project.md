## Comical Post Processing Effect

Chroma's art direction was to make the game look comical in a confomist environment, showing the contrast between the character and the world. To sell this idea, I developed a post processing effect that gives the game a comic book like look. Below is the video of the effect in action and also a breakdown of the effect. 

<center>
<video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
  <source src="/assets/images/capstone2.mp4" type="video/mp4">
</video>
</center>

* I first made a outline shader to make certain points of interset like pop out. Since we had a lots of points of interest I decided to create a post processing effect that gets applied to a custom stencil and then the outline shader is applied to the stencil, this way we can control which parts of the scene get the outline effect. This presented two disadvantages:
    * The outline effect was rendering top of other objects and was not being occluded by them.
    * The outline effect looked same on all objects.
 To solve the first problem I implemented an occlussion mask that used the depth buffer to check if the pixel is occluded by another object and not render the outline there. I'm still working on the solution for the second problem.

* I then created a higlight overlay material by using a Fresnel effect as the opaciy mask and the the amount of highlight covered by the Fresnel effect is controlled by using World Position Offset. This overlay material is added on certain objects to give it a comical hit effect.
* Then I took the shadow information from the scene as texture by subtracting specular and base color from the scene color, converted it to a mask and overlayed hatching lines over it.
* Finally I did the same thing to make an emissive mask and overlayed a halftone pattern over it.

## Glitch Post Processing Effect

The goal was to establish a spiderverse-inspired glitchy look to some of the VFX associated with the main character's abilities. I developed a post processing effect that gives any object on a custom stencil a give a glitchy look. The VFX is yet to implemented in the game but the effect can be seen in the video below.

<center>
<video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="/assets/images/capstone4.mp4" type="video/mp4">
</video>
</center>

## Artist Tool - Auomated Maya Model Showcase

Seeing the need of the artists to display their models often in a specified format by the leads, I developed a tool for them that automates this process and helps them diplay their models in the specified format just by one click of a button. 

* The tool creates a camera animation that goes around the model.
* The camera is keyframed at 45 degree intervals and the tool adjusts the camera position and rotation to make the model always in the view of the camera and centered.
* The display mode is alternated between wireframe and smooth shaded, and both modes are displayed for each angle.
* I made this tool open source and it can be found [here](https://github.com/aniketrajnish/Model-Showcase-Tool-Maya).
    <center>
    <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="/assets/images/capstone3.mp4" type="video/mp4">
    </video>
    </center>

## UE5 Shockwave Tool

I was presented with a situation where our team needed to create shockwave effects at various places in the game, like in the levels, from the enemies, in between the player reload animation, as a ripple etc. I proposed creating a tool that lets us create shockwave between multiple points and using that tool to create the shockwave effects for all the purposes.
    <center>
    <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="/assets/images/capstone7.mp4" type="video/mp4">
    </video>
    </center>

## Heatwave Effect

I developed an algorithm that creates a heatwave distortion effect and extend this algorithm to create 3 different ways to add this effect to the level:
* As a on-screen post processing effect that applies to the whole screen.
* As a meaterial that can be applied to mesh of different shapes to govern the area of effect.
* As a particle system to add more behavior to the effect.
    <center>
    <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="/assets/images/capstone6.mp4" type="video/mp4">
    </video>
    </center>

## Optimized Alembic Curly Hair

We had to implement curly hair for the main character of the game, keeping in mind that it shouldn't have a lot of performance overhead. I used the groom plugin in UE5 to import an alembic cache as a hair component. I optimized the hair by:
* Dividing the hair into buns, modelling just one bun having fewer than 500 particles in blender and using GPU Instancing to render multiple copies of the buns. This sacrificed the variety of buns but it was not of importance to us. This gave us a performance boost of 4x (1x for each bun).
* Giving the hair material just a simple gradient between two colors from top to bottom. The hair material was also changed to a masked material that subdivided each strand into 8 different strands, faking 4000 strands for each bun from the 500 strands giving us a performance boost of 8x.
* Disabling hair physics and manually keyframing each bun, adding to the comical look of the game, and drastically reducing the performance overhead. This gave us a performance boost of ~2x.
* In total we got a performance boost of 8x \* 4x \* ~2x = ~64x.
    <center>
    <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
        <source src="/assets/images/capstone5.mp4" type="video/mp4">
    </video>
    </center>

## Death Dissolve Effect

I developed a death dissolve effect for the enemies in the game. 
    <center>
    <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="/assets/images/capstone8.mp4" type="video/mp4">
    </video>
    </center>