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
* The raycast loop-
```
for (float i = 0; i < theta; i += steps)
{
    GL.Begin(GL.LINES);
    GL.Color(col); //Initializing GL Library with white color as input

    GL.Vertex3(transform.position.x, transform.position.y, 0); //starting point

    GL.Vertex3(player.transform.position.x+ Mathf.Cos(i * Mathf.Deg2Rad)* maxVisiblityDistance, player.transform.position.y + Mathf.Sin(i * Mathf.Deg2Rad)* maxVisiblityDistance, 0); //ending point

    GL.End(); //clearing garbage
}
```
* This loop draws rays from the player's position to equally spaced points around the player.
* The angle that light covers is governed by *theta* (which is exposed in the inspector).
* The spacing between each ray is governed by *steps* (which is exposed in the inspector).
* The color of the rays is governed by *col* (which is exposed in the inspector).

