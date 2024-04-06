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