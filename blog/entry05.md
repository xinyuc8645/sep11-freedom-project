# Entry 5
##### 4/13/26
## Context
Usuals...Right? New blog means new information? Yep that's right, with new information comes new updates about the project. For this blog I'll be mainly covering what me and my partner did durinig the spring break for our project; how we communicate, problem solve and transform our plan --> functionable game. However I must say that, as for me I did NOT expect such an big progress towards our game. Like actually. So I guess, sit back, relax and read?..
## Content
Okay, so for the content, I'll be explaining stuff in this way: I'm going to first explain how the codes in the project correlates with the stuff, I've been learning accordingly to how the plan is going to be; then I'm going to explain how the project came in one piece from my perspective then provide an link to the project and the code to it. So without further, let's get started. I actually want to focus on this part of the code:
```js
 // brick wall
                    brick = this.physics.add.staticImage(87, 372, 'brickWall');
                    brick.setSize(30, 80);
                    brick.setScale(0.15);

                    this.physics.add.overlap(player1, brick, function() {
                        if (userAnswered === false) {
                            userAnswered = true;
                            var answer = prompt("Answer to pass! What is 2 + 2?");
                            if (answer === "4") {
                                brick.destroy();
                            } else {
                                alert("Wrong! Try again.");
                                userAnswered = false;
                            }
                        }
                    }, null, this);
```
Ok, I'm going to break this down a bit
So let's start with the brickwall. (Also keep the code was from an commit log meaning everything in this code could of been changed)
I first created an object that is NON moving called brick in which the position is located at the x value of 87 and y value of 372. And the 3rd parameter is used to show the image of the brickwall, as it was preloaded before in the preload function. I then set the size of collison hitbox in which the sprite would hit the/touch the brickwall to be at 3o pixels wide and 80 pixel high. And lastly I set the entirely of the picture of the brickwall object to 0.15; as setting it to 0.5-1 and over would be a little too big. Now how does tihs correlates with what I'm learning with my tool? Well...Earlier in my learning log, I actually focused on collision in which it uses this code:
```js
this.physics.add.collider(player1, testplatform)
```
You might be wondering..How would THIS code correlate of your brickwall? Well...Its not much far.Earlier we know, there is an brickwall that is an non-moving object that is why its called "static" however the thing is other object can still COLLIDE into that brickwall without the brickwall moving. And just to refresh memeories the collision code, it basically means that there is collision between the player1 sprite and the platform whether it could involve bounce, push and etc. Meaning you add both together an static object of an brickwall + enabling/adding collision between two object makes an object interactive. And the result is basically this:
```js
brick = this.physics.add.staticImage(48, 250, 'brickWall');
brick.setSize(30,80);    
brick.setScale(0.15);    
this.physics.add.collider(player1, brick);
```
Yea..Basically its just that simple. Now you have an static non moving object of an brick having collision enable between the player1 sprite and brickwall so when the player1 runs to the brickwall the sprite are basically stopped or others result depending on how you modify it.
Okay let's move on to the second half of that code:
```js
this.physics.add.overlap(player1, brick, function() {
                        if (userAnswered === false) {
                            userAnswered = true;
                            var answer = prompt("Answer to pass! What is 2 + 2?");
                            if (answer === "4") {
                                brick.destroy();
                            } else {
                                alert("Wrong! Try again.");
                                userAnswered = false;
                            }
                        }
                    }, null, this);
```
For the function we created something called:
```
this.physics.add.overlap(player1, brick, function() {
```
However there seems to be an overlap within the physics.add. So what is that? Overlap basically means that it checks if the player1 sprite is touching the brickwall, and if they are the following function will be triggered. Now I know its not mentioned here but at the top of the code from my cs50.dev there is a bunch of global variables we can use. And there is one called userAnswered and I'll pretty sure its trued off. 
```js
 if (userAnswered === false) {
  userAnswered = true;
```
However what this code does is basically that it makes it so when the sprite touches the brickwall it will only be asked twice until they can figure out meaning, if they get it wrong they will continue getting prompt. Lastly
```js
 var answer = prompt("Answer to pass! What is 2 + 2?");
                            if (answer === "4") {
                                brick.destroy();
                            } else {
                                alert("Wrong! Try again.");
                                userAnswered = false;
                            }
                        }
                    }, null, this);
```
By this we created an variable called answer, and the prompt message is self explantory. If they answer the correct answer, the brickwall will be destroyed/removed. However if they get it wrong, they will try again and be alerted in which the brickwall will stay and not be destroyed. 
I want to say that this section of the code kind of correlates with javascript a bit more; espeically on the side of if functions. Since as you can see in this function if their answer is 4, they basically get it right, else if their answer is not = to 4 then they have to try again. It's really similar to if function in javascript; actually pretty much basically the same since in java; you basically just do:
```js
if (score < 5) {
console.log("Winner!");
} else {
console.log("Try Again!");
}
```
Now now, this is only one section of the code. And I'm to be frank we have two levels for our games right now. The second level is basically the replicate of level 1, basically the code are re-used just that the whole layout and the placement of the doors, portals, brickwalls, are changed location. And I'm not going to lie we kind of did delayed our project towards the end of the break, but I think AI-assisting and helping us catch small error from large chunk of code and giving us small hint of how an code could possibly functiion actually speed the whole process by alot. For example: this whole function of code for lives:
```js
 if (dying === false) {
                            dying = true;
                            player1.disableBody(true, false);
                            lives--;
                            livesText.setText('Lives: ' + lives);
                            score = 0;
                            scoreText.setText('Score: 0');
                            if (lives <= 0) {
                                lives = 3;
                                dying = false;
                                userAnswered = false;
                                keyOn = false;
                                this.scene.start('Level1');
                            } else {
                                this.time.addEvent({
                                    delay: 500,
                                    callback: function() {
                                        dying = false;
                                        userAnswered = false;
                                        keyOn = false;
                                        this.scene.restart();
                                    },
                                    callbackScope: this
                                });
                            }
                        }
                    }, null, this);

                    // brick wall
                    brick = this.physics.add.staticImage(87, 372, 'brickWall');
                    brick.setSize(30, 80);
                    brick.setScale(0.15);

                    this.physics.add.overlap(player1, brick, function() {
                        if (userAnswered === false) {
                            userAnswered = true;
                            var answer = prompt("Answer to pass! What is 2 + 2?");
                            if (answer === "4") {
                                brick.destroy();
                            } else {
                                alert("Wrong! Try again.");
                                userAnswered = false;
                          }
                        }
                    }, null, this);
```
Right now it look like there is no issues, however believe it or not there was quite few of missing closing brackets
<p>Lastly here is the link directly for the code section and the playable game section:
  
