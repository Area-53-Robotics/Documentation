# Program Structure
Program organization is a critical part of programming, that is very subjective. This of course means that no one can agree on how it should be done. However, there are a few general guidelines that you should follow.

## Main File
PROS projects have no main file, however the concept still applies. The only function you should define in your main file is main. The main file is for executing code, not defining it. The same principle applies to your opcontrol and autonomous functions (as well as functions like disabled). These act as the main functions for VEX, and should be treated as such.

## Splitting Up Your Main File
In PROS, everything in the src folder gets compiled. This means that you can define opcontrol and autonomous in any file, so long as they're only defined once. This means that you can split your opcontrol code and autonomous code into their own files.


## Header Files
There is typically one header file for each body file that you define. You only need to create headers for files that contain things that you want to access in other parts of your program. For example if I have a body file called utils.cpp, I would also create a file called utils.hpp. The folder structure of your headers should mirror the structure of your body files. For example if I have a folder called helpers, and in that folder I have auton.cpp, opcontrol.cpp, and misc.cpp, I would also create a folder for my headers called helpers, and in that folder I would create auton.hpp, opcontrol.hpp, and misc.hpp.
