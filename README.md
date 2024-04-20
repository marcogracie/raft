# Raft implementation
## Overview
### Log
1. Just brought project in, see that
the starter code launches every replica, and
replicas consume data, gonna start by creating state with classes.
2. Have all replicas responding with a message of type fail.
3. Made it so these responses are now reached in the natural flow of program,
instead of directly calling send method.
4. Next going to encode the other info into response
5. cool now returning good looking json with leader as 'idk lol'
6. Time to bring some democracy on the scene
7. ELections are at a satisfactory level for milestone, I can see
in the simple tests we are cycling leaders more than neccessary,
this is my first priority to fix.
8. I fixed the elections cycling by setting the timer a little longer
9. implementing the log consensus proved to be difficult, but after a good deal of trial and error figured it out
10. accounting for dropped messages meant we had to keep track of append entries that were unACKed and periodically try them again
11. currently sending messages that are too big for OS, but saw this may not be a problem on the autograder, i will probably end up zipping 
the messages later though
### Properties/ Features
I think the best property of this code that made it quite maintainable and easy to debug is how I elected to track
state with objects, It handled the delegation of methods very well as all the classes stem from a common State
superclass that acts almost as a handler and routes commands to the appropriate service/ response depending on that
replica's state at that given moment. This structure made defining functions for each message type incredibly concise
and clean.
### Testing 
I tested the code by running the test suite many times, debugging using print statements, and also using the prints
to visually confirm the states of the systems were correct at any given time