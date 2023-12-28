Created a Spongebob VR experience in Unreal Engine 5 with a team of 4 artists. I was responsible for the lighting, post-processing, animation state machines, rigging and the overall blueprinting of the project.

  <center>
  <video controls loop style="width: 90%; border: 3px solid black; border-radius: 15px;">
    <source src="/assets/images/spongebobvr0.mp4" type="video/mp4">
  </video>
  </center>

**Proxy Pass**<br>
This week I worked on-
* Enhancing the visual aesthetics of the scene through lighting and post-processing effects to give it a blue underwater ambience.
* Rigging and creating the animation state machine for the SpongeBob hands.
* Creating the animation state machine for the breaking animation of the SpongeBob hands.
* Setting up trigger volumes to initiate the breaking animation of the SpongeBob hands.
* Creating parent materials for the scene and props to make them modular.
* Placing the navmesh for teleportation.

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/envlight1.png" data-lightbox="env-light" data-title="env light 1">
                <img src="/assets/images/sb/envlight1.png" alt="env light 1">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/envlight2.png" data-lightbox="env-light" data-title="env light 2">
                <img src="/assets/images/sb/envlight2.png" alt="env light 2">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Environment Lighting</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/reeeg.png" data-lightbox="rig" data-title="Rig">
                <img src="/assets/images/sb/reeeg.png" alt="Rig">
            </a>
        </td>        
    </tr>
    <tr>
        <th style="text-align: center;">Rigged Spongebob hands</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/abp_1.png" data-lightbox="abp-sb" data-title="ABP 1">
                <img src="/assets/images/sb/abp_1.png" alt="ABP 1">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/abp_2.png" data-lightbox="abp-sb" data-title="ABP 2">
                <img src="/assets/images/sb/abp_2.png" alt="ABP 2">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Animation Blueprint</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/brktrigger.png" data-lightbox="break-trigger" data-title="Break Trigger">
                <img src="/assets/images/sb/brktrigger.png" alt="break-trigger">
            </a>
        </td>        
    </tr>
    <tr>
        <th style="text-align: center;">Break Trigger</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/mat.png" data-lightbox="parent-material" data-title="Parent Material">
                <img src="/assets/images/sb/mat.png" alt="parent-material">
            </a>
        </td>        
    </tr>
    <tr>
        <th style="text-align: center;">Parent Material</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/navm.png" data-lightbox="navmesh" data-title="Navmesh">
                <img src="/assets/images/sb/navm.png" alt="Navmesh">
            </a>
        </td>        
    </tr>
    <tr>
        <th style="text-align: center;">Navmesh</th>       
    </tr>
</table>

**Clean Pass**<br>
This week I worked on-
* Fixing the physics collisions between objects.
* Fixing the teleportation mechanic.
* Doing a second pass on the lighting.
* Implementing grabbing and snapping of props.

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/telep.png" data-lightbox="teleportation" data-title="Teleportation">
                <img src="/assets/images/sb/telep.png" alt="Teleportation">
            </a>
        </td>        
    </tr>
    <tr>
        <th style="text-align: center;">Fixing collision and teleprtation mechanic</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/light1.png" data-lightbox="clean-light-sb" data-title="clean light">
                <img src="/assets/images/sb/light1.png" alt="clean light">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/light2.png" data-lightbox="clean-light-sb" data-title="clean light">
                <img src="/assets/images/sb/light2.png" alt="clean light">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Second Lighting Pass</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/grab.png" data-lightbox="grab-sb" data-title="grab">
                <img src="/assets/images/sb/grab.png" alt="grab">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/snap.png" data-lightbox="snap-sb" data-title="snap">
                <img src="/assets/images/sb/snap.png" alt="snap">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Grab & Snap for Props</th>       
    </tr>
</table>

