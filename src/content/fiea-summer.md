Soul Shard is a cooperative puzzle platformer that draws inspiration from EA's 'It Takes Two'. It is being developed by [19 Souls on Board](https://www.19soulsonboard.com/about), a team of 19 student developers from Cohort 18 at the Florida Interactive Entertainment Academy on the downtown campus of the University of Central Florida. I'm assisting the team as a technical artist this summer.
* The development update to the game can be viewed [here](https://www.youtube.com/watch?v=0S1EbyBRVhw). 
* The repository containing my contributions to the project can be found [here](https://github.com/19SOB/ucf-fiea-19sob-capstone-project-temp).

## 1.0 Smoke System
My first task was to design and develop a stylized explosive smoke particles for various machinery and explosions in the game. The basic idea was to develop a functional prototype and then refine it in the iterative design process.

## 1.1 Cloud Texture
Initially, I designed various cloud textures with separate RGB channels for Base Color, Emmisivity and Opacity Mask.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/CloudRGB.png" data-lightbox="image-cloud-texture" data-title="Cloud Texture">
                <img src="/assets/images/prev/CloudRGB.png" alt="Cloud Texture" >
            </a>
        </td>
    </tr>
</table>

## 1.2 Smoke Material
* The smoke material was made using these textures. 
* The emmisivity and particle colors were exposed for editing while making the particles.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/CloudMat.png" data-lightbox="image-smoke-material" data-title="Smoke Material">
                <img src="/assets/images/prev/CloudMat.png" alt="Smoke Material" >
            </a>
        </td>
    </tr>
</table>

## 1.3 Smoke Particles - 1st iteration
* The smoke particles were made using the Niagara VFX system. 
* The particles (100) were made to spawn in a burst around a cylinder with an initial velocity radially outwards. 
* A positive gravitational force was added to make the particles rise with a drag coefficient to smoothen things and make it feel natural. 
* Individual particles also received rotation in addition to a colour (the exposed parameter) that was lerped from grey to black.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Smoke1.gif" data-lightbox="image-smoke-1" data-title="Smoke Particles - 1st iteration">
                <img src="/assets/images/prev/Smoke1.gif" alt="Smoke Particles - 1st iteration" >
            </a>
        </td>
    </tr>
</table>

## 1.4 Smoke Particles - 2nd iteration
* A light renderer was added to the particles to further intricately define the explosion.
* The light renderer was started off at the same initial position as the smoke particles.
* The intensity was lerped from 100 to 0.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Smoke2.gif" data-lightbox="image-smoke-2" data-title="Smoke Particles - 2nd iteration">
                <img src="/assets/images/prev/Smoke2.gif" alt="Smoke Particles - 2nd iteration" >
            </a>
        </td>
    </tr>
</table>

## 1.5 Debris Texture
The debris texture was made in photoshop using online reference images and the brush tool.<table class="custom-table">
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/DebrisTex.png" data-lightbox="image-debris-texture" data-title="Debris Texture">
                <img src="/assets/images/prev/DebrisTex.png" alt="Debris Texture" >
            </a>
        </td>
    </tr>
</table>

## 1.6 Debris Material
The debris material was created using the debris texture in a similar fashion to the smoke material.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/DebrisMat.png" data-lightbox="image-debris-material" data-title="Debris Material">
                <img src="/assets/images/prev/DebrisMat.png" alt="Debris Material" >
            </a>
        </td>
    </tr>
</table>

## 1.7 Smoke Particles - 3rd iteration
* The debris particle was given the same parameters as the smoke particle.
* Since the debris appeared lighter, the drag was reduced and gravitational force (positive) was raised to increase the spread.
* Apart from that, a fountain emitter was assigned the same debris material to make the spread look more abrupt.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Smoke3.gif" data-lightbox="image-smoke-3" data-title="Smoke Particles - 3rd iteration">
                <img src="/assets/images/prev/Smoke3.gif" alt="Smoke Particles - 3rd iteration" >
            </a>
        </td>
    </tr>
</table>

## 1.8 Spark Texture
The spark texture with separate RGB channels was obtained online.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Spark.png" data-lightbox="image-spark-texture" data-title="Spark Texture">
                <img src="/assets/images/prev/Spark.png" alt="Spark Texture" >
            </a>
        </td>
    </tr>
</table>

## 1.9 Spark Material
* The spark material was made using the spark texture. 
* The blue channel was used as the opacity mask.
* The emmisive color was obtained after combining red and yellow.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/SparkMat.png" data-lightbox="image-spark-material" data-title="Spark Material">
                <img src="/assets/images/prev/SparkMat.png" alt="Spark Material" >
            </a>
        </td>
    </tr>
</table>

## 1.10 Smoke Particles - Final iteration
* The spark particles were given the same parameter as the debris particle, i.e. a higher spread emitter and a fountain emitter.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Smoke4.gif" data-lightbox="image-smoke-4" data-title="Smoke Particles - Final iteration">
                <img src="/assets/images/prev/Smoke4.gif" alt="Smoke Particles - Final iteration" >
            </a>
        </td>
    </tr>
</table>

## 1.11 Other Variations
Few other variations of the smoke system.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Smoke5.gif" data-lightbox="image-smoke-5" data-title="Less stylized system">
                <img src="/assets/images/prev/Smoke5.gif" alt="Less stylized system" >
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/Smoke6.gif" data-lightbox="image-smoke-6" data-title="Debris only system">
                <img src="/assets/images/prev/Smoke6.gif" alt="Debris only system" >
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/Smoke7.gif" data-lightbox="image-smoke-7" data-title="Puff system">
                <img src="/assets/images/prev/Smoke7.gif" alt="Puff system" >
            </a>
        </td>
    </tr>
</table>

## 2.0 Flame system
My subsequent task was to design & develop flame systems for different purposes like burning coal, chimneys, explosion, etc.

## 2.1 Noise Texture
A stylized noise texture was created to serve as the opacity mask for the flame material.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/NoiseTex.png" data-lightbox="image-noise-texture" data-title="Noise Texture">
                <img src="/assets/images/prev/NoiseTex.png" alt="Noise Texture" >
            </a>
        </td>
    </tr>
</table>

## 2.2 Flame Material
* Parametrically controlled texture coordinate was masked to obtain a controllable gradient. The value is clamped between 0 and 1 to prevent excessive bleeding.
* The noise texture was added to give fire-like shape to the mask.
* The UV map of the texture was given a panner (with texture coordinate as input) to animate it, depicting a burning fire.
* A RadialGradientExponential (with texture coordinate as input) was subtracted from the mask to prevent square edges.
* The tiling, erosion & color of the material were exposed as dynamic parameters to be controlled by the Niagara system. 
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FlameMat.gif" data-lightbox="image-flame-material" data-title="Flame Material">
                <img src="/assets/images/prev/FlameMat.gif" alt="Flame Material" >
            </a>
        </td>
    </tr>
</table>

## 2.3 Flame Particles - 1st iteration
* Majorly, the structure of flame system was completed during the formation of material itself.
* The sprites were spawned in a circular grid with different rotations to give a 3D look.
* The color was lerped between yellow and red. 
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FlameVFX.gif" data-lightbox="image-flame-1" data-title="Flame Particles - 1st iteration">
                <img src="/assets/images/prev/FlameVFX.gif" alt="Flame Particles - 1st iteration" >
            </a>
        </td>
    </tr>
</table>

## 2.4 Flame mesh
The flame system previously made was disapproved by the team for being too toony and not matching the game tone setting. So I decided to replace the sprite based particle system to a mesh one. I modeled an icoshpere mesh with decimate modifier for this purpose to provide randomness.
<table class="custom-table">
    <tr>
        <td>
            <img src="/assets/images/prev/FlameMesh.png" alt="example image" >
        </td>
    </tr>    
</table>

## 2.5 Flame material
The flame material was created simply by assigning the particle color input to the emmisive color of the material so that we can assign it later in the emmiter itself.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FlameMesh.png" data-lightbox="image-flame-mesh" data-title="Flame Mesh">
                <img src="/assets/images/prev/FlameMesh.png" alt="Flame Mesh" >
            </a>
        </td>
    </tr>
</table>

## 2.6 Flame Particles - Final iteration
* A fountain based emitter is used after removing gravity, cone velocity, drag and scaleColor just retaining the initial properties.
* The default sprite renderer is replaced with a mesh renderer and the icosphere and the flame material we created is assigned.
* The particles were assigned a random vertical velocity so that variance in the fire's peak giving it a natural eye.
* They're scaled down in size as they reach up to give an inverted conical shape by using bezier curves to keep the transition smooth.
* The color is lerped between yellow and red with the lifetime of the particle.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FlameVFX2.gif" data-lightbox="image-flame-2" data-title="Flame Particles - Final iteration">
                <img src="/assets/images/prev/FlameVFX2.gif" alt="Flame Particles - Final iteration" >
            </a>
        </td>
    </tr>
</table>

## 3.0 Footprint System
Further I was assigned the task to develop a snow-based footprint system over snow for the main characters (Ambrose and Nimue).  

## 3.1 Footprint Sprites - 1st iteration
* I used a snow texture which I found online to make the footprint sprites.
* The foot impressions of the right foot of both the characters were traced using the pen tool and the texture was masked to make the footprint sprites.
* The left footprint sprite was simply made by inverting the image horizontally.
<table class="custom-table">
    <tr>
        <th colspan="2" style="text-align: center;">Foot Impressions</th>
    </tr>
    <tr>
        <td>
            <a href="/assets/images/prev/AmbroseFI.png" data-lightbox="image-ambrose-foot-impression" data-title="Ambrose Foot Impression">
                <img src="/assets/images/prev/AmbroseFI.png" alt="Ambrose Foot Impression">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/NimueFI.png" data-lightbox="image-nimue-foot-impression" data-title="Nimue Foot Impression">
                <img src="/assets/images/prev/NimueFI.png" alt="Nimue Foot Impression">
            </a>
        </td>
    </tr>
    <tr>
        <th>Ambrose Foot Impression</th>
        <th>Nimue Foot Impression</th>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Footprint Sprites</th>
    </tr>    
    <tr>
        <td>
            <a href="/assets/images/prev/AmbroseFPS1.png" data-lightbox="image-ambrose-footprint-sprite-1" data-title="Ambrose Footprint Sprite - 1st iteration">
                <img src="/assets/images/prev/AmbroseFPS1.png" alt="Ambrose Footprint Sprite - 1st iteration">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/NimueFPS1.png" data-lightbox="image-nimue-footprint-sprite-1" data-title="Nimue Footprint Sprite - 1st iteration">
                <img src="/assets/images/prev/NimueFPS1.png" alt="Nimue Footprint Sprite - 1st iteration">
            </a>
        </td>
    </tr>
    <tr>
        <th>Ambrose Footprint Sprite - 1st iteration</th>
        <th>Nimue Footprint Sprite - 1st iteration</th>
    </tr>
</table>

## 3.2 Footprint Material - 1st iteration 
* The material used for the footprints was a deferred decal material with blending mode set to translucent so that you can apply it as a decal.
* The alpha of the texture/sprite was assigned to the opacity of the material and the RGB values to the base color.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FPMat1.png" data-lightbox="image-footprint-material-1" data-title="Footprint Material - 1st iteration">
                <img src="/assets/images/prev/FPMat1.png" alt="Footprint Material - 1st iteration">
            </a>
        </td>
    </tr>    
</table>

## 3.3 Footprint Blueprint
* An actor blueprint is created for both left and right footprints.
* A decal facing downwards with the footprint material is added as the child to the DefaultSceneRoot.
* The decal is made to fade away gradually after 5 seconds.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FPBP.png" data-lightbox="image-footprint-blueprint" data-title="Footprint Blueprint">
                <img src="/assets/images/prev/FPBP.png" alt="Footprint Blueprint">
            </a>
        </td>
    </tr>    
</table>

## 3.4 Adding to the third person blueprint
* I used the default third person character provided by Unreal to playtest the footprints.
* In the TPC blueprint, planes are added as a child of the mesh and the respective foot as the parent socket so that it snaps perfectly with the foot's movement.
* The planes are rendered as invisible (hidden in game), events are prevented from overlapping, and collisions are disabled as they're just meant for spawn reference to the footprints. 
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/TPBP.png" data-lightbox="image-third-person-blueprint" data-title="Adding to the third person blueprint">
                <img src="/assets/images/prev/TPBP.png" alt="Adding to the third person blueprint">
            </a>
        </td>
    </tr>    
</table>

## 3.5 Animation Notifier
* Animation notifiers are added for each footprint to spawn at the appropriate time in the running animation.
* In the third person animation blueprint's event graph, a character reference is set and cast to the third person character as the blueprint awakes.
* In the third person character blueprint's event graph, two new custom events are introduced to spawn the footprints.
* The event is meant to spawn an actor from the footprint class we created earlier. 
* The foot reference is assigned to the spawn location. 
* The actor rotation is assigned to the spawn rotation.
* The spawn scale was decided after playtesting.
* The custom events are assigned to the animation notifier in the third person animation blueprint's event graph.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/AnimNoti.gif" data-lightbox="image-animation-notifier" data-title="Adding run animation notifier">
                <img src="/assets/images/prev/AnimNoti.gif" alt="Adding run animation notifier">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/TPAnimBP.png" data-lightbox="image-third-person-animation-blueprint" data-title="Third person animation event graph">
                <img src="/assets/images/prev/TPAnimBP.png" alt="Third person animation event graph">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/TPCharBP.png" data-lightbox="image-third-person-character-blueprint" data-title="Third person character event graph">
                <img src="/assets/images/prev/TPCharBP.png" alt="Third person character event graph">
            </a>
        </td>
    </tr>
    <tr>
        <th>Adding run animation notifier</th>
        <th>Third person animation event graph</th>
        <th>Third person character event graph</th>
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FP1.gif" data-lightbox="image-first-output" data-title="First Output">
                <img src="/assets/images/prev/FP1.gif" alt="First Output">
            </a>
        </td>
    </tr>
    <tr>
        <th>First Output</th>
    </tr>
</table>

## 3.6 Footprint Sprites - Final iteration
The team pinpointed that the current footprint lacked originality as snow footprints are generally a little darker (dark grey/blue) with blue tint on the edges. Apart from this, they suggested to add normal information to the footprints as well.
* I decreased the exposure of the textures, added bluish tint on the edges using the brush (Chalk 2) tool.
* Further, I generated the normals using the inbuilt 3D tools provided in Photoshop. (which turned out to be one of my most laggy workflow experiences with Photoshop).
<table class="custom-table">
    <tr>
        <th colspan="2" style="text-align: center;">Footprint Textures/Sprites</th>
    </tr>
    <tr>
        <td>
            <a href="/assets/images/prev/AmbroseFPS2.png" data-lightbox="image-new-ambrose-footprint-texture" data-title="New Ambrose Footprint Texture">
                <img src="/assets/images/prev/AmbroseFPS2.png" alt="New Ambrose Footprint Texture">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/NimueFPS2.png" data-lightbox="image-new-nimue-footprint-texture" data-title="New Nimue Footprint Texture">
                <img src="/assets/images/prev/NimueFPS2.png" alt="New Nimue Footprint Texture">
            </a>
        </td>
    </tr>
    <tr>
        <th>New Ambrose Footprint Texture</th>
        <th>New Nimue Footprint Texture</th>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Footprint Normals</th>
    </tr>
    <tr>
        <td>
            <a href="/assets/images/prev/AmbroseFPN.png" data-lightbox="image-ambrose-footprint-normals" data-title="Ambrose footprint normal">
                <img src="/assets/images/prev/AmbroseFPN.png" alt="Ambrose footprint normal">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/NimueFPN.png" data-lightbox="image-nimue-footprint-normals" data-title="Nimue footprint normal">
                <img src="/assets/images/prev/NimueFPN.png" alt="Nimue footprint normal">
            </a>
        </td>
    </tr>
    <tr>
        <th>Ambrose footprint normal</th>
        <th>Nimue footprint normal</th>
    </tr>
</table>

## 3.7 Footprint Material - Final iteration
The footprint material was modified to support normal information and the normal map textures generated were assigned.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FPMat2.png" data-lightbox="image-footprint-material-2" data-title="Footprint Material - Final iteration">
                <img src="/assets/images/prev/FPMat2.png" alt="Footprint Material - Final iteration">
            </a>
        </td>
    </tr>    
</table>
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FP2.gif" data-lightbox="image-final-output" data-title="Final Output">
                <img src="/assets/images/prev/FP2.gif" alt="Final Output">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="1">Final Output</th>
    </tr>
</table>

## 4.0 Snowstorm System
My next task was to design and develop a snowstorm system for the yard area. I was provided with a [reference video](https://www.shutterstock.com/video/clip-1058627680-dense-heavy-blizzard-snowstorm-vfx-insert-slow-motion) for the same.

## 4.1 Snow Particles
* I found this task quite easy and felt that simply a fountain emitter with the default particle renderer would do the trick.
* So, I created a fountain emitter and inverted its initial velocity to make the particles fall downwards instead of upwards. 
* The particles were made to spawn around a big sphere.
* The trajectory cone's apex angle was increased as well to increase the spread of the particles.
* The gravity was decreased and drag was increased to make the snowfall appear more genuine.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Snow1.gif" data-lightbox="image-snow-particles" data-title="Snow Particles">
                <img src="/assets/images/prev/Snow1.gif" alt="Snow Particles">
            </a>
        </td>
    </tr>    
</table>

## 4.2 Wind Material
As I had anticipated, I was suggested to add more depth to the snowstorm. The idea was to make the snow more dramatic by introducing a wind system. They provided a [reference video](https://www.youtube.com/watch?v=sGkh1W5cbH4) as well.
* A translucent unlit material was chosen for the wind particles.
* The emissive color was made to be driven by the particle color. 
* The opacity was controlled by the multiplication of the alpha value of the particle with a RadialGradientExponential to introduce a smooth gradient fall-off that would make the wind look natural.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/WindMat.png" data-lightbox="image-wind-material" data-title="Wind Material">
                <img src="/assets/images/prev/WindMat.png" alt="Wind Material">
            </a>
        </td>
    </tr>    
</table>

## 4.3 Wind Particles
* A new Cascade particle system is created and the rendering for the default emitter is turned off.
* The particle is given random horizontal velocity with minor deviations in other directions.
* An emitter for trails is added and it's made to follow the first emitter and spawn alongside it.
* The wind material created earlier is added to the trail emitter.
* The scale is made to represent a long trail.
* The direction of velocity is made to ribbon over its lifetime to make the trail follow a wave-like pattern.
* The particles are made to spawn around a sphere with controllable radius to control the spread.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/WindPart.gif" data-lightbox="image-wind-particles" data-title="Wind Particles">
                <img src="/assets/images/prev/WindPart.gif" alt="Wind Particles">
            </a>
        </td>
    </tr>    
</table>

## 4.4 Fog Texture
* A smooth noise texture (obtained online) was used as the fog texture for smooth light absorption (extinction).
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FogTex.png" data-lightbox="image-fog-texture" data-title="Fog Texture">
                <img src="/assets/images/prev/FogTex.png" alt="Fog Texture">
            </a>
        </td>
    </tr>    
</table>

## 4.5 Fog Material
* A volume-based material with additive blending is created for the fog to be volumetric.
* A sphere mask between world and particle position with particle radius as the mask's radius is used to control the rate of light absorption (extinction) of the material.
* The mask is parametrically controlled by a hardness and extinction value multiplied by RGB value of the texture I obtained earlier.
* The albedo of the material takes in the multiplication of the sphere mask and the blend overlay between our texture and a RGB value parameter which we can control in the instance of that material.
* Thus we can control the hardness, light absorption rate and the color of the fog.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FogMat.png" data-lightbox="image-fog-material" data-title="Fog Material">
                <img src="/assets/images/prev/FogMat.png" alt="Fog Material">
            </a>
        </td>
    </tr>    
</table>

## 4.6 Fog Particle
* A new Cascade particle system is created and an instance of the fog material is assigned to it. 
* The particle is scaled only along the X-axis & Z-axis to represent a flat surface and its velocity is set to zero.
* This particle needs to be paired with an exponential height fog (with volumetric fog enabled) to render over the screen.
* The particles are spawned around a cylinder (having zero thickness) with its flat edge in the X-Z plane.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/FogEH.gif" data-lightbox="image-fog-extinction-hardness" data-title="Fog Extinction & Hardness">
                <img src="/assets/images/prev/FogEH.gif" alt="Fog Extinction & Hardness">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/FogCol.gif" data-lightbox="image-fog-color" data-title="Fog Color">
                <img src="/assets/images/prev/FogCol.gif" alt="Fog Color">
            </a>
        </td>
    </tr>
    <tr>
        <th>Fog Extinction & Hardness</th>
        <th>Fog Color</th>
    </tr>
</table>

* Finally the snow niagara system, wind cascade system, fog cascade system & an exponential height fog (with volumetric fog enabled) are added into a single blueprint actor to be used in the yard scene as a snowstorm system.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/SnowStormFinal.gif" data-lightbox="image-snowstorm-system" data-title="Snowstorm System">
                <img src="/assets/images/prev/SnowStormFinal.gif" alt="Snowstorm System">
            </a>
        </td>
    </tr>
</table>

## 5.0 Cable system
My next task was to come up with a physics-based cable system that was mostly to be used for cosmetic purposes in the game.

## 5.1 Cable Actors
Fortunately, Unreal comes preloaded with cable actors with rope physics for on-the-go usage. 
* These cables implement the traditional way for rope physics i.e. using a series of particles with motion constraints between them.
* The texture maps were obtained from the Quixel Megascans.
* The physics is constrained between objects that the cable is attached to them by using Physics constraint actor between the two objects.
* Cable's end is attached to any one of the objects.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Cable.gif" data-lightbox="image-cable-actors" data-title="Cable Actors">
                <img src="/assets/images/prev/Cable.gif" alt="Cable Actors">
            </a>
        </td>
    </tr>    
</table>


## 6.0 Glowing Crack Material
The team then assigned me the task to come up with materials with glowing cracks. They provided me with [references](https://assetstore.unity.com/packages/vfx/particles/spells/mesh-effects-67803#description) as well.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/gcrackref.png" data-lightbox="image-glowing-crack-material" data-title="Glowing Crack Material">
                <img src="/assets/images/prev/gcrackref.png" alt="Glowing Crack Material">
            </a>
        </td>
    </tr>    
</table>

## 6.1 Crack textures
* As the reference for the material that I was provided with was a Unity asset, I tried reverse engineering the properties of the material to recreate it in Unreal.
* I could make out that a single color channel of the base map (Albedo) was inverted and clamped between 0 and 1 and was multiplied with the emissivity input for the material.
* The single channel input texture ensured that the light emitted took grayscale values according to the base map and we could control the intensity, rate, color tint, etc through the emissivity input.
* A normal map was also used to add depth information to the cracks to make them look more realistic.
* So I imported a non-uniform galvanized metal's texture maps (base & normal) from the Quixel Bridge for this purpose.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/CrackBase.png" data-lightbox="image-crack-base-texture" data-title="Base Map">
                <img src="/assets/images/prev/CrackBase.png" alt="Base Map">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/CrackNormal.png" data-lightbox="image-crack-normal-map" data-title="Normal Map">
                <img src="/assets/images/prev/CrackNormal.png" alt="Normal Map">
            </a>
        </td>
    </tr>
    <tr>
        <th>Base Map</th>
        <th>Normal Map</th>
    </tr>
</table>


## 6.2 Emission Parameters
* The emissive color parameter of the material is governed by a time-dependent sine wave that leads to pulsating behavior by the glowing cracks.
* The sine input is given a `Rate` factor as its frequency, to control the rate of pulsation.
* Then the wave is given an offset governed by the `Pulse Intensity`. Its value is preferably kept to be greater than one to avoid negative waves (this prevents lag between the pulse cycles).
* The offseted wave function is amplified by a `Glow Intensity` factor to control the amplitude of the glow.
* Finally, the entire amplified function is multiplied by an `Emissive Color` Vector parameter which governs the color of the glow.
* The `Rate, Pulse Intensity, Glow Intensity, Emissive Color` are parametrically exposed to be controlled by the instance of that material.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/EmissionParameter.png" data-lightbox="image-emission-parameters" data-title="Emission Parameters">
                <img src="/assets/images/prev/EmissionParameter.png" alt="Emission Parameters">
            </a>
        </td>
    </tr>    
</table>

## 6.3 Emission Shape
* The base color of the material is governed by the base map of texture and a `Base Tint` Vector factor.
* The base map is blend overlayed with the `Base Tint` as the base. This ensures that whenever the blend is greater than half the grey value, it will get screened else it will get multiplied. (Every blend option was tried and the Overlay type was found to be best suited for our purpose).
* The final blend output is multiplied again with the base map and assigned to the base color of the material.
* The normal map is assigned as the material's normal as it is.
* The shape of the emission is governed by a single color channel of the base map (all three were tried and the Red channel felt the most appealing to the eyes).
* The color input is inverted using 1-x node and it is assigned a `Coverage` parameter as the exponent.
* The value is clamped between 0 and 1 and is multiplied by the amplified function obtained above and finally assigned to the emissive color property of the material. 
* The `Base Tint & Coverage` are parametrically exposed to be controlled by the instance of that material.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/EmissionShape.png" data-lightbox="image-emission-shape" data-title="Emission Shape">
                <img src="/assets/images/prev/EmissionShape.png" alt="Emission Shape">
            </a>
        </td>
    </tr>    
</table>

* A material instance of this material was created and assigned to one of the items in the game.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/Coverage.gif" data-lightbox="image-changing-coverage" data-title="Changing Coverage">
                <img src="/assets/images/prev/Coverage.gif" alt="Changing Coverage">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/GlowIntensity.gif" data-lightbox="image-changing-glow-intensity" data-title="Changing Glow Intensity">
                <img src="/assets/images/prev/GlowIntensity.gif" alt="Changing Glow Intensity">
            </a>
        </td>
    </tr>
    <tr>
        <th>Changing Coverage</th>
        <th>Changing Glow Intensity</th>
    </tr>
    <tr>
        <td>
            <a href="/assets/images/prev/PulseIntensity.gif" data-lightbox="image-changing-pulse-intensity" data-title="Changing Pulse Intensity">
                <img src="/assets/images/prev/PulseIntensity.gif" alt="Changing Pulse Intensity">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/Rate.gif" data-lightbox="image-changing-rate" data-title="Changing Rate">
                <img src="/assets/images/prev/Rate.gif" alt="Changing Rate">
            </a>
        </td>
    </tr>
    <tr>
        <th>Changing Pulse Intensity</th>
        <th>Changing Rate</th>
    </tr>
    <tr>
        <td>
            <a href="/assets/images/prev/EmissiveColor.gif" data-lightbox="image-changing-emissive-color" data-title="Changing Emissive Color">
                <img src="/assets/images/prev/EmissiveColor.gif" alt="Changing Emissive Color">
            </a>
        </td>
        <td>
            <a href="/assets/images/prev/BaseTint.gif" data-lightbox="image-changing-base-tint" data-title="Changing Base Tint">
                <img src="/assets/images/prev/BaseTint.gif" alt="Changing Base Tint">
            </a>
        </td>
    </tr>
    <tr>
        <th>Changing Emissive Color</th>
        <th>Changing Base Tint</th>
    </tr>
</table>

## 7.0 Loading Screen
I decided to switch my role to explore the track of a tech designer. I was assigned the task to design a loading screen for the various scene transitions in the game. 

## 7.0 Widget
* A 16:9 widget was created to serve as the lock screen. 
* A [video](https://drive.google.com/file/d/1AEvD9Qi2J3TZTnRo6RIspSqx6nZX-jSQ/view) was provided to be used as the background for the lock screen.
* Since Unreal Engine doesn't support Video files for Widget as is, I had to do a workaround. I imported the video as a media player and created a video texture out of it. Then I created a material with UI domain that could be used in the widget as an Image. (Image in widgets support the use of materials as a brush)
* The video was looped and precached to avoid any frame drops in between each loop.
* The default Rendering Hardware Interface was changed to DirectX11 as Vulkan/DirectX12 eventually failed to cache the video and led to a black screen.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/loadscrmat.gif" data-lightbox="image-widget-video-material" data-title="Video UI Material">
                <img src="/assets/images/prev/loadscrmat.gif" alt="Video UI Material">
            </a>
        </td>
    </tr>
    <tr>
        <th>Video UI Material</th>
    </tr>
</table>

## 7.1 Progress Bar
The team wanted me to implement a progress bar whose colors can be controlled by us in the engine. Apart from this, the progress bar's progress was to be linked with the amount of level content and lighting information was loaded in the level.

* I used the Progress Bar prefab provided by the Unreal Engine in the Widget Palette as the base. 
* The progress percentage was bound with the `GetAsyncLoadPercentage` with an upper clamp on the timing. 
* A custom sprite was used for the progress bar as well.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/progressbarbp.png" data-lightbox="image-progress-bar" data-title="Progress Bar Blueprint">
                <img src="/assets/images/prev/progressbarbp.png" alt="Progress Bar Blueprint">
            </a>
        </td>
    </tr>    
</table>

## 7.2 Tips System
Next, we decided upon implementing a tips system that would show up random tips on the widget while the level is loading. 

* A semi-transparent black box was used as the container for the textbox of the tips that would come randomly.
* DCC font was used for the text to keep it seamless with the game.
* The text was randomly chosen from an array of strings and was set to switch to another string after a threshold time.
* The sound designers even went on to implement a narration system that read out the tips that came out on the screen.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/tipbp.png" data-lightbox="image-tips-system" data-title="Tips System Blueprint">
                <img src="/assets/images/prev/tipbp.png" alt="Tips System Blueprint">
            </a>
        </td>
    </tr>    
</table>

## 7.3 Widget & Level Blueprint
* The widget was added to the viewport of the screen when a new level was opened. 
* It was made to wait for `GetAsyncLoadPercentage` to get to 100, and then a prompt was shown to press any key (cross-platform) to disable the widget and open the newly loaded level. The blueprint was made to wait for a threshold time in case the level took too long to load. 
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/lswidget.png" data-lightbox="image-widget-and-level-blueprint" data-title="Widget & Level Blueprint">
                <img src="/assets/images/prev/lswidget.png" alt="Widget & Level Blueprint">
            </a>
        </td>
    </tr>    
</table>

## 7.4 Final Touches
* All the widgets and elements were animated To give a more professional look.
* The game's logo was added in the center and was made to fade into a text prompt that asked the players to press a key to continue once the level had been loaded.
<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/prev/LoadingScreen.gif" data-lightbox="image-final-touches" data-title="Final Touches">
                <img src="/assets/images/prev/LoadingScreen.gif" alt="Final Touches">
            </a>
        </td>
    </tr>    
</table>