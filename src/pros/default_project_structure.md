# Project Structure
The default pros project is structured as follows
```
project
│   project.pros        (used by PROS CLI to know kernel version and other metadata)
│   Makefile            (instructs make how to compile your project)
|   common.mk           (helper file for Makefile)
│
└───src                 (source files should go here)
│   │   main.cpp        (source for competition task functions, like operator control and autonomous)
|
└───include             (Header files should go in here)
│   │   api.h           (Lets source files know PROS API functions)
│   │   main.h          (Includes api.h and anything else you want to include project-wide)
|   └───pros            (Contains all of the specific header files for the PROS API functions)
|   └───okapi           (Contains all of the header files for OkapiLib)
|   └───display         (Contains all of the header files for LVGL, the graphics library for the V5 screen)
│
└───firmware
│   libpros.a       (Pre-compiled PROS library)
│   okapilib.a      (Pre-compiled OkapiLib library)
|   v5.ld           (Instructs the linker how to construct binaries for the V5)
```

Most of these files are automatically generated, and should not be touched. Src contains all of your body files, and include contains all of your header files. Due to how pros is built, all files in these directories are compiled when you run pros make. The only files that you should edit are main.h and main.cpp

main.cpp contains these functions:
```cpp
// main.cpp
void initialize() {}
void disabled() {}
void competition_initialize() {}
void autonomous() {}
void opcontrol() {}
```
Most of these functions are self explanatory, and have comments describing their purpose.

Opcontrol contains an infinite loop, because it is meant to run until the program is killed.

