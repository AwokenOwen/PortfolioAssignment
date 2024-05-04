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

The first challenge I faced with the sound effects was creating sounds that correctly matched what the actions I created them for. It was very difficult 
