---
layout: post
title: FIEA Technical Artist Portfolio
date: 2022-11-03 11:00:00
description: this blog shall contain some of my favorite pieces of code/artwork that I'd be submitting for my Technical Artist Portfolio (for FIEA)!
tags: unity3d unreal-engine FIEA tech-art
categories: blog
---

As the title suggests, this blog shall contain some of my favorite pieces of code/artwork that I'd be submitting for my Technical Artist Portfolio (for [FIEA](https://fiea.ucf.edu/)) in no particular order.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/FIEA_PORTFOLIO.png" title="FIEA Portfolio" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

#### **1.0 2D Lighting System - Unity**
* While competing for the [Brackeys Game Jam 2021.1](https://itch.io/jam/brackeys-5), we decided to make a top-down atmospheric 2D game as they were trending a lot on [itch.io](https://itch.io/) back then.
* Back when we started working on this project, Unity didn’t have any rendering pipeline that supported 2D lighting, so I developed my own lighting system for it. This was primarily done to add to the atmospheric look of the game.
* The detailed documentation and source code can be found [here](https://makra.wtf/docs/2022/two-opoosites/).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/2dlightsys.gif" title="The first iteration" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    The first iteration
</div>

* The first iteration uses the Unity’s low level [Graphics Library (gl)](https://docs.unity3d.com/ScriptReference/GL.html) to draw rays emerging from the player.
* An Unlit Shader that supports both transparency and vertex colors is used as the ray's material to make the light rays feel natural.
* The environment is scripted to react to the lighting.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/2dmeshlightsys.gif" title="The second iteration (optimized)" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    The second iteration (optimized)
</div>

* The previous lighting method was very inefficient with time complexity of `O(n)` as the loop had to run 3600 times every frame with a step size of 0.1.
* I solved this issue by detecting the edges of nearby objects, casting rays at them, and then filling the space by generating mesh between them in the second iteration.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/2oppingame.gif" title="In-game look" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    In-game look
</div>

* This is how the lighting finally looked in the game, with some post-processing thrown on top of it. You can try it yourself [here](https://makra.itch.io/two-opposites).

#### **2.0 ASCII Line Art - p5js**
* After getting an experience as a tech artist at FIEA this summer, I was confident this was the track that I'd be applying to.
* To provide a testimony to it, I decided to make ASCII Line art for all professors and mentors this Teacher's Day.
* I designed 52 of these in total and made one for Prof. Chris Roda, Prof. Rick Hall, and Prof. Ron Weaver as well.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/CHRIS_SIR.png" title="Chris Sir" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Chris Sir
        </div>
    </div>    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/RICK_SIR.png" title="Rick Sir" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Rick Sir
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/RON_SIR.png" title="Ron Sir" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Ron Sir
        </div>
    </div>     
</div>

* These were made using [p5js](https://p5js.org/) by detecting changes in the overall RGB values of different parts of images.

{% highlight javascript %}

//text to be used in the image
const name = 'chrisroda';

function draw() {

  //setting background to black
  background(0);
  
  let w =  width / img.width;
  let h =  height / img.height;
  img.loadPixels();

  //iterating through pixels and assigning letters based on average rgb values
  for (let i = 0; i < img.width; i++) {
    for (let j = 0; j < img.height; j++) {
      const pixelIndex = (i + j * img.width) * 4;
      const r = img.pixels[pixelIndex + 0];
      const g = img.pixels[pixelIndex + 1];
      const b = img.pixels[pixelIndex + 2];
      const avg = (r + g + b) / 3;
      
      noStroke();
      fill(255);
      
      const len = name.length;
      const charIndex = floor(map(avg,0,255,len,0));  
      
      textSize(w);
      textAlign(CENTER, CENTER);

      //edge detection (hardcoded)
      if(avg > 100 && avg < 180)     
          text(name.charAt(charIndex), i * w + w * 0.5, j * h + h * 0.5);     
      
    }
  }
}

{% endhighlight %}

* If you zoom onto the images (by clicking on them), you'll find out that the pixels of the images are converted into letters of the name of the person that it's made for.
* Many of these images were converted into DXF format and engraved on acrylic sheets to be gifted to the professors.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Collage_LineArt.png" title="Engraved Images" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Engraved Images
</div>

#### **3.0 Raymarched Clouds**
* While working on Human Canon prototype for CrazyLabs, I encountered the classic problem of optimizing volumetric clouds for low-end devices (especially mobile).
* While doing my research over the internet, I came across this [video](https://youtu.be/4QOcCGI6xOU) about raymarched clouds by Sebastian Lague.
* This video eventually drew my attention towards raymarching, and eventually, I wrote my own raymarcher for Unity. You can find the project [here](https://github.com/aniketrajnish/Raymarching-Engine-Unity). The HLSL (Shader) files can be found [here](https://github.com/aniketrajnish/Raymarching-Engine-Unity/tree/main/Assets/Shaders).
* Further, I followed [this article](https://shaderbits.com/blog/creating-volumetric-ray-marcher) about making raymarched volumetric clouds in Unreal engine to develop my own version of the same in Unity.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <video class="video-fluid rounded z-depth-1" autoplay muted loop>
            <source src="../../../assets/img/Raymarch_Clouds.mp4" type="video/mp4">
        </video>
    </div>
</div>
<div class="caption">
    Raymarched Clouds in Unity
</div>


#### **4.0 Raymarched 4D Environment**
* I further extended the raymarching engine to render 3D sections of Four-dimensional objects like HyperCube, HyperSphere and DuoCylinder.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <video class="video-fluid rounded z-depth-1" autoplay muted loop>
            <source src="../../../assets/img/Raymarch_4d.mp4" type="video/mp4">
        </video>
    </div>
</div>
<div class="caption">
    Raymarched 4D Objects in Unity
</div>

* The 4D shape distance functions—

{% highlight HLSL %}

//Hypercube
float Hypercube(float4 p, float4 b)
{
    float4 d = abs(p) - b;
	return min(max(d.x,max(d.y,max(d.z,d.w))),0.0) + length(max(d,0.0));
}

//Hypershpere
float Hypersphere(float4 p, float s)
{
    return length(p) - s;
}

//Duo Cylinder
float DuoCylinder( float4 p, float2 r1r2) {
  float2 d = abs(float2(length(p.xz),length(p.yw))) - r1r2;
  return min(max(d.x,d.y),0.) + length(max(d,0.));
}

{% endhighlight %}

#### **5.0 Snowstorm System - Soul Shard**
* I assisted the [19 Souls on Board](https://www.19soulsonboard.com/about) team at FIEA as a technical artist for their capstone project [Soul Shard](https://store.steampowered.com/app/2005820/Soul_Shard/). The game is getting processed by Steam and will be out soon!
* As a part of this engagement, one of my tasks was to develop a snowstorm system for the yard area that's situated in the middle of the map by looking at a [reference video](https://www.youtube.com/watch?v=sGkh1W5cbH4).
* The detailed documentation and source code can be found [here](https://makra.wtf/docs/2022/soul-shard/).
* To simulate a natural looking snowstorm, I decided to divide the snowstorm into three subsystems—  
  
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Snow1.gif" title="A Snow Subsystem" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Snow Subsystem
        </div>
    </div>    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/WindPart.gif" title="A Wind Subsystem" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        A Wind Subsystem
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/FogEH.gif" title="A Fog Subsystem" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        A Fog Subsystem
        </div>
    </div>     
</div>

* Putting these together after proper scaling gave the following result—

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <video class="video-fluid rounded z-depth-1" autoplay muted loop>
            <source src="../../../assets/img/SnowStormFinal.mp4" type="video/mp4">
        </video>
    </div>
</div>
<div class="caption">
    Snowstorm System Final In-Game Look
</div>

#### **6.0 Digital Art - Hypercasual Concept Pitches**
* As a part of the PPP (Pay-Per-Prototype) deal by CrazyLabs, I was expected to deliver Concept Pitches of various Hypercasual ideas and they approved the best ones for me to develop.
* To make the digital art mockups for these, I used Procreate on iPad.
* These are the mockups for the game Tilt Paint (the original concept pitch can be found [here](https://makra.wtf/assets/pdf/TiltPaint.pdf))—

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TP_1.png" title="Mockup" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TP_2.png" title="Mockup" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/TP_3.png" title="Mockup" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>     
</div>

* Some mockups were rendered in Blender too. Take for instance the mockup of Body Crack ASMR (the original concept pitch can be found [here](https://makra.wtf/assets/pdf/BodyCrackASMR.pdf))—

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/BASMR_1.png" title="Mockup" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/BASMR_2.png" title="Mockup" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/BASMR_3.png" title="Mockup" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/BASMR_4.png" title="Mockup" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>       
</div>

* The comprehensive list and source files for all the 30 concept pitches delivered can be found [here](https://makra.wtf/projects/) by scrolling to the `concept pitches` section.

#### **7.0 Retro Shader & Post Processing - Are Ya Winning, Son?**
* While participating in the GMTK Game Jam 2020, we worked on a retro-styled game where the AI won't let you win. 
* To add to the retro theme, we decided to use shaders and post-processing effects so that the game feels as if it's being played on a CRT TV.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <video class="video-fluid rounded z-depth-1" autoplay muted loop>
            <source src="../../../assets/img/AYWS_fin.mp4" type="video/mp4">
        </video>
    </div>
</div>

* This was achieved by using Post-Processing & a distorted render texture layered on top of it.
* You can play the game [here](https://makra.itch.io/are-ya-winning-son) and watch its devlog [here](https://youtu.be/Anhjc7sRoFc).

#### **8.0 Pixel Art - Doge to the Moon**
* While competing for the Opera GX Game Jam, I worked on Pixel Art of various characters of our game [Doge to The Moon](https://gamejolt.com/games/doge2themoon/636263). 
* All of these Pixel Arts were made using the GameMaker Studio 2's Sprite Editor.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Doge_PA.png" title="All Pixel Arts" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    All Pixel Arts
</div>

* All of these assets also had their glowing counterpart to mimic the animation of getting hit.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Doge_Hit_PA.png" title="Glowing Pixel Arts" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Glowing Pixel Arts
</div>

* Most of the sprites were converted into sprite sheets to animate the sprites with slight variations in each slice of the sprite sheet.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Doge_Anims_PA.png" title="Animation Sprite Sheets" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Animation Sprite Sheets
</div>

* Apart from these sprites, I also designed the background images (starts and the space) and made them scroll vertically at different speeds to give a parallax effect.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/stars_PA.png" title="Stars Section" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Stars Section
        </div>
    </div>    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Back_PA.png" title="Background Section" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Background Section
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Doge_Final.gif" title="Final In-Game Look" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Final In-Game Look
        </div>
    </div>     
</div>

#### **9.0 VFX Graph in Unity**
* I had to make a theme reveal video for a [Game Jam](https://itch.io/jam/gamejam-2020-ad) that my college was hosting. 
* I decided to utilize this opportunity and learn VFX graphs in Unity. 
* VFX graph help simulate over a million particles in real-time as they use the parallel processing capabilities of GPU, unlike the default particle system that runs on CPU.
* Everything that you see in this video is made out of '2020', which was the theme for the JAM itself.

<div class="embed-responsive embed-responsive-16by9 rounded z-depth-1-half" style="width: auto;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/kPlAOdrKgbw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<br>

#### **10.0 Non-Euclidean Worlds in Unity**
* I worked on various Non-Euclidean world simulations inside of Unity, especially after CodeParade announced that [it's technically impossible to develop Non-Euclidean worlds in Unity without low-level access to its Rendering Engine](https://youtu.be/kEB11PQ9Eo8?t=233).
* The first simulation consisted of cameras rendering over a render texture in the opening of a tunnel and colliders that teleported the player between different worlds seamlessly, offering a non-euclidean illusion.

<div class="embed-responsive embed-responsive-16by9 rounded z-depth-1-half" style="width: auto;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/Jv5gQzI1xhk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<br>

* The subsequent two simulations used multiple intersecting single-sided planes instead of a 3d mesh to give a non-euclidean look.

<div class="d-flex">
  <div class="embed-responsive embed-responsive-16by9 mr-3 rounded z-depth-1-half" style="width: 50%;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/wi1RoQJWHbk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>
  </div>
  <div class="embed-responsive embed-responsive-16by9 rounded z-depth-1-half" style="width: 50%;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/4zfHbw6GRes" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>
  </div>
</div>

<br>

#### **11.0 Terrain Sculpting - Map of India for AFPS**
* I led a team of 25 individuals to develop an Indian-themed battle royale game.
* The top view of the map was sculpted to represent the Indian map.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/AFPS_TopView.png" title="In-Game Look of the Map" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    In-Game Look of the Map
</div>

* This terrain was sculpted using the Unity's default Terrain Editor, and this is the timelapse video of developing this map-

<div class="embed-responsive embed-responsive-16by9 rounded z-depth-1-half" style="width: auto;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/n17XMTDp_Ns" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
<br>

#### **12.0 Glowing Crack Material - Soul Shard**

* I developed a material with glowing cracks governed by various parameters for Soul Shard.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/EmissionParameter.png" title="Stars Section" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Emission Parameters
        </div>
    </div>    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/EmissionShape.png" title="Background Section" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Emission Shape
        </div>
    </div>        
</div>

* The material's properties were governed by six parameters in total—
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Coverage.gif" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Coverage
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/GlowIntensity.gif" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Glow Intensity
    </div>
    </div>    
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/PulseIntensity.gif" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Pulse Intensity
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Rate.gif" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Rate
    </div>
    </div>    
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/EmissiveColor.gif" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Emissive Color
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/BaseTint.gif" title="example image" class="img-fluid rounded z-depth-1" zoomable=true %}
        <div class="caption">
        Base Tint
    </div>
    </div>    
</div>