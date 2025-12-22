# Entry 2
##### 12/21/25

# Context
Alright, for this blog, we'll be mainly exploring cameras, viewport and visibility within phaser. I think for the past 3 or couple of learning logs, I've been heavily focused on exploring cameras within phaser. Since camera defines how the user itself sees the overall screen of the stage and how they can interact with the objects involved in the stage. If I rememeber it correct last time in the blog 1, I only explored the basic's like why I choosed the tool phaser, what led me to it and etc. Basically the basics. Therefore we are moving pass that. So buckle up..I guess
# Engineering Designing Process
Base off of everything's that's been going
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
