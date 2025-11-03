# Tool Learning Log

## Tool: Phaser

## Project: An game like Duck Life..

---

### 9/29/25: Getting started
<ul>
<li>From the website doc for <a href= "https://docs.phaser.io/phaser/getting-started/installation">phaser installing</a>  the cdn link is in the following:</li>

  ```js
<script src="//cdn.jsdelivr.net/npm/phaser@3.86.0/dist/phaser.js"></script>
<script src="//cdn.jsdelivr.net/npm/phaser@3.86.0/dist/phaser.min.js"></script>
```
<li>Have to include either one in my html from my ide</li>
<li>Ok so, base off of, the youtube videos I've watched many codes from phaser including basic tutorials has to be basically downloaded and get the code from that template, because you cannot just randomly create a code with no knowledge.</li>
<li>Refer back to this <a href= "https://www.youtube.com/watch?v=iqMIGGy5YiE&list=PLmcXe0-sfoShHpVWLDW2gqsyH1UFRni_2">youtube video</a>
For now, I'll be studying and testing my tool for basics; refer back to the video playlist of <a href= "https://www.youtube.com/watch?v=gFXx7lgxK9A&list=PLDyH9Tk5ZdFzEu_izyqgPFtHJJXkc79no&index=2">"Phaser Tutorials"</a>
<li>For configuring a shape, in this case or something, and wanting to adjust height, weight just type height: and weight:</li>
<li>Create a variable called </li>

```js
var configuration {
height: 100,
weight: 500,
}
```
<li>Basically just like the html code,  but in js we have to create a variabble, so we can modify it.</li>
<li>And we save all of that code into the game scenes</li>

```js
var newGame = Phaser.game(configuration);
```
  
</ul>

### 10/27/25 Learning...
<ul>
  <li>Instead of following the youtube tutorials since it's mostly on game creation, instead I will be following the Phaser Documentations tutorials</li>
  <li>Starting from: <a href= "https://docs.phaser.io/phaser/concepts/cameras">Tutorial</a></li>
  <li>Camera in Phaser can either destroyed, created and others</li>
  <li>You can access an camera manager using the code of 
    
  ```js
    var camera = this.cameras.main;
  ```
<li>This camera is already created by phaser meaning you can modify it however you want</li> 
</li>
<li>Also managed to mess around with the camera to have an specific size, and position for example:
  
  ```js
var newCamera = this.cameras.add(60, 40, 250, 400);
```
<li> The first two, coordinates with in the brackets () are the x and the y position and the last two is the width and height</li>
</li> Basically, its 250x wide, 400 tall and located somewhere around the top left corner of the IDE</li>
<li>A more in-depth about the x and y positioning of camera</li>

```js
var top = camera.x;
var left = camera.y;
```
<li>This code determines the position of the camera. For example: x represents the horizontal position whereas the y represents the vertical position. (ONLY for top left angle)

```js
this.cameras.addExisting(camera);
``` 
<li>This camera code allows you to add an camera, which already exited on top of it. So that the current scene you created, can both recongize it and both use it</li>
<li>Whats the different between</li>

```js 
this.cameras.remove(camera);
```
<li>and</li>

```js
camera.destroy();
```
<li>Since doesn't both remove the camera? Or does it mean one removes the camera temporarily and the other one removes it completely?</li>
</ul>




<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
