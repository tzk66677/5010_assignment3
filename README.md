# 5010_assignment3

# Taiji Visual Music Animation
This project is a p5.js sketch that displays a rotating Taiji (Yin-Yang) symbol. The symbol’s rotation speed changes in several stages and then continuously accelerates after 30 seconds. The animation automatically resets after 4 minutes. Additionally, when you click the mouse, the black and white colors of the Taiji symbol swap.

# Features
Stage-Based Rotation:
The rotation speed is controlled by how many frames have passed:

0–5 seconds (0–300 frames): Slow rotation (0.01 increment per frame).
5–10 seconds (301–600 frames): A little faster (0.02 per frame).
10–15 seconds (601–900 frames): Faster rotation (0.03 per frame).
15–20 seconds (901–1200 frames): Even faster (0.05 per frame).
20–30 seconds (1201–1800 frames): Fast rotation (0.08 per frame).
Continuous Acceleration:
After 30 seconds (past 1800 frames), the rotation speed increases continuously by adding a small acceleration (0.0005 per frame) to the current speed.

# Automatic Reset:
The animation runs for 4 minutes (approximately 14400 frames) before resetting all values (rotation angle and acceleration) so that the loop starts over smoothly.

# Interactive Color Swap:
When you click the mouse, the colors of the Taiji symbol swap (black becomes white and white becomes black), adding a simple interactive element.

# How It Works
Frame Count as a Timer:
The sketch uses the built-in frameCount variable to determine which stage of rotation to apply. This avoids delays or stuttering because the stage is continuously updated based on the frame number.

# Rotation Logic:

For the first 30 seconds, the rotation speed is set by fixed values corresponding to different time intervals.
After 30 seconds, the sketch begins to continuously accelerate the rotation speed by incrementing a variable (rotSpeed) each frame, which is then added to the rotation angle.
Reset Mechanism:
When frameCount exceeds 14400, the animation resets by setting the rotation angle and acceleration back to zero. Since frameCount itself cannot be reset, the sketch simulates a reset by pausing and restarting the drawing loop.

# Drawing the Taiji Symbol:
The Taiji symbol is drawn using a dedicated function. It consists of:

An outer circle.
A white semicircle created with the arc function.
Two large inner circles.
Two smaller inner circles (with a size proportional to the outer circle). The color swap on mouse press is handled within this drawing function.
