## Part 10 – Adding a computer generated opponent {#part-10-adding-a-computer-generated-opponent}

In general games are more fun if you get to compete against an opponent, for Space Turtle Chomp this is very easy to do as we have already written all the code we just need to create an opponent section and cut and paste then modify our existing code.

1.  First we need to create a new turtle object as the opponent, move just under #Create player turtle and add

| 6 | #Create player turtle |
| --- | --- |
| 7 | player = turtle.Turtle() |
| 8 | player.color(&quot;darkorange&quot;) |
| 9 | player.shape(&quot;turtle&quot;) |
| 10 | player.penup() |
| 11 | Player.speed(0) |
|  |  |
|  | #Create compition turtle |
|  | comp = turtle.Turtle() |
|  | comp.color(&quot;red&quot;) |
|  | comp.shape(&quot;turtle&quot;) |
|  | comp.penup() |
|  | comp.setposition(random.randint(-290, 290), random.randint(-290, 290)) |

1.  Save your game as kbgame10 and Run your module

You now have a Red opponent space Turtle now you can make it move around the screen and add the boundary checking so it doesn’t run away. Move to your While Loop section and add the following

| 98 | While True: |
| --- | --- |
| 99 | Player.forward(speed) |
| 100 | Comp.forward(12) |
| 101 |  |
| 102 | #Boundary Player Checking x coordinate |
| 103 | if player.xcor() &gt; 290 or player.xcor() &lt;-290: |
| 104 | player.right(180) |
| 105 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |
| 106 |  |
| 107 | #Boundary Player Checking y coordinate |
| 108 | if player.ycor() &gt; 290 or player.ycor() &lt;-290: |
| 109 | player.right(180) |
| 110 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |
| 111 |  |
| 112 | #Boundary Comp Checking x coordinate |
| 113 | if comp.xcor() &gt; 290 or comp.xcor() &lt;-290: |
| 114 | comp.right(180) |
| 115 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |
| 116 |  |
| 117 | #Boundary Comp Checking y coordinate |
| 118 | if comp.ycor() &gt; 290 or comp.ycor() &lt;-290: |
| 119 | comp.right(180) |
| 120 | os.system(&quot;afplay bounce.mp3&amp;&quot;) |

*note: you can make the comp.forward speed faster or slower by changing the number within the brackets

1.  Save and run your module

Now your opponent turtle is moving around the screen and bouncing of the walls, next we want to give them a score

1.  Within the variable score section add

| 47 | #Create variable score |
| --- | --- |
| 48 | score = 0 |
| 49 | Compscore = 0 |

1.  Now copy the #player Collision checking paste below and update as below

| 107 | #Collision checking |
| --- | --- |
| 108 | if isCollision(player, foods[count]): |
| 109 | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| 110 | foods[count].right(random.randint(0,360)) |
| 111 | winsound.PlaySound(&#039;chomp.wav&#039;, winsound.SND_ASYNC) |
| 112 | Score +=1 |
| 113 |  |

| 111 | winsound.PlaySound(&#039;chomp.wav&#039;, winsound.SND_ASYNC) |
| --- | --- |
| 112 | Score +=1 |
| 113 | mypen.penup() |
| 114 | mypen.hideturtle() |
| 115 | mypen.setposition(-290, 305) |
| 116 | scorestring =&quot;Score: %s&quot; %score |
| 117 | mypen.write(scorestring, False, align=&quot;left&quot;, font=(&quot;Arial&quot;, 14, &quot;normal&quot;)) |
| 118 |  |
| 119 | # Comp Collision checking |
|  | if isCollision(comp, foods[count]): |
|  | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |
|  | foods[count].right(random.randint(0,360)) |
|  | winsound.PlaySound(&#039;chomp.wav&#039;, winsound.SND_ASYNC) |
|  | compscore+=1 |
|  | #Draw the Comp score on the screen |
|  | mypen2.undo() |
|  | mypen2.penup() |
|  | mypen2.hideturtle() |
|  | mypen2.setposition(200, 305) |
|  | scorestring =&quot;Score: %s&quot; %compscore |
|  | mypen2.write(scorestring, False, align=&quot;left&quot;, font=(&quot;Arial&quot;, 14, &quot;normal&quot;)) |
|  |  |

1.  Save and Run your module

Congratulations Module 10 Completed