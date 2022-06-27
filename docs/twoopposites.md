---
layout: default
---

## Two Opposites
Two opposites is a game about the journey of two opposites (characters with mirrored controls) separated by a mirror. They need to solve puzzles to escape the mirror world and finally meet each other. However, the challenge lies in the fact that they can only solve these puzzles together. You can play it in your browser [here](https://makra.itch.io/two-opposites) <br><br>
The game was made in a week (by three of us) for the Brackeys Game Jam (participated by 10k+ people worldwide) and ranked #22 in the innovation category. <br><br>

<img src="../files/TwoOppLogo.png" style="width:100%">

## 2D Lighting System
We had decided that the atmosphere was to be given the most priority while developing this game. And the visual appeal of the game played a major role in that. Back when we started working upon this project, Unity didn't have any render pipeline that supported 2D lighting. So my task was to develop a 2D lighting system for the game.

### 2D Raycaster (GL)
* The basic idea was to draw transparent lines originating radially outwards from a sprite with negligible separation to give a sense of light coming out.
* I used the Unity's low level [Graphics Library (gl)](https://docs.unity3d.com/ScriptReference/GL.html) to draw lines between two points.
* The raycast loop- <br><br>

<img src="../files/raycast_loop.png" style="width:100%"> <br><br>

* This loop draws rays from the player's position (which is exposed in the inspector) to equally spaced points around the player.
* The angle that light covers is governed by theta (which is exposed in the inspector).
* The spacing between each ray is governed by steps (which is exposed in the inspector).
* The color of the rays is governed by col (which is exposed in the inspector).
* The length of light ray is governed by maxVisiblityDistance (which is exposed in the inspector).
* This script is attached to the MainCamera and the loop is called in OnPostRender() so that the lines are rendered as soon as the camera finishes rendering the scene.

<table border="0">
 <tr>
    <td><img src="../files/theta.gif" style="width:100%"></td>
    <td><img src="../files/steps.gif" style="width:100%"></td>
 </tr>
 <tr>
    <td>Changing theta</td>
    <td>Changing steps</td>
 </tr>
</table>

<table border="0">
 <tr>
    <td><img src="../files/col.gif" style="width:100%"></td>
    <td><img src="../files/maxvdist.gif" style="width:100%"></td>    
 </tr>
 <tr>
    <td>Changing color</td>
    <td>Changing max visibility distance</td>
 </tr>
</table>

### Ray Material
* My next task was to make the light rays feel more natural by introducing transparency.
* Upon some pondering I found that GL library by default uses the Unlit material provided by Unity to create the lines.
* As the unlit material doesn't support transparency, I wrote an unlit shader that supported both transparency and vertex colors.
* The RGBA values of the colors of the material based upon this shader was passed as an input. <br>

<img src="../files/RGBA.png" style="width:100%">

* With transparency controls the rays looked much natural. <br>

<img src="../files/TRays.gif" style="width:100%">

### Environment Lighting