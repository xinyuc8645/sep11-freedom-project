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

### 11/10/25 Still Learning Very Much
<ul>
  <li>Last time left off at tutorial in camera;still continue off of camera</li>
  <li>Viewport in Phaser:</li>
  <li>Base from the documentation, the viewport in phaser is, an camera's "Window" or the visible area in which the player actually sees
    <li>Key properties include:</li>
  <li>x and y position one; x is left edge of the viewport, y is the top edge of the viewport</li>
  <li>Width, and height; self explantory</li>
  <li>CenterX and centerY, centerX is horizontal center of the viewport and centerY is the vertical center of the viewport</li>
  <li>It's purpose:Can be moved, centered and resized, and also defines the visible area of the game in which the player sees</li>
  <li>An code for this:</li>
  
```js
  this.cameras.main.setViewport(0, 0, 400, 300);
```
<li>What this do is this: sets the position of both x and y to 0 and the width being 400 and the height of 300</li>
<li>This code can be used by only camera size, height, position and viewport and etc</li>
<li>Worldview</li>
<li>Worldview is the area in which the game world that the camera sees currently or can "see"; it depends on the camera rotation, zoom and others</li>
<li>What's the difference between worldview and viewport?: Think of it like this, viewport is the window frame, and worldview is the the part of area you can see through, that window</li>
<li>Usage of worldview</li>
<li>Helps determine what part of the game is visible, useful for tracking visibility detectio of collision</li>
<li>Some codes for it are: Getting the displayed height and the midpoint</li>

```js
var x = camera.midPoint.x;
var y = camera.midPoint.y;
```

</ul>

### 11/10/24 Cameras..Still?
<ul>
  <li>I know I know there for the past 3 or 2 learning log I've been talking and documentating about cameras within the phaser, however after this learning log I promise no more cameras, we'll move on to something new</li>
  <li>Topic: Cameras;Visibility/Input</li>
  <li>What is visibility in camera for phaser? Well to to put it in simple words bascially, whether the camera will be able to show's currently what's on ths screen and if the camera is visible then, it can render the scene</li>
  For example this code 
  
  ```js
  var visible = camera.visible;
  ```
<li>Makes the camera visible,however how do turn it off and off?</li>

```js
camera.setVisible(true);
```
<li>This makes the camera value true meaning its visible</li>

```js
camera.setVisible(false);
```
<li>This makes the camera value false meaning its not visible</li>
<li>Remember, an visible camera RENDERS the scene whereas an invisible camera does NOT render the scene</li>
<li>You can also set an background color for the camera by using this code:</li>

```js
camera.setBackgroundColor(blue);
//makes the background color of the camera blue
```
<li>What if I want to render in an certain scene, however an existing object within that scene isn't neccessary and I want it out completely but at the same time I don't want to make my camera invisible so how can I ignore that object? Well...</li>

```js
camera.ignore(gameObject);
```
<li>This code ignores an certain game object within the scene; the object can either be an game object, array of them</li>
</ul>




<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
