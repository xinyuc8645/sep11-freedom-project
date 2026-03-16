# Entry 4
##### 3/9/26
## Context
Okayyyyyyy, 3 times the charm? 4 times? Yes this time in the blog I'll be mostly introducing....PROGRESS! I can't say its fully done nor fully polish but SOME work is definintely done between blog 3 and this current blog. Thus I'll basically be just talking about the usuals + check in with what me and my partner are currently doing for our game for the freedom project. Feel free to refer back to the learning log, however some content/code listed in this blog won't be a direct 1:1 refer to the learning log so just keep that in mind but I'll explain the codes that are unknown.
# Content
### Setup
Ok, so this blog might be a bit shorter than the last blog since all I did for the last blog was explain phaser actions and all other stuffs. HOWEVER keep in mind that the codes I've tinker with, MAY not be used in the actual game YET. So the first step I wanted to do set up the basic game canva by using this code from the phaser website:
```js
var config = {
    type: Phaser.AUTO,
    width: 800,
    height: 600,
    scene: {
        preload: preload,
        create: create,
        update: update
    }
};

var game = new Phaser.Game(config);

function preload ()
{
}

function create ()
{
}

function update ()
{
}
```
The width of the whole canva of the current game is (800,600), with 800=x and 600=y length. However when I tested it on my http-server it seems that the x value did not fit the screen of my laptop. So i changed the x value of 800 --> 1200. Even though it still lack in some spaces, it still work. Could be refactored later. And the major scenes are the preload function which basically preloads any png/jpg/images/textures beforehand so when you create it in the create function it actually loads. The create function basically just creates the pre loaded image, and lastly the update function which makes certain sprite/objects move each time. However for this blog I will only be covering mostly the preload and the create function. 
### Background
So since the canva doesn't have an background image. I decided that I would give an placeholder image in the meantime. The code in which used is:
```js
this.load.image('bluesky', 'assets/bluesky.jpg');
```
This loads the bluesky.jpg that was saved. The jpg was located in the section not within the index.html. Meaning the main directory was called "our first game", and when I click that folder, it has the index.html and etc. However there is also a sub directory called "assets", which contains all the textures/sprites and others. Which is referred back here as 'assets/bluesky.jpg'. And the "this.load.image" just loads the image within. Now that the background image of the bluesky.jpg is pre loaded I wanted to put it actually on the canvas now. How?
```js
var skyBg = this.add.image(600, 375, 'bluesky')
    skyBg.setDisplaySize(1200, 750);
```
Basically I created the variable called "skyBg" and within that I added the image of the already pre-loaded image of the bluesky.jpg and locate it at the x value of 600, and y value of 375. Then i used the created variable skyBg to make it display size 1200,750. Why?
Because if I let's say comment that displaysize out, the image would only display the top half of the canva only showing BLUES..However since I made the width to be 1200, and height to be 750 now it will display almost entirely of the bluesky.jpg. Although it's not perfect to some extend. Now since the bluesky placeholder background is established let's move on to the platform section.
### Platforms
The platform preloaded image will be the same to the bluesky.jpg
```js
this.load.image('concrete1', 'assets/concrete1.png');
```
Likewise, preloads the image of the concrete which will be the main texture of the platform (still needs refactor to make it less sluggish) and also located within the sub-folders of the assets
Now, you might think "cool, you pre loaded an image of an texture and now create an platform with it, ok but how? and how will you make it so that the platform are not fall-through meaning if a sprite were to be standing on top of it they wouldn't be completely fall through the platform?" Well good question! That's what I'm going to answer!
Rememeber the original basic setup? Well upon further research, you need some tweaking for it. In order to make the platform have collide or not fall through you need to enable the game's physics first. Which is 
```js
physics: {
        default: 'arcade',
        arcade: {
            gravity: { y: 450 },
        }
    },
```
I added physics which makes it so we can control physics within our game now! Yay! And we set the default to arcade which when I research said that out of all the phaser physics setting this is the most simple and easiest one to work with and within the arcade {} there are specific setting that correlates to it. For exmaple: gravity..I set the y = 450 when the sprite/object is falling down it will be pulled down by about 450 units and if you put non at all, they just won't fall..
Now the code to create it was:
```js
var testplatform = this.physics.add.staticGroup()
    var platform = testplatform.create(300, 500, 'concrete1')
    platform.displayWidth = 250;
    platform.displayHeight = 30;
    platform.refreshBody()
```
I know, 4-5 lines of code insane right?!! Ok so I created an variable called testplatform, and inside that it makes it so it creates an group of static objects, meaning even if an sprite or another objects hits them, they won't move, they will just simply be stuck in place like a golem. Then i created another variable called "platform" which in this I made it equal to the testplatform variable which contain the static group to ensure the platform wouldn't move, and create it and set the location of x to 300 and y to 500. Now if i didn't include displayWidth and displayHeight, the platform will block like an square. Thus is why I made the width 250 and height 30. Lastly I included refreshBody(). What is that exactly? Basically refreshes the platform and updates the current physics hitboxes so the sprite wouldn't fall through. And for the rest of the platform its basically rinse and repeat:
```js
//create function
var platform2 = testplatform.create(500,300, 'concrete1')
    platform2.displayWidth = 250;
    platform2.displayHeight = 30;
    platform.refreshBody()
```
No need for pre load since we are using the same texture for the same platform(might vary/change though)
# Engineering Design Process
From the last blog, I claim that I was still somewhere around step 2 which is the research and gathering part. However, by this blog I can say that I am somewhere between steps 3-5. Why? Because as in the content section you can see I already start creating platforms, backgrounds, basic canvas and etc. However this isn't an finish product nor can i say it reaches the goal of an MVP yet. Since the mininmum MVP of our game should be included that when the user inputs the key of "wasd"  and up, down, right, left key the player 1 and player 2 sprite should both able to move. The sprite is able to be to jump/interact with items and etc. Basically viable but not perfect. Since step 5 is designing/plan for solving the problem, by using different materials and etc. Additonally to add on to this, in step 3 its brainstorming which currently me and my partner is still doing. We are still brainstorming in different ways, certain things can interact, move, collide and etc. And last but not least step 4 which chooses the best one to solve the problem which correlates to any problem that we could encounter like, movement issue, object not appearing issue and etc. Thus, this is why I say that we are in-between steps of 3-5. However by next blog, we should be entirely focus on step 5.
# Skills

Text

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
