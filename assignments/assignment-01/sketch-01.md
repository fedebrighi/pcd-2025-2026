PCD a.y. 2024-2025 - ISI LM UNIBO - Cesena Campus

# Sketch 01 - Notes

v1.0.0-20260316

This sketch shows an example of a board, with a number of small balls and one player ball moving and bouncing. Three different board configuration can be tried: 
- minimal, with only 2 small balls 
- large, with 400 small balls
- massive, with 4000 small balls

### About the simulation loop

The core simulation loop repeatedly:
- check if it is time to kick the player ball
- computes the next board state, depending on how much time is elapsed
- renders a new frame, updating synchronously the view with the updated board state

Sequential steps to update the board state:
- the state of the player ball is updated. That is:
  - the velocity is updated by applying the friction factor
  - the position is updated given the velocity and the elapsed time
  - collision with boundaries is checked
- the state of each small balls is updated
- collisions among small balls are checked
- collisions between the player ball and small balls are checked

### About Rendering

Rendering is requested by the main thread when calling `view.render` in the loop. The method is synchronous, that is: it returns when the rendering has been completed. How it works:
- in Swing, rendering is done by the EDT, so asynchronously with respect to other threads, such as the main thread. The method `repaint` provided by Swing components (such as frames, panels, etc) trigger rendering by producing a new task to do for the EDT.
- in the code, a monitor (`RenderSynch`) is used to synchronize the EDT rendering with the thread requesting repainting
