## Part 8 – Loading a background image and adding sound {#part-8-loading-a-background-image-and-adding-sound}

So you now have your space turtle running around the screen chasing and chomping moving space cabbages. Now you want to add a nice background and sounds to your game

1.  The first we want to do is download the background image and sound files into the folder where your kbgame files are stored. Yu can do this by selecting the image file here [kbgame-bg.gif](https://mysite.bhpbilliton.com/personal/kieran_mccluskey_bhpbilliton_com/Documents/01%20Dev%20Platform/14%20Culture/Perth%20web%20Girls/Python%20Game/kbgame/kbgame-bg.gif)
2.  For Windows users download the following .wav files [bounce.wav](https://mysite.bhpbilliton.com/personal/kieran_mccluskey_bhpbilliton_com/Documents/01%20Dev%20Platform/14%20Culture/Perth%20web%20Girls/Python%20Game/kbgame/bounce.wav)[chomp.wav](https://mysite.bhpbilliton.com/personal/kieran_mccluskey_bhpbilliton_com/Documents/01%20Dev%20Platform/14%20Culture/Perth%20web%20Girls/Python%20Game/kbgame/.chomp.wav)For Apple Mac users download the following .mp3 files[bounce.mp3](https://mysite.bhpbilliton.com/personal/kieran_mccluskey_bhpbilliton_com/Documents/01%20Dev%20Platform/14%20Culture/Perth%20web%20Girls/Python%20Game/kbgame/bounce.mp3)[chomp.mp3](https://mysite.bhpbilliton.com/personal/kieran_mccluskey_bhpbilliton_com/Documents/01%20Dev%20Platform/14%20Culture/Perth%20web%20Girls/Python%20Game/kbgame/chomp.mp3)
3.  Now you load the background image by adding the bgpic to the setup screen option

| 3 | #Set up screen |
| --- | --- |
| 4 | turtle.setup(650,650) |
| 5 | wn = turtle.Screen() |
| 6 | wn.bgcolor(&quot;navy&quot;) |
|  | wn.bgpic(“kbgame-bg.gif”) |
|  | wn.tracer(3) |

1.  The space cabbages currently are the same size as your turtle lets makes them smaller and add a few more. You can do this by typing the following within the #create objective space cabbage food section

|  | #create food |
| --- | --- |
|  | maxFood = 10 |
|  | Foods = [] |
|  |  |
| 38 | for count in range(maxFoods): |
| 39 | foods.append (turtle.Turtle()) |
| 40 | foods[count].color(&quot;lightgreen&quot;) |
| 41 | foods[count].shape(&quot;circle&quot;) |
|  | foods[count].shapesize(.5) |
| 42 | foods[count].penup() |
| 43 | foods[count].speed(0) |
| 44 | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |

1.  Save you game as kbgame8 and Run your module

If you want to use your own background image you simply need to create an image in your favourite image editor and save it as 600 by 600 and as a .gif file.

Now we need to add the sound this again is fairly simple but we use a different function depending on whether you are using a Windows or Apple Mac operating system

For Apple Mac

1.  You need to inform the Python program to use the audio features of your Apple Mac you do this by importing the OS (operating system) commands by typing the following at the top of your application

| 1 | #Turtle Graphics Game – Space Turtle Chomp |
| --- | --- |
| 2 | import turtle |
| 3 | Import math |
| 4 | Import random |
|  | Import os |

1.  Now in the #boundary checking section we type the following

| 80 | #Boundary Player Checking x coordinate |
| --- | --- |
| 81 | if player.xcor() &gt; 290 or player.xcor() &lt;-290: |
| 82 | player.right(180) |
| 83 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |
| 84 |  |
| 85 | #Boundary Player Checking y coordinate |
| 86 | if player.ycor() &gt; 290 or player.ycor() &lt;-290: |
| 87 | player.right(180) |
| 88 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |
| 89 |  |
| 90 | #Move Food around |
| 91 | for count in range(maxFoods): |
| 92 | foods[count].forward(3) |
| 93 |  |
| 94 | #Boundary Food Checking x coordinate |
| 95 | if foods[count].xcor() &gt; 290 or foods[count].xcor() &lt;-290: |
| 96 | foods[count].right(180) |
| 97 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |
| 98 |  |
| 99 | #Boundary Food Checking y coordinate |
| 100 | if foods[count].ycor() &gt; 290 or foods[count].ycor() &lt;-290: |
| 101 | foods[count].right(180) |
| 102 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |
| 103 |  |
| 104 | #Collision checking |
| 105 | if isCollision(player, foods[count]): |
| 106 | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| 107 | foods[count].right(random.randint(0,360)) |
| 108 | os.system(&quot;afplay chomp.mp3&amp;&quot;) |
|  |  |

_*note: we are playing the bounce sound when either your turtle or the cabbages bounce of the boundary and the chomp sound when you collide with a cabbage_.The little ‘&amp;’ after .mp3 tells the computer to play the sound in the background so the game doesn’t stop until the sound finishes, the technical term for this is Asynchrounous.

For Windows

1.  You need to inform the Python program to use the audio features of your Windows computer you do this by importing the winsound commands by typing the following at the top of your application

| 1 | #Turtle Graphics Game – Space Turtle Chomp |
| --- | --- |
| 2 | import turtle |
| 3 | import math |
| 4 | import random |
|  | import winsound |

1.  Now in the #boundary checking section we type the following

| 80 | #Boundary Player Checking x coordinate |
| --- | --- |
| 81 | if player.xcor() &gt; 290 or player.xcor() &lt;-290: |
| 82 | player.right(180) |
| 83 | winsound.PlaySound(&#039;bounce.wav&#039;, winsound.SND_ASYNC) |
| 84 |  |
| 85 | #Boundary Player Checking y coordinate |
| 86 | if player.ycor() &gt; 290 or player.ycor() &lt;-290: |
| 87 | player.right(180) |
| 88 | winsound.PlaySound(&#039;bounce.wav&#039;, winsound.SND_ASYNC) |
| 89 |  |
| 90 | #Move Food around |
| 91 | for count in range(maxFoods): |
| 92 | foods[count].forward(3) |
| 93 |  |
| 94 | #Boundary Food Checking x coordinate |
| 95 | if foods[count].xcor() &gt; 290 or foods[count].xcor() &lt;-290: |
| 96 | foods[count].right(180) |
| 97 | winsound.PlaySound(&#039;bounce.wav&#039;, winsound.SND_ASYNC) |
| 98 |  |
| 99 | #Boundary Food Checking y coordinate |
| 100 | if foods[count].ycor() &gt; 290 or foods[count].ycor() &lt;-290: |
| 101 | foods[count].right(180) |
| 102 | winsound.PlaySound(&#039;bounce.wav&#039;, winsound.SND_ASYNC) |
| 103 |  |
| 104 | #Collision checking |
| 105 | if isCollision(player, foods[count]): |
| 106 | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| 107 | foods[count].right(random.randint(0,360)) |
| 108 | winsound.PlaySound(&#039;chomp.wav&#039;, winsound.SND_ASYNC) |
|  |  |

_*note: we are playing the bounce sound when either your turtle or the cabbages bounce of the boundary and the chomp sound when you collide with a cabbage_.The SND_ASYNC tells the computer to play the sound in the background so the game doesn’t stop until the sound finishes, the technical term for this is Asynchrounous.

1.  Save and run your module
2.  Now you can change the background to black to make the game look better

| 3 | #Set up screen |
| --- | --- |
| 4 | turtle.setup(650,650) |
| 5 | wn = turtle.Screen() |
| 6 | wn.bgcolor(&quot;black&quot;) |
|  | wn.bgpic(“kbgame-bg.gif”) |
|  | wn.tracer(3) |

1.  Save and Run your model

Congratulations Module 8 Completed