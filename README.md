# Retrieving_The_Bone
Code that connects to iPhone camera from python on Mac that image processes a operation game board and sends controls robotic arm using pico over mqtt

Files:

1) Pico_Main:
   resets pulley level and arm position, then listens over mqtt for commands from coputer code, ordering the three servos where to go in order to get to proper position over the operation game piece. Then triggers the pulley to lower and raise to grab the peice, then return to initial positon.
2) Mac_Main:
   searches for the green apple coordinates and blue base of the arm coordinates, then converts pixels into x and y distance, and uses inverse kinematics to convert this into agnles for the servos. Sends these angles over mqtt to the Pico.
3) Mac_Helper_Funcs:
   Functions that scan the board for the centroid of the largest green and blue object in the camera and returns the x and y pixel location.
