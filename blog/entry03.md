# Entry 3
##### 2/2/26

# Context
Soooo, we are back again for the 3rd time, for blog 3 I'll be mainly talking about others codes that I tinkered with my tool phaser. NOT including camera/visibility/viewports in the second blog. The main topics that I'll be covering for this blog is phaser actions,

# Content for Phaser Action
Of course, we are going to start off basic since I are still learning/tinkering with my tool. So then it brings us the question..What exactly is phaser action in phaser? Think of action in phaser as an way of applying an existing function towards more than 1+ objects all at once. More specifically:
<ul>
  <li>Helps apply those function to mulitple object at once</li>
  <li>Helps perform certain task and movement(rotating, moving and etc</li>
</ul>
Now I know this might be a little hard to digest with. But I'll show you can quick example:

```js
Phaser.Actions.SetAlpha(myGroup.getChildren(), 0.5);
```
This is an code provided by the phaser. I know, I know you might be thinking what is "myGroup" and what is "getChildren", 0.5 and etc.
Basically the idea is that the "myGroup" inside contains multiple objects more specifically contains more than 1 sprite. Now before getting into what is getChildren. I'll explain what the 0.5 is. In phaser sprite are controlled by alpha values. In other words, the alpha values that controls the sprite determines the sprite's transparent. In this case the sprite/object in this case of myGroup will be 0.5 meaning its 50% transparent whereas 1 is no transparent and 0 is fully transparent. And it's clear that in the code before the () there is an code called "setAlpha" which supports this idea. getChildren basically returns the number of arrays of sprite within the myGroup. Since inside that myGroup code there should be more than 1+ sprite inside. Now to put all those ideas together the code will first get all the sprite contained in then the myGroup then sets the alpha value of each sprite inside the myGroup to 0.5
Moving on, you know that from the earlier code that when doing an phaser action code, its usually passed in the value of an alpha, (also scale,and position) and also within an arrays of mulitple sprites. But there are also three extra parameters values that you can pass the phaser action witin. This includes:
<ul>
  <li>index</li>
  <li>Step</li>
  <li>Direction</li>
</ul>
Don't worry I'll explain each of them. Also before explaining them in-depth one thing to note is that when passing these parameters the phaser action that was passed originally will not change, however the arrays of sprite inside will.

### Step
So, when we are taking about step, step is an parameter value that when used it increments and applies to each sprite as it loops within the array. What this means is that when it loops the array that the sprite is inside of, each sprite will have different values inside of having the same. For example:

```js
Before(without using step)
Phaser.Actions.SetX(objects, 100);
```
What do you think will happen when the action is run and loops? Well, the x value is set horizontal at 100 meaning the sprite when runned by the phaser action will all have the same value of 100 for x
However what happens when is it runned with step?

```js
After(Using step)
Phaser.Actions.SetX(objects, 100, 50);
```
You might have notice that there is an extra set of values within the parameters (). So what does this mean exactly? This means that as the action is runned, the x value location of the sprite is different. For example the first x value starts at 100, then the second x is at 150, then at third x is 200 and so on fourth
Why is using step important? Well, it helps in creating diversity and patterns so that its not just boring and plain and each value having the same value
### Index
[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