```js
  if (dying === false) {
                            dying = true;
                            player1.disableBody(true, false);
                            lives--;
                            livesText.setText('Lives: ' + lives);
                            score = 0;
                            scoreText.setText('Score: 0');
                            if (lives <= 0) {
                                lives = 3;
                                dying = false;
                                userAnswered = false;
                                keyOn = false;
                                this.scene.start('Level1');
                             else {
                                this.time.addEvent({
                                    delay: 500,
                                    callback: function() {
                                        dying = false;
                                        userAnswered = false;
                                        keyOn = false;
                                        this.scene.restart();
                                    ,
                                    callbackScope: this
                                });
                            }
                        
                    }, null, this);

                    // brick wall
                    brick = this.physics.add.staticImage(87, 372, 'brickWall');
                    brick.setSize(30, 80);
                    brick.setScale(0.15);

                    this.physics.add.overlap(player1, brick, function() {
                        if (userAnswered === false) {
                            userAnswered = true;
                            var answer = prompt("Answer to pass! What is 2 + 2?");
                            if (answer === "4") {
                                brick.destroy();
                            } else {
                                alert("Wrong! Try again.");
                                userAnswered = false;
                          }
                        
                    }, null, this);
```
This was sort of what exactly looked like before ai-assisting as some of the brackets are quite easy to miss, since sometimes it gets overlapped with certain codes and doesn't know where it ends from
<a href = "our-first-game/index.html at main · rains1435/our-first-game · GitHub
https://github.com/rains1435/our-first-game/blob/main/index.html">Link for code</a> 
<a href="https://rains1435.github.io/our-first-game/">Link for playable game</a></p>
## Engineering Designing Process
Okay, so to be honest I'm suprised at how much progess me and my partner did towards the MVP. Considering that by the last blog, that by blog 5 we should be entirely on step 5 which is "creating an prototype". HOWEVER, we actually are past that. And we SHOULD be past that. Since now our MVP entirely are an functionable, working game with sprites moving, collecting coins, and teleporting to the next level. I want to say that I'm positive that we are on step 6 which is testing our prototype. And that's perfect actually, since on monday; the april 20th we are testing each other games and testing how they work. So I think during this time it's the perfect time for our classmates to break and test our game to find our what bug could occur. Yes me and my partner did bug proof before hand however I think with more peoples its more viable. And pretty much this is all I can say. Below I'll show you the plan and the link via it, and how we transform that plan into an viable and functionable game..
## Skills 
### AI-Assitance In Coding
Ok, so let me just explain this skill, AI-Assistance in coding is the practices in which you use the AI to help you debug codes, refine/simplify codes by providing hints and certain steps of how you can possibility move towards the end goal, INSTEAD of just straight up giving you the result and the outcome of it. And that's what me and my partner needed help on during the project. For example as the earlier code, you can see that there was huge chunk of code lay. However some brackets are missing. And I think going through each of one of them would be possibly. However I think having ai-assist and locatiing some of the location of missing brackets help reduce time and make our own time more productive
### Communcation Is Key
Yes, communcation being an key is an skill. Imagine this, if two people are working on the same project together with no communication what so ever. And they have no idea what each person is doing what and when they should pull...push and etc. Then their project will result in an incomplete and an mess. However if they communicate their project are more likely to be completed and will cause less confusion among each other as their own role in the project is defined. Additionally it also helps an cause and effect. Now when I mean this "cause and effect" I mean that whenever one person encounter an problem they have in their project, the other can communicate with person a to resolve it altogether. Whereas to put in perspective if they have no communication, then most likely that issue will not even get resolve as person b most likely won't even know if there is a issue in the first place as they are only focusing on their side. Therefore communication is the key to all things, this includes our human civilization and our history of progressing. Without communication I don't think we would of got this far
[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