**Environment Final Pass**<br>
This week I worked on-
* Final pass on the lighting by simulating fake lighting using emissive materials.
* A blueprint to open and close the cabinet.
* Final pass on the animation blueprints to fix the hand breaking upon trigger.
* Fixing the spatula grab pose using animation state machine.
* Final pass on the modular parent material for the scene and props. 

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/light3.png" data-lightbox="fin-light" data-title="Final Lighting">
                <img src="/assets/images/sb/light3.png" alt="Final Lighting">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/light4.png" data-lightbox="fin-light" data-title="Final Lighting">
                <img src="/assets/images/sb/light4.png" alt="Final Lighting">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/light5.png" data-lightbox="fin-light" data-title="Final Lighting">
                <img src="/assets/images/sb/light5.png" alt="Final Lighting">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="3" style="text-align: center;">Final Lighting Pass</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/door.png" data-lightbox="door-open-close" data-title="Door Open & Close">
                <img src="/assets/images/sb/door.png" alt="door-open-close">
            </a>
        </td>        
    </tr>
    <tr>
        <th style="text-align: center;">Door Open & Close Blueprint</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/a1.png" data-lightbox="abp-fin-sb" data-title="ABP Fin 1">
                <img src="/assets/images/sb/a1.png" alt="ABP Fin 1">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/a2.png" data-lightbox="abp-fin-sb" data-title="ABP Fin 2">
                <img src="/assets/images/sb/a2.png" alt="ABP Fin 2">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Final Pass - Animation Blueprint</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/spat.png" data-lightbox="spat-fix" data-title="Spatuala Fix">
                <img src="/assets/images/sb/spat.png" alt="spat-fix">
            </a>
        </td>        
    </tr>
    <tr>
        <th style="text-align: center;">Spatula Fix</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/mat1.png" data-lightbox="mat-fin-sb" data-title="Mat Fin 1">
                <img src="/assets/images/sb/mat1.png" alt="Mat Fin 1">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/mat2.png" data-lightbox="mat-fin-sb" data-title="Mat Fin 2">
                <img src="/assets/images/sb/mat2.png" alt="Mat Fin 2">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Final Pass - Modular Parent Material</th>       
    </tr>
</table>

**Character Final Pass**<br>
This week I worked on-
* Animation blueprint of all the characters.
* Animation state machine of all the characters.
* Added behaviour to the sauce bottle.
* Added audio triggers in the scene.
* Worked on Fluid VFX which somehow didn't work in VR. 

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/abp_krabs.png" data-lightbox="char-abp-sb" data-title="Character ABP 1">
                <img src="/assets/images/sb/abp_krabs.png" alt="Character ABP 1">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/abp_plankton.png" data-lightbox="char-abp-sb" data-title="Character ABP 2">
                <img src="/assets/images/sb/abp_plankton.png" alt="Character ABP 2">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/plank2.png" data-lightbox="char-abp-sb" data-title="Character ABP 3">
                <img src="/assets/images/sb/plank2.png" alt="Character ABP 3">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="3" style="text-align: center;">Character Animation Blueprints & Animation State Machines</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/aud.png" data-lightbox="aud-trigger-sb" data-title="Audio Trigger 1">
                <img src="/assets/images/sb/aud.png" alt="Audio Trigger 1">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/aud2.png" data-lightbox="aud-trigger-sb" data-title="Audio Trigger 2">
                <img src="/assets/images/sb/aud2.png" alt="Audio Trigger 2">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="2" style="text-align: center;">Audio Triggers</th>       
    </tr>
</table>

<table class="custom-table">
    <tr>
        <td>
            <a href="/assets/images/sb/fluid_1.png" data-lightbox="fluid-sb" data-title="Fluid 1">
                <img src="/assets/images/sb/fluid_1.png" alt="Fluid 1">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/fluid_2.png" data-lightbox="fluid-sb" data-title="Fluid 2">
                <img src="/assets/images/sb/fluid_2.png" alt="Fluid 2">
            </a>
        </td>
        <td>
            <a href="/assets/images/sb/sos.png" data-lightbox="fluid-sb" data-title="Fluid 3">
                <img src="/assets/images/sb/sos.png" alt="Fluid 3">
            </a>
        </td>
    </tr>
    <tr>
        <th colspan="3" style="text-align: center;">Fluid VFX</th>       
    </tr>
</table>
