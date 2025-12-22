# Entry 2
##### 12/21/25

# Context
Alright, for this blog, we'll be mainly exploring cameras, viewport and visibility within phaser. I think for the past 3 or couple of learning logs, I've been heavily focused on exploring cameras within phaser. Since camera defines how the user itself sees the overall screen of the stage and how they can interact with the objects involved in the stage. If I rememeber it correct last time in the blog 1, I only explored the basic's like why I choosed the tool phaser, what led me to it and etc. Basically the basics. Therefore we are moving pass that. So buckle up..I guess
# Content
Alright, so for the content, I just want to do an basic recap of the things I learned from the learning log from tinkering with phaser. We know that viewport, in this case is the camera's vision, basically the area and the visibility the "user" can actually see.
The main properties of the viewport includes an x and y and an width and height
For example: the X and the y properties represent the top left corner and the width and the height are the size of the viewport. There is also centerX or center Y. Think of them as the center midpoint of the viewport. To give an example:
```js
this.cameras.main.setViewport(0, 0, 400, 300);
```
The viewport x and y is 0, the width is 400 and the height is about 300
Alright for worldview, what exactly is an worldview? Worldview is the area of the world in which the camera sees. (NOT THE PLAYER)
The worldview depends on the camera's actual rotation, positioning and others. For example:
```js
var x = camera.midPoint.x;
var y = camera.midPoint.y;
```
We know for the camera is in midpoint/center of the current view within the game stage using the camera.midPoint. And the variable x and y, x is horizontal with camera.midPoint.x; and y is vertical for camera.midPoint.y;
As for visibility it basically determines and renders what, the camera can actually use. For example if you want to set it off and on use:
```js
camera.setVisible(true);  
camera.setVisible(false);
```
The true makes it so that the camera IS able to render the scene, whereas false IS NOT be able to render the scene. There's also other combination or usage. For example if you want to set the background color of the camera to be an certain color like:
```js
camera.setBackgroundColor('purple');
```
This sets the background color of the camera to purple
# Engineering Designing Process
Base off of everything's that's been going I would consider myself currently in the stage of 2 which is researching/gather information. The reason why I say that is becasue I do not think I'm at step 1 since I already have a problem to define which is learning my tool more. In which case my tool phaser. However currently I'm only on the camera part of the phaser too. In the documentation there is alot more to phaser tool than just camera. Therefore I believe step 2 defining and researching more about the tool is the best option and that if I were to move on past to step's like step 3 or 4 it would have an massive gap in-between. Since I would not have enough knowledge to help me build and test
# Skill
### Code skills: Ok ok I know for the last blog I also put something like "basic programming skills" but trust me its essential and needed for the tool of phaser. For example, last time I only included if statement therefore I want to refresh your memory again. Let's say if you were to code an game that makes has an an character, he has 5 lives, and if all his lives are gone he basically dieds, and games over. So by using the conditonals if statement you can easily simulate this by:
```js
if (npcHealth <= 0) {
console.log("You are dead! Game Over");
}else {
console.log("Keep on pushing!");
}
```
Using if and else conditionals like this help you to control the game's logic much better, and can also be used in when the NPC interacts with other objects
### Thinking and Tinkering
While I work with phaser in cameras, viewports and visibilities, I learned to break down each step down into smaller bite sizes so I know what's going on. Basically, I've come across alot of big chunk of code or some codes I don't understand. However I take those code piece by piece and tinker with them until I either understand what's going on, or what it is doing.
For example:
```js
this.cameras.main.setViewport(0, 0, 400, 300);
this.cameras.main.setBackgroundColor('blue');
this.cameras.main.ignore(enemy);
```
I know that 
```js
this.cameras.main.setBackgroundColor('blue');
```
Sets the background color of the camera to blue
```js
this.cameras.main.setViewport(0, 0, 400, 300);
```
This has 4 points, x and y and the width and the height
and so on, basically taking it into smaller chunks, so its better to digest



[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
