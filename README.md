# 5010_assignment3

Taiji Visual Music Animation
This project is a p5.js-based interactive visual music animation featuring a Taiji (Yin-Yang) symbol. The symbol rotates at varying speeds based on different stages and continuously accelerates after 30 seconds. The entire animation resets after 4 minutes. This README explains the code, its features, and how to run or customize the project.

Features
Taiji Symbol:
The animation displays a Taiji symbol, drawn using p5.js. The symbol comprises an outer circle, a white semicircle, two inner large circles, and two smaller inner circles. When the mouse is pressed, the colors (black and white) swap, adding an interactive element.

Stage-Based Rotation:
The animation is divided into several stages determined by the frameCount:

Stage 0 (0–5 seconds, 0–300 frames): Rotation speed increases by 0.01 per frame.
Stage 1 (5–10 seconds, 301–600 frames): Rotation speed increases by 0.02 per frame.
Stage 2 (10–15 seconds, 601–900 frames): Rotation speed increases by 0.03 per frame.
Stage 3 (15–20 seconds, 901–1200 frames): Rotation speed increases by 0.05 per frame.
Stage 4 (20–30 seconds, 1201–1800 frames): Rotation speed increases by 0.08 per frame.
Continuous Acceleration:
After 30 seconds (frameCount > 1800), the animation enters a continuous acceleration phase. In this phase, a variable rotSpeed is incremented by 0.0005 per frame, causing the rotation speed to continuously increase.

Automatic Reset:
The entire animation resets after 4 minutes (approximately 14400 frames at 60fps). When this occurs, the animation resets the rotation angle and acceleration values. Since frameCount is a built-in variable and cannot be reset directly, the code simulates a reset by pausing (noLoop()) and then restarting the drawing loop (loop()).

Code Overview
Global Variables
angle:
Holds the current rotation angle of the Taiji symbol.
rotSpeed:
Stores the current rotation speed used in the continuous acceleration phase after 30 seconds.
frameCount:
A built-in p5.js variable that counts the number of frames rendered, used to determine the current stage.
Stage Control
The code uses conditional statements based on frameCount to determine the current stage:

0–300 frames:
The symbol rotates slowly (0.01 per frame).
301–600 frames:
The symbol rotates slightly faster (0.02 per frame).
601–900 frames:
The rotation speed increases further (0.03 per frame).
901–1200 frames:
A more significant increase in rotation speed (0.05 per frame).
1201–1800 frames:
The symbol rotates at a high constant speed (0.08 per frame).
After 1800 frames (30 seconds):
The rotation speed begins to continuously accelerate by increasing rotSpeed by 0.0005 each frame.
Automatic Reset
After 14400 frames (about 4 minutes), the animation resets:

The rotation angle (angle) and the continuous acceleration speed (rotSpeed) are set to 0.
The animation loop is paused and then restarted to simulate a reset.
Drawing the Taiji Symbol
The function drawTaiji(r) handles the drawing of the Taiji symbol:

An outer circle is drawn and filled with a primary black color.
A white semicircle is drawn using the arc function.
Two large inner circles (one for each half) are drawn.
Two smaller circles inside the large circles are drawn with sizes proportional to the outer circle (r/3).
When the mouse is pressed, the primary colors swap (black becomes white and vice versa).
