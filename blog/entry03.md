# Entry 3
##### 2/2/26

# Context
Soooo, we are back again for the 3rd time, for blog 3 I'll be mainly talking about others codes that I tinkered with my tool phaser. NOT including camera/visibility/viewports in the second blog. The main topics that I'll be covering for this blog is phaser actions, sub-categories parameters(steps index and directions) alignto. And also please do refer back to the learning log and some content that is here will be pullled from the [learning log](

# Content for Phaser Action
Of course, we are going to start off basic since I are still learning/tinkering with my tool. So then it brings us the question..What exactly is phaser action in phaser? Think of action in phaser as an way of applying an existing function towards more than 1+ objects all at once. More specifically:
<ul>
  <li>Helps apply those function to multiple object at once</li>
  <li>Helps perform certain task and movement(rotating, moving and etc</li>
</ul>
Now I know this might be a little hard to digest with. But I'll show you can quick example:

```js
Phaser.Actions.SetAlpha(myGroup.getChildren(), 0.5);
```
<p>This is an code provided by the phaser. I know, I know you might be thinking what is "myGroup" and what is "getChildren", 0.5 and etc.
Basically the idea is that the "myGroup" inside contains multiple objects more specifically contains more than 1 sprite. Now before getting into what is getChildren. I'll explain what the 0.5 is. In phaser sprite are controlled by alpha values. In other words, the alpha values that controls the sprite determines the sprite's transparent. In this case the sprite/object in this case of myGroup will be 0.5 meaning its 50% transparent whereas 1 is no transparent and 0 is fully transparent.</p>
<p>And it's clear that in the code before the () there is an code called "setAlpha" which supports this idea. getChildren basically returns the number of arrays of sprite within the myGroup. Since inside that myGroup code there should be more than 1+ sprite inside. Now to put all those ideas together the code will first get all the sprite contained in then the myGroup then sets the alpha value of each sprite inside the myGroup to 0.5</p>
Moving on, you know that from the earlier code that when doing an phaser action code, its usually passed in the value of an alpha, (also scale,and position) and also within an arrays of multiple sprites. But there are also three extra parameters values that you can pass the phaser action within. This includes:
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
If you already did basic javascript/have some kind of experiences of coding. You know that index is the location of which an element in an certain place is. For example, let's say we have an array call 
```js
 var fruits = ["apple, pineapple, coconut"]
```
Now if we want the index let's say 0, that would give us the value of apple, and so on. By this logic it's also somewhat the same for phaser usage
What index is in phaser is where the sprite within an array of an action value starts from, basically their starting point
```js
Phaser.Actions.SetAlpha(objects, 0.5, 0, 5);
```
You can see that this code, nowhere does it directly say index. However there is something that needs clarifying. That is: inside the parameter when passing action of an phaser. There are key components: array name, value, step, index, and direction. In the example above array name = objects, value = 0.5 (for transparent), 0 = step, and 2 is the index. What this this means?
It means that the transparent change will only apply to the objects within the array starting from 6 not include 0, 1, 2, 3, 4, and 5
And also small detail, technically this code does work, it's just that in this case there is only 5 sprites, meaning if it were to run the code, nothing would be affected since there isn't an sprite after 5
### Direction
Direction is basically pretty self-explantory. Basically it controls in which the direction when runned the phaser action the array will be looped through. Like which ways (not trying to confuse you) For example: let's say you are starting at 1 that just means from regular start to end, left --> right, and if its -1 then its from end to start, right --> left. One thing to note is that is does not change the array and what it does. It only changes how the order/when it will be applied to that sprite
```js
Phaser.Actions.SetAlpha(objects, 1, -0.1, 0, -1);
```
From the previous code in index, we know what each number in the parameters represent. So in this case it would be that, the phaser action will start from the last sprite since the direction is -1 and the 1 in the beginning means the transparent alpha value which is 1 meaning it will be fully visible after looping from end object to start. And lastly the step is -0.1 meaning everytime it loops the each sprite the alpha value of each will be decreased by -0.1. Meaning let's say if there is 3 sprites. It starts at the 3rd sprite which is the end, by which the alpha value is 1, then the 2nd sprite alpha value will be 0.9 and so on
### Align To value
Alignto, action code is basically helping you to line up more than 1+ sprite towards an specific position in an scene. Or as phaser documentation describe it "as taking an array of sprites and lining up against each other"
Let's take an closer look at an code example provided by phaser:
```js
Phaser.Actions.AlignTo(items, position, [offsetX], [offsetY]);
```
<ul>
<li>>The items in this action code refers to the items you want it aligning to/updated towards to</li>
<li>Position refers to the position in which the item is to be aligned with</li>
<li>offsetX is the horizontal offset from the position</li>
<li>offsetY is the vertical offset from the position</li>
</ul>
How can this be used?

```js
var objectsNames = [Object1, Object2, Object3];
Phaser.Actions.AlignTo(objectsNames, Phaser.Display.Align.LEFT_CENTER);
```
In the variable objectsNames we have created an array, and inside those array there is 3 sprite/objects. By taking a look at the code below: the three sprite/object will be lined up vertically centered towards. (And also before you start saying that this code won't work, think of before the code there is already three objects/sprites called object1, object2, and object3
### Goals regarding the next blog 4
Ok, ok to be honest personally I feel like in this blog I have not yet cover a lot of stuff from the action section for phaser. And to be frank there IS a lot of stuff in each section for the phaser api documentations. However, I do really want to learn more about phaser. Therefore by the next blog I hope to cover the entirely(not entirely it's alot, but mostly) of the Actionlist;angle, call, Get first and get Last, Grid align, and Inc alpha. That is basically the goal I want to set for my goal for blog 4. And if by blog 4, I somehow do not get to those points, then it looks like I'll have to work even harder than before and tinker with my tool. But mostly likely I will
# Engineering Designing Process
From blog 2, I believe I mention that I am still on step 2. I know I know from the blog 2 there was an whole 2-3 months gaps in-between. However something that is important to understand is that even though during that 2-3 month time period was a lot of time to tinker and mess with the tool, personally I still do not yet believe that it is enough for steps 3 and 4. The reason is because there isn't yet an solution and a problem for me to solve. But if you think it like this way: "while tinkering I came across problems and I can solve this code by doing X solution" then yes somewhat in that case you can say that I'm in steps 3-4 since I'm diving deeper and deeper into the core of the phaser tool as an whole. So from my perspective I think I'm still on step 2, however if you think about the way I said, then you can think of it as steps 3-4
# Skills
### Manipulating/Controlling things within an array
<ul>
<li>What do I mean by this? Well it means quite liter what I said
In the content, I explained main three sub extra parameters: Step, Index and Direction</li>

```js
Phaser.Actions.SetAlpha(objects, 1, -0.1, 0, -1);
```
<li>Step is included: -0.1</li>
<li>Direction also included: -1</li>
<li>Index included: 0</li>
<li>Why does this show manipulating arrays with step, index and direction? Because without the values of step, index and direction the array when loop will be boring and not dynamic.</li>

```js
Phaser.Actions.SetAlpha(objects, 1,);
```
<li>This is without step, index and direction meaning it just makes the objects/sprite within that array to be fully visible, nothing else happens.</li>
<li>Whereas before it starts all the way from the last object/sprite, then each time the array is loop through the sprite alpha value is decreased by 0.1 which makes it so much dynamic and interesting</li>
</ul>

### Critical Thinking
You might be wondering, what exactly do you mean by "critical thinking"??? Well, for me its when you understand and is able to question your own code and by doing that you slow digest that code slowly into bit pieces so its more easier to look at. For example in the near beginning. I had an code called:

```js
Phaser.Actions.SetAlpha(myGroup.getChildren(), 0.5);
```
To be honest, at first I was also a bit confused of this code. I didn't know what the .setAlpha meant. I didn't know what the value 0.5 meant inside the parameters. And the myGroup andn getChildren. But as I explain and more able to digest the code by figuring out what each part does I slowly digest it into bite sizes. For example I know that setAlpha makes an sprite/objects transparent or not. And the 0.5 value inside the parameter means how much the transparent will be included, and so on. Therefore by adding those all together I now know what the code actually does and means
[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
