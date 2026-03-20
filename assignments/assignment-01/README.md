PCD a.y. 2024-2025 - ISI LM UNIBO - Cesena Campus

# Assignment #01 -  Poool Game

v1.0.0-20260319

The assignment is about designing and developing a game called `Poool`. 

### Game Description 

The game consists in a bidimensional board with a number of small balls and two bigger balls, representing human player ball and a bot (i.e. computer controlled) ball.  

<img src="board.png">

The number of small ball can be high (thousands). All balls that can move and bounce,  against the border or each other. We consider elastic collisions and friction force, so that a moving ball stops after a while. At the top of the board, in the corners, there are two circles representing holes. The score of the human and bot player is displayed somewhere: in the picture: in blue, on the left (human) and on the right (bot).


The objective of the game for the players (human and bot) is to kick the small balls in the holes, by throwing their own balls in a sequence of throws
- When a player puts a small ball in a hole, his/her score is incremented by one.
- If a small ball kicks another small balls in a hole, scores are not changed.
- The game ends when there are no more balls in the board and the winner is the player with the biggest score. 
- The game ends also if/when the ball of a player goes in a hole. In that case, the winner is the other player, in spite of the score.

To kick her/his ball, the human player can press keys - UP, DOWN, LEFT, RIGHT - to instantaneously update the velocity (simulating an impulse).
- For instance, by pressing UP the velocity vector can be updated by adding (0,1)

Players (human and bot) play asynchronously.

### The Assignment

Design and develop a concurrent version of `Poool`, in two different versions:
1)  one based on Java **multithreaded programming**, using only default/platform threads;
2)  a variant applying **Task-based** approach, using Java **Executor Framework**, where useful.


The concurrent programs should be designed according the principles studied during the course, promoting modularity, encapsulation as well as performance, reactivity. Further remarks:
- For active components/thread interaction, monitors must be used, with your own implementation (no lib support)
- The behaviour of the bot is not meant to be smart, could be any.
- For every other aspect not specified, students are free to choose the best approach for them.

The `assignment-01`folder in the repo includes some code sketches that could be used as a starting point. In particular:
- [`sketch01`](./sketch-01.md) is a simple sequential simulation of bouncing balls, including collisions and friction force
- [`sketch02`](./sketch-02.md) is an example of a GUI program with an asynchronous input management.

Beside the source code, the assignment should contain a brief report, including:
- A brief analsysis of the problem, focusing in particular aspects that are relevant from concurrent point of view.
- A description of the adopted design, the strategy and architecture.
- A description of the behaviour of the system using one or multiple Petri Nets, choosing the proper level of abstraction.
- Performance tests, to analyse and discuss the performance of the programs (for each version) compared to the sequential version
- Verification of the program or some parts of it, defining proper simplified models, using model-checking and JPF in particular. 


### The deliverable

The deliverable must be a zipped folder `Assignment-01`, to be submitted on the course web site, including:  
- `src` directory with sources
- `doc` directory with the report in PDF (`report.pdf`). 




