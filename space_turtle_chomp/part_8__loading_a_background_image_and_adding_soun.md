## Part 8 – Loading a background image and adding sound {#part-8-loading-a-background-image-and-adding-sound}

So you now have your space turtle running around the screen chasing and chomping moving space cabbages. Now you want to add a nice background and sounds to your game

Step 1.  The first we want to do is download the background image and sound files into the folder where your kbgame files are stored. You can do this by selecting the image file here [kbgame-bg.gif](/src/kbgame-bg.gif).

Step 2.  
For Windows users download the following .wav files:

* [bounce.wav](/src/bounce.wav)
* [chomp.wav](/src/chomp.wav)

For Apple Mac users download the following .mp3 files:

* [bounce.mp3](/src/bounce.mp3)
* [chomp.mp3](/src/chomp.mp3)

Step 3.  You load the background image by adding the wn.bgpic to the \#Set up screen section after wnbgcolor\('navy'\) :

```python
wn.bgpic('kbgame-bg.gif')
```

Step 4.  The space cabbages currently are the same size as your turtle lets makes them smaller and add a few more. You can do this by changing the max\_foods number and adding a the following to the for count in range section:

```python
# create food
max_foods = 10


for count in range(max_foods):
    foods[count].shapesize(.5)

```

Step 5.  Save your game as kbgame8 and run your module

\*note: if you want to use your own background image you simply need to create an image in your favourite image editor and save it as a 600 by 600 .gif file.

Now we need to add the sound this again is fairly simple but we use a different function depending on whether you are using a Windows or Apple Mac operating system

### For Apple Mac or Linux

Step 6.  You need to inform the Python program to use the audio features of your Apple Mac you do this by importing the OS \(operating system\) commands by typing the following at the top of your application with the other import's:

```python
import os
```

Step 7.  Now in the \#boundary checking section we type the following os.system... code at the end of each boundary and collision checking section:

```python
    # Boundary Player Checking x coordinate
    if player.xcor() > 290 or player.xcor() < -290:
        player.right(180)
        os.system('afplay bounce.mp3&')

    # Boundary Player Checking y coordinate
    if player.ycor() > 290 or player.ycor()  <-290:
        player.right(180)
        os.system('afplay bounce.mp3&')

    # Move Food around
    for food in foods:
        foods[count].forward(3)

        # Boundary Food Checking x coordinate
        if foods[count].xcor() > 290 or foods[count].xcor() < -290:
           foods[count].right(180)
           os.system('afplay bounce.mp3&')

        # Boundary Food Checking y coordinate
        if foods[count].ycor() > 290 or foods[count].ycor() < -290:
           foods[count].right(180)
           os.system('afplay bounce.mp3&')

        # Collision checking
        if isCollision(player, foods[count]):
           foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290))
           foods[count].right(random.randint(0,360))
           os.system('afplay chomp.mp3&')
```

_\*note: we are playing the bounce sound when either your turtle or the cabbages bounce of the boundary and the chomp sound when you collide with a cabbage_.

The little ‘&’ after .mp3 tells the computer to play the sound in the background so the game doesn’t stop until the sound finishes, the technical term for this is Asynchronous.

### For Windows

Step 6.  You need to inform the Python program to use the audio features of your Windows computer you do this by importing the winsound commands by typing the following at the top of your application with the other import's::

```python
import winsound
```

Step 7.  Now in the \#boundary checking section we type the following winsound.PlaySound... code at the end of each boundary and collision checking section

```python
    # Boundary Player Checking x coordinate
    if player.xcor() > 290 or player.xcor() < -290:
        player.right(180)
         winsound.PlaySound('bounce.wav', winsound.SND_ASYNC)

    # Boundary Player Checking y coordinate
    if player.ycor() > 290 or player.ycor() < -290:
        player.right(180)
         winsound.PlaySound('bounce.wav', winsound.SND_ASYNC)

    # Move Food around
    for count in range(maxFoods):
        food.forward(3)

        #  Boundary Food Checking x coordinate
        if food.xcor() > 290 or food.xcor() < -290:
           food.right(180)
            winsound.PlaySound('bounce.wav', winsound.SND_ASYNC)

        # Boundary Food Checking y coordinate
        if food.ycor() > 290 or food.ycor() < -290:
           food.right(180)
            winsound.PlaySound('bounce.wav', winsound.SND_ASYNC)

        # Collision checking
        if isCollision(player, food):
           food.setposition(random.randint(-290, 290), random.randint(-290, 290))
           food.right(random.randint(0,360))
            winsound.PlaySound('chomp.wav', winsound.SND_ASYNC)
```

_\*note: we are playing the bounce sound when either your turtle or the cabbages bounce of the boundary and the chomp sound when you collide with a cabbage_.The SND\_ASYNC tells the computer to play the sound in the background so the game doesn’t stop until the sound finishes, the technical term for this is Asynchronous.

Step 8.  Save and run your module

Step 9.  Now you can change the background to black to make the game look better by editing the wn.bgcolor.. to:

```python
wn.bgcolor('black')
```

Step 9.  Save and Run your model

Your code should look like this: Mac/Linux [kbgame8.py](/src/kbgame8.py), Windows [kbgame8.py](/src/kbgame8_win.py)

**Congratulations Module 8 Completed**

