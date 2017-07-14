## Part 7 – Making multiple food items \(Space Cabbages\) to chase {#part-7-making-multiple-food-items-space-cabbages-to-chase}

In this section you are going to develop a way of having multiple space cabbages \(food\) moving around the screen for your turtle to chomp. You are going to do this using the python functions of Lists and Loops

Step 1.  First we create the maximum number of cabbages and an empty list by editing the \#Create food section with the following code at the top:

```python
#Create food
maxFoods = 6
foods = []
```

Step 2.  Next you create a for loop using maxFoods as the range updating the code

From this:

```python
food = turtle.Turtle()
food.color("lightgreen")
food.shape("circle")
food.penup()
food.speed(0)
```

To this:

```python
for count in range(maxFoods):
    foods.append (turtle.Turtle())
    foods[count].color("lightgreen")
    foods[count].shape("circle")
    foods[count].penup()
    foods[count].speed(0)
    foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290))
```

So we use the append function to add our maximum number of cabbages held in the list, so foods.\[1\] is a turtle object, foods.\[2\] is a turtle object etc. etc.

Step 3.  Now you need to do the same thing for moving the turtle within the \# Move Food around section by changing

this:

```python
# Move food around
    food.forward(3)
```

to:

```python
# Move food around
    for count in range(maxFoods):
        foods[count].forward(3)
```

And then indent and change

this:

```python
    # Boundary Food Checking x coordinate
    if food.xcor() > 290 or food.xcor() <- 290:
        food.right(180)

    # Boundary Food Checking y coordinate
    if food.ycor() > 290 or food.ycor() <- 290:
        food.right(180)
```

to:

```python
    # Boundary Food Checking x coordinate
    if foods[count].xcor() > 290 or foods[count].xcor() <- 290:
        foods[count].right(180)

    # Boundary Food Checking y coordinate
    if foods[count].ycor() > 290 or foods[count].ycor() <- 290:
        foods[count].right(180)
```

Step 4.  Now let’s move \(cut and paste\) your food collision checking code within move goal loop. Make sure you indent and then change food to foods\[count\] so your code now looks like:

```python
    #Move food around
    for count in range(maxFoods):
        food[count].forward(3)

    # Collision checking
    if isCollision(player, food):
        food.setposition(random.randint(-290, 290), random.randint(-290, 290))
        food.right(random.randint(0, 360))

    # Collision checking
    if isCollision(player, foods[count]):
        foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290))
        foods[count].right(random.randint(0,360))
```

Step 5.  Save the game as kbgame7 and run your module

You now have multiple cabbages moving around your screen however the screen can start to look a bit jumpy, to fix this we can add the tracer function to the program. This tells the computer not to refresh the screen each time and speeds up the animation.

Step 6.  Add the tracer function by typing the following at the end of the \#Set up screen area:

```python
wn.tracer(3)
```

Step 7.  Save and run your module

Your code should now look like this: [kbgame7.py](/src/kbgame7.py)

**Congratulations Module 7 Completed**

