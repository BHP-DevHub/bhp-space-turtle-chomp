## Part 11 – Setting a time limit {#part-11-setting-a-time-limit}

You have most of your Space Turtle Chomp game developed now, however at the moment it can go on forever, like most games what you can do is set a time limit for the game duration, again this is simple to do

1.  Move to the top of your code and import the time function

| 1 | #Turtle Graphics Game – Space Turtle Chomp |
| --- | --- |
| 2 | import turtle |
| 3 | Import math |
| 4 | Import random |
|  | import os |
|  | import time |

1.  Move down to the just below the #Set speed variable section and add

| 65 | #Set Speed variable |
| --- | --- |
| 66 | speed = 1 |
| 67 |  |
| 68 | #Set game time limit for 1 minute (60 seconds) |
| 69 | timeout = time.time() + 10*6 |
| 70 |  |
| 71 |  |

_*note we set our game timeout to 6 lots of 10 second for a 1 minute game we could set it to 10*3 for 30 seconds or 5*5 for 25 seconds_

1.  Move to the While Loop section and add the following

| 100 | while True: |
| --- | --- |
| 101 | gametime = 0 |
| 102 | if gametime == 6 or time.time() &gt; timeout: |
| 103 | break |
| 104 | gametime = gametime - 1 |
| 105 |  |

*note: you set a variable could gametime and set it to 0, the if statement then runs the loop until gametime = 6

1.  Save your game as kbgame11 and run your Module

You should now have 60 seconds to chomp more space cabbages than your computer opponent before the game ends, fantastic well done. The last thing you can do for your game as part of this tutorial is have the game display who wins at the end of 60 seconds.

1.  Move to the very end of your code and add the following simple if statement and argument

| 173 | if (int(score) &gt; int(compscore)): |
| --- | --- |
| 174 | mypen.setposition(0, 0) |
| 175 | mypen.color(&quot;yellow&quot;) |
| 176 | mypen.write(&quot;Game Over: You WIN&quot;, False, align=&quot;center&quot;, font=(&quot;Arial&quot;, 28, &quot;normal&quot;)) |
| 177 | else: |
| 178 | mypen.setposition(0, 0) |
| 179 | mypen.color(&quot;yellow&quot;) |
| 180 | mypen.write(&quot;Game Over: You LOOSE&quot;, False, align=&quot;center&quot;, font=(&quot;Arial&quot;, 28, &quot;normal&quot;)) |
| 181 |  |

The If statement compares your score (player) against the opponent score (comp) and if your score is higher it prints the You Win message and if it is lower it prints the You Loose message.

That is the end of today’s tutorial, if you got through all of it in 1 day well down that it an awesome effort but it doesn’t matter if you didn’t as the tutorial is online and you can still access it from home with your parents help.

If you enjoyed this and wanted to continue practising, other things you might want to try is

*   Making multiple opponents using the List [] function like you did for food
*   Setting a start option at the beginning of the game
*   Setting a play again option at the end
*   Setting up a easy, medium and hard option for the game

There are lots of tutorials and help out on the internet if you look. It is also a great idea to try the other game options from Christian Thompson at his site [http://christianthompson.com](http://christianthompson.com)

Congratulations Module 11 Completed