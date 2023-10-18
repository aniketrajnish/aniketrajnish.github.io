## Games for community
Took burts of week-long project to publish a game in a week for my undergraduate college community to play and compete in. The competion was known as PlayPro and saw participation by 400+ people for each game. I published the following games for this purpose. For these games I implemented an leaderboard using dreamlo:

**1. Banana Warrior**

**2. Fertilize.io**

**3. 2048 Jelly**

**4. Toilet Spinner**

**5. Chrome Dino Remastered**

**6. Return To Monke**

**7. Obamium Maker**

*Update: Most of these apps were removed from the Play Store as they used a deprecated Unity Ads SDK that didn't align with the store's policy.  Remember, don't be greedy, folks!*

## Soul Shard
* Provided assistance in shader & gameplay programming, and the development of particle & VFX systems.
* Developed a dynamic footprint system for main characters and VFX effects such as stylized fire, smoke, debris, and flames.
* Created a dynamic snowstorm system and implemented rope physics for cables, as well as a dynamic loading screen for various scene transitions.
* Curated development logs and documentation about my contribution that can be found [here](/works/fiea-summer/). 

## Optimized Bullet-Time Destruction Pipeline in Unity

## Front Flip Animation State Machine & IK Rig in Unreal Engine

## Project Holly
Created an interactive movie experience using Unity. For this project, I developed an asset that allows one to stream a video in small chunks accroding to the user's choices. This allows you to take control of the characters and make choices on not only the direction of the narrative of the film but also fine control on the character's movement.

## Mathematical Model for Rendering using Gaussian Elimination
Mathematically modeled and implemented a 3D rendering technique that uses numerical methods to calculate the intersection of planes and render 3D objects. Extended this approach to render the 3D projection of [4D hypercubes](https://github.com/aniketrajnish/4d-rendering-ma202-project).

## ASCII Line Art

* Made ASCII Line art for all my dear professors and mentors on Teacher's Day.
* I made 52 of these in total.
<table class="custom-table" style="width: 100%;">
    <tr>
        <td style="text-align: center;">
            <a href="/assets/images/prev/CHRIS_SIR.png" data-lightbox="image-4" data-title="Chris Sir">
                <img src="/assets/images/prev/CHRIS_SIR.png" alt="Chris Sir">
            </a>
            <br>
            <strong>Chris Sir</strong>
        </td>
        <td style="text-align: center;">
            <a href="/assets/images/prev/RICK_SIR.png" data-lightbox="image-5" data-title="Rick Sir">
                <img src="/assets/images/prev/RICK_SIR.png" alt="Rick Sir">
            </a>
            <br>
            <strong>Rick Sir</strong>
        </td>
        <td style="text-align: center;">
            <a href="/assets/images/prev/RON_SIR.png" data-lightbox="image-6" data-title="Ron Sir">
                <img src="/assets/images/prev/RON_SIR.png" alt="Ron Sir">
            </a>
            <br>
            <strong>Ron Sir</strong>
        </td>
    </tr>
</table>

* These were made using [p5js](https://p5js.org/) by detecting changes in the overall RGB values of different parts of images.
    ```
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
    ```

* If you zoom onto the images (by clicking on them), you'll find out that the pixels of the images are converted into letters of the name of the person that it's made for.
* Many of these images were converted into DXF format and engraved on acrylic sheets to be gifted to the professors.
<table class="custom-table" style="width: 100%;">
    <tr>
        <td style="text-align: center;">
            <a href="/assets/images/prev/Collage_LineArt.png" data-lightbox="image-7" data-title="Engraved Images">
                <img src="/assets/images/prev/Collage_LineArt.png" alt="Engraved Images">
            </a>
            <br>
            <strong>Engraved Images</strong>
        </td>
    </tr>
</table>

## Procedural Generation of 3D space from 2D map using Raycasts
Developed a 3D Renderer in Scratch using principles of raycasting, with features such as varying FOV  and shadow-mapping. Any 2D map input gets converted into a procedurally generated 3D world.

## Unity First!
Tried using Unity & Blender for most of my assignments instead of softwares like AutoCAD and Matlab.

## Tried Proving CodeParade wrong :3
* I worked on various Non-Euclidean world simulations inside of Unity, especially after CodeParade announced that [it’s technically impossible to develop Non-Euclidean worlds in Unity without low-level access to its Rendering Engine](https://youtu.be/kEB11PQ9Eo8?t=233).
* The first simulation consisted of cameras rendering over a render texture in the opening of a tunnel and colliders that teleported the player between different worlds seamlessly, offering a non-euclidean illusion.

## Made a go-kart!!

## VFX and Edits
