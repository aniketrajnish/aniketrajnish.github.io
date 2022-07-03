---
layout: default
---

## Two Opposites
Two opposites is a game about the journey of two opposites (characters with mirrored controls) separated by a mirror. They need to solve puzzles to escape the mirror world and finally meet each other. However, the challenge lies in the fact that they can only solve these puzzles together. You can play it in your browser [here](https://makra.itch.io/two-opposites) <br><br>
The game was made in a week (by three of us) for the Brackeys Game Jam (participated by 10k+ people worldwide) and ranked #22 in the innovation category. <br>

<a href="../files/TwoOppLogo.png" data-lightbox="twoOpposites" data-title="Two Opposites"><img src="../files/TwoOppLogo.png" style="width:100%"></a>

### 2D Lighting System
We had decided that the atmosphere was to be given the most priority while developing this game. And the visual appeal of the game played a major role in that. Back when we started working upon this project, Unity didn't have any render pipeline that supported 2D lighting. So my task was to develop a 2D lighting system for the game.

### 2D Raycaster (GL) - 1st iteration
* The basic idea was to draw transparent lines originating radially outwards from a sprite with negligible separation to give a sense of light coming out.
* I used the Unity's low level [Graphics Library (gl)](https://docs.unity3d.com/ScriptReference/GL.html) to draw lines between two points.
* The raycast loop- <br><br>

<a href="../files/raycast_loop.png" data-lightbox="raycastloop" data-title="Raycast Loop"><img src="../files/raycast_loop.png" style="width:100%"></a> <br><br>

* This loop draws rays from the player's position (which is exposed in the inspector) to equally spaced points around the player.
* The angle that light covers is governed by theta (which is exposed in the inspector).
* The spacing between each ray is governed by steps (which is exposed in the inspector).
* The color of the rays is governed by col (which is exposed in the inspector).
* The length of light ray is governed by maxVisiblityDistance (which is exposed in the inspector).
* This script is attached to the MainCamera and the loop is called in OnPostRender() so that the lines are rendered as soon as the camera finishes rendering the scene.

<table border="0">
 <tr>
    <td><a href="../files/theta.gif" data-lightbox="parameters" data-title="Changing theta"><img src="../files/theta.gif" style="width:100%"></a></td>
    <td><a href="../files/steps.gif" data-lightbox="parameters" data-title="Changing steps"><img src="../files/steps.gif" style="width:100%"></a></td>
 </tr>
 <tr>
    <td>Changing theta</td>
    <td>Changing steps</td>
 </tr>
</table>

<table border="0">
 <tr>
    <td><a href="../files/col.gif" data-lightbox="parameters" data-title="Changing color"><img src="../files/col.gif" style="width:100%"></a></td>
    <td><a href="../files/maxvdist.gif" data-lightbox="parameters" data-title="Changing max visibility distance"><img src="../files/maxvdist.gif" style="width:100%"></a></td>    
 </tr>
 <tr>
    <td>Changing color</td>
    <td>Changing max visibility distance</td>
 </tr>
</table>

### Ray Material
* The next task ahead to make the light rays feel more natural by introducing transparency.
* Upon some pondering I found that GL library by default uses the Unlit material provided by Unity to create the lines.
* As the unlit material doesn't support transparency, I wrote an unlit shader that supported both transparency and vertex colors.
* The RGBA values of the colors of the material based upon this shader was passed as an input. <br>

<a href="../files/RGBA.png" data-lightbox="rgba" data-title="RGBA Input"><img src="../files/RGBA.png" style="width:100%"></a>

* With transparency controls the rays looked much natural. <br>

<a href="../files/TRays.gif" data-lightbox="rgba" data-title="Light looks more natural"><img src="../files/TRays.gif" style="width:100%"></a>

### Environment Lighting
* The next step would be to make the environment around react to the light rays emitted by the player.
* This would involve two steps-

1. Making the light ray stop when it hits an object. This is done by raycasting along the light rays that GL draws and checking if we've hit something.
<a href="../files/RaycastHit.png" data-lightbox="envlight" data-title="Stopping if we hit something"><img src="../files/RaycastHit.png" style="width:100%"></a>
2. Making the sprite color of the object depend upon its distance from the light source.
<a href="../files/spritecol.png" data-lightbox="envlight" data-title="Sprite color dependent on distance from light source"><img src="../files/spritecol.png" style="width:100%"></a>

### Final Output
<a href="../files/2dlightsys.gif" data-lightbox="finalenvlight" data-title="Natural Light with dynamic environment reacting to it"><img src="../files/2dlightsys.gif" style="width:100%"></a>

### 2D Raycaster (GL) - 2nd iteration
* The previous method for generating rays was very inefficient with a time complexity of O(n) as the loop had to run 3600 times every frame with a step size of 0.1.
* This issue was tackled by detecting the edges of nearby objects and casting rays at them and then filling the space between them by generating mesh between them. <br><br>
<a href="../files/mesh2dlight.png" data-lightbox="mesh2dlight" data-title="Detecting the edges of nearby objects and generating mesh between them."><img src="../files/mesh2dlight.png" style="width:100%"></a>

### Final Output
<a href="../files/2dmeshlightsys.gif" data-lightbox="finalmesh2dlight" data-title="Looks exactly like individual rays"><img src="../files/2dmeshlightsys.gif" style="width:100%"></a>

### Environment Reflection
* Two players (each with their own top down camera) were added in either sides of the map separated by a box collider.
* The screen was split into two (one for each camera) by decreasing the width of the both camera's viewport rect to 0.5 and offsetting one of them to 0.5.

### Player Movement 
* A simple rigidbody top down controller was yoinked from one of Brackeys tutorials for the first player.
* While the movement of the second player was made to be governed by that of the first player's. <br>
<a href="../files/inversion.png" data-lightbox="inversion" data-title="Movement Lateral Inversion"><img src="../files/inversion.png" style="width:100%"></a>
* This inverts the movement of the second player horizontally (lateral inversion) as if their movements were mirrored.
<a href="../files/inversion.gif" data-lightbox="inversion" data-title="Output on inverted movement."><img src="../files/inversion.gif" style="width:100%"></a>

### Player Sprites & Animations
* Two sprite sheets of the top-down view of a male & female character (drawn by one of my teammates) walking were imported into the game. 
* These sprites were split into frames for animation using Unity's inbuilt sprite editor.

<table border="0">
 <tr>
    <td><a href="../files/BoySprite.png" data-lightbox="ss" data-title="Boy Sprite Sheet"><img src="../files/BoySprite.png" style="width:100%"></a></td>
    <td><a href="../files/GirlSprite.png" data-lightbox="ss" data-title="Girl Sprite Sheet"><img src="../files/GirlSprite.png" style="width:100%"></a></td>    
 </tr>
 <tr>
    <td>Boy Sprite Sheet</td>
    <td>Girl Sprite Sheet</td>
 </tr>
</table>

* These were then animated at 10 fps.
* The controller was tweaked to support both animation and smooth rotation of the player sprites.
<a href="../files/newmov.png" data-lightbox="newmov" data-title="New Player Controller"><img src="../files/newmov.png" style="width:100%"></a>

* The translation is governed by Unity's Physics engine (using rigidbodies) and is executed in the FixedUpdate() method to keep keep it independent of frame rate.
* The rotation of the sprite changes with its movement direction (governed by the combination of vertical and horizontal input).
* The translation and rotation speed is parametrically controlled by speed and rotSpeed variable exposed in the inspector.
* The animation is simply enabled if we're sending an input, else it stays disabled. <br><br> 
<a href="../files/Sprites.gif" data-lightbox="newmovoutput" data-title="New Player Movement with Animations"><img src="../files/Sprites.gif" style="width:100%"></a>

### Button Mechanic
We decided upon a coming up with a button mechanic system. The idea was to spawn two buttons (one in each world) and the player was expected to walk over both the buttons simultaneously two open gates so that people can people can proceed to the next level.
* When the player walked over a button, the button's sprite renderer was made to glow.
* Also, an event was called to check if the other button is pressed as well.
* If the other button was pressed, the gates (which were hinged at their corner) would rotate and the player could pass through them. <br><br>
<a href="../files/Buttons.gif" data-lightbox="btn" data-title="Button Mechanic"><img src="../files/Buttons.gif" style="width:100%"></a>

### Pushable Objects
To add more depth to the puzzles, we decided to come up with a few objects that the players could push in order to block or press something. 
* A physics material (with high coefficient of friction value & 0 bounciness) is created.
* Sprites for pushable objects (with hand-drawn texture maps by one of the teammates) are imported.

<table border="0">
 <tr>
    <td><a href="../files/crate.png" data-lightbox="crate" data-title="Crate base map"><img src="../files/crate.png" style="width:100%"></a></td>
    <td><a href="../files/cratenormal.jpg" data-lightbox="crate" data-title="Crate normal map"><img src="../files/cratenormal.jpg" style="width:100%"></a></td>    
 </tr>
 <tr>
    <td>Crate base map</td>
    <td>Crate normal map</td>
 </tr>
</table>

* These textures are assigned to the URP's default lit sprite material.
* Their prefabs are created with Box Collider 2D & Rigidbody 2D components having the physics material assigned to them. <br><br>
<a href="../files/Pushable.gif" data-lightbox="pushable" data-title="Pushable Objects"><img src="../files/Pushable.gif" style="width:100%"></a>

### Death Mechanic
We decided to include spikes in the game. They would kill the the players on contact, rendering few areas of the game as unapproachable. We decided to keep the death animations and effect as brutal and gross (taking inspiration from Limbo) to add to the dark atmosphere of the game.

* Colliders were set up on the spikes (with 'Death' tag) and the player.
* If the player came in contact with the spike a Coroutine containing all the relevant methods for death of the player was called.

<a href="../files/death2opp.png" data-lightbox="death" data-title="Death Logic"><img src="../files/death2opp.png" style="width:100%"></a>

### Spike Texture
* Since our core idea was to make the game atmospheric & appealing to the eyes we wanted to keep environment ques pretty detailed. We decided to do the same with the spikes.
* The spike texture maps were hand-drawn by one of the teammates. We had initially thought of including a height/bump map but later replaced it with a normal map.

<table border="0">
 <tr>
    <td><a href="../files/spikes.png" data-lightbox="spike" data-title="Spike base map"><img src="../files/spikes.png" style="width:100%"></a></td>
    <td><a href="../files/SpikesNormal.png" data-lightbox="spike" data-title="Spike normal map"><img src="../files/SpikesNormal.png" style="width:100%"></a></td>
    <td><a href="../files/spike height.png" data-lightbox="spike" data-title="Spike height map"><img src="../files/spike height.png" style="width:100%"></a></td>    
 </tr>
 <tr>
    <td>Spike base map</td>
    <td>Spike normal map</td>
    <td>Spike height map</td>
 </tr>
</table>

* These textures are assigned to the URP's default lit sprite material.

### Death Animation
* A sprite sheet for hand=drawn animation of blood splash was imported.

<a href="../files/BloodSplash.png" data-lightbox="bloodsplash" data-title="Blood Splash sprite sheet"><img src="../files/BloodSplash.png" style="width:100%"></a>

* This sprite sheet was played upon collision with the spikes.
* The movement state of the players were changed from animated to static.
* The movement vector of the players were overridden to be zero.
* The canvas was fade out to black and the level was reloaded.

<a href="../files/death2oppcor.png" data-lightbox="deathlogic" data-title="Death Coroutine"><img src="../files/death2oppcor.png" style="width:100%"></a>

### Final Ouptut
<a href="../files/death2opp.gif" data-lightbox="deathoutput" data-title="Death"><img src="../files/death2opp.gif" style="width:100%"></a>

### Level Design

### Game UI & UX
For the game UI, we decided to keep it minimal and match the atmospheric tone of the game. 

### Font
* We browsed through a bunch of hand-drawn fonts for the game's UI. 
* We shortlisted to Architects Daughter, Amatic, and Blokletters and finalized Amatic in the end due to the 
* The colors were kept minimal and preferably lerped between black and white. <br><br>
<a href="../files/amatic.png" data-lightbox="font" data-title="Amatic font"><img src="../files/amatic.png" style="width:100%"></a>

### Animations
* The animations were kept minimal - fading, scaling, and translations. 
* A canvas with black panel was used as an overlay and it was used for fading transitions between different scenes and menus.

<table border="0">
 <tr>
    <td><a href="../files/menuanim.gif" data-lightbox="menuanim" data-title="Main Menu"><img src="../files/menuanim.gif" style="width:100%"></a></td>
    <td><a href="../files/pausemenu.gif" data-lightbox="pausemenuanim" data-title="Pause Menu"><img src="../files/pausemenu.gif" style="width:100%"></a></td>
 </tr>
 <tr>
    <td>Main Menu</td>
    <td>Pause Menu</td>
 </tr>
</table>

### Intro clip
* We created a small clip using Unity's timeline as the menu felt a little lifeless. Again, minimalism and dark atmosphere were the key. <br>

<a href="../files/mainmenu.gif" data-lightbox="mm" data-title="Main Menu Final"><img src="../files/mainmenu.gif" style="width:100%"></a>

### Music 


