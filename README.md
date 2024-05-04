# Portfolio Assignment 
My submission for my portfolio assignment

# What I Did
My role in this project was to make the camera system and create the sound effects/music. During this project, I had to rewrite the camera system to fit the game better. I felt the camera system was more important to the build than the sound effects so I spent more time tweaking and then rewriting the camera system before getting the necessary sound effects.

In the old camera system, a line trace was made between the camera and the player. If the line trace hits the camera is then put in an algorithm that chooses the closest camera to the player and with the highest priority. 

The final reworked camera system works as a volume system. When both characters enter a volume the camera switches. The camera position was saved as a camera node variable the active camera node decided where the camera was and what the *next* node was. If the next volume the players entered correlated with the *next* node variable and the node contained a spline traistion, the camera smoothly animated to the next position by following a spline. If the camera didn't contain a spline transition it just snapped to the next position.

The sounds used were a combination of found sounds online and ones I made myself. My method of making sounds was to use the object I could find around my dorm to simulate the sound I was looking for.

# Challenges
The first challenge I faced while making the camera system was raycasting/line tracing in Unreal. The first problem with the first camera system was that the player controllers were not part of the correct layer for the line trace this took awhile to figure out and change the line trace to be able to see the player controller.

The next challenge I faced was the realization that the camera system needed a whole overhaul and rework. This took up a lot of time that could have been used for sound effects so because of this the sound effects were lacking compared to the result I was looking for.

Another challenge was placing camera angles that fit. The camera angles needed to be in a place to fully show where the player needs to go and allow them to complete the task that is needed from them effectively. This involved a lot of playtesting and placing new cameras, and moving splines to match the animation I was looking for.

The first challenge I faced with the sound effects was creating sounds that correctly matched what the actions I created them for. It was very difficult to match the sounds as they ended up not sounding like what I intended.

Another challenge was time, I wanted to create sounds for everything but due to the fast nature of this course I couldn't do that so I had to find sounds of FreeSounds.org and edit them in Audacity to fully match what I was looking for.

# How I did it

How the camera system works:

At the start of the Camera Manager Actor it sets the Current Node variable to the Start Node variable that is set in the editor before play:
![image](https://github.com/AwokenOwen/PortfolioAssignment/assets/138807889/9a33ee09-f851-4458-a3e2-e57be428f4c1)

Then on every tick it checks if the current node has a look target. If it does it makes the camera look at the look target actor stored in the node. If it doesn't have a look target it looks at the midpoint between the two players:
![image](https://github.com/AwokenOwen/PortfolioAssignment/assets/138807889/8d1a6674-efd6-4cb1-9fcc-7abf76eac30b)

The way to switch cameras was a custom event. This event checked if there was spline transition to this node if so it followed the correct spline and then set the new node as the current node (if the camera is currently following a transition it stops the current transition if it's currently in the same transition it does nothing):
![image](https://github.com/AwokenOwen/PortfolioAssignment/assets/138807889/00a6fc4d-7fb9-480e-af6b-6efe054c134d)

Then to add functionallity for cutscene cameras I added two simple functions for setting custom cameras so you can switch freely between them (if the camera is transitioning skip the transition and set the custom camera):
![image](https://github.com/AwokenOwen/PortfolioAssignment/assets/138807889/79dd8d07-804c-400a-a21e-139fbee4ab3d)

How I played sounds:

For most of the sounds I added splay sound at location in the blueprints responsible for doing those actions.

For walking I added animation notifies in the animation themselves that play the sound at the right time.

Finally for the music I used a cross fade in a single sound cue to switch between the two music tracks when need be.

# Version Control
We chose GitHub becasue it seemed the easiest to use and people on the team had experience with it. I personally only had limited expierence 
