## Part 9 – Adding a score and displaying it on the screen {#part-9-adding-a-score-and-displaying-it-on-the-screen}

To make this more like a game you can add a score for each time your turtle chomps on a cabbage. To do this you create a new score variable by typing the following

1.  Move to the #Create turtle section of your code and type the following

| 29 | player.shape(&quot;turtle&quot;) |
| --- | --- |
| 30 | player.penup() |
| 31 | Player.speed(0) |
| 32 |  |
| 33 | #Create variable score |
| 34 | score = 0 |
| 35 |  |
| 36 |  |

1.  Move to the bottom of your While Loop at the end of your collision checking section and type

| 107 | #Collision checking |
| --- | --- |
| 108 | if isCollision(player, foods[count]): |
| 109 | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| 110 | foods[count].right(random.randint(0,360)) |
| 111 | winsound.PlaySound(&#039;chomp.wav&#039;, winsound.SND_ASYNC) |
| 112 | Score +=1 |
| 113 |  |

*note: this will calculate a score but you can’t see it on the screen

1.  Now we add the score to the screen by re-using the mypen turtle and using it to write the score, you can do this by typing

| 111 | winsound.PlaySound(&#039;chomp.wav&#039;, winsound.SND_ASYNC) |
| --- | --- |
| 112 | Score +=1 |
| 113 | mypen.penup() |
| 114 | mypen.hideturtle() |
| 115 | mypen.setposition(-290, 310) |
| 116 | scorestring =&quot;Score: %s&quot; %score |
| 117 | mypen.write(scorestring, False, align=&quot;left&quot;, font=(&quot;Arial&quot;, 14, &quot;normal&quot;)) |
| 118 |  |
| 119 |  |

So you have created a string that displays the score in the top left hand corner of your screen

1.  Save your game as kbgame9 and Run your module

What you should now see is that your score is in the top left hand corner of the screen but the number (1, 2, 3, 4 etc.) are writing on top of each other. You can fix this by delete the previous score before writing the new score.

1.  Add the undo option to the mypen section

| 113 | mypen.undo |
| --- | --- |
| 114 | mypen.penup() |
| 115 | mypen.hideturtle() |
| 116 | mypen.setposition(-290, 310) |
| 117 | scorestring =&quot;Score: %s&quot; %score |
| 118 | mypen.write(scorestring, False, align=&quot;left&quot;, font=(&quot;Arial&quot;, 14, &quot;normal&quot;)) |
| 119 |  |

1.  Save and Run your module

Congratulations Module 9 Completed