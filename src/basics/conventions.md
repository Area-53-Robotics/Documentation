# Conventions
Coding conventions are general guidelines for creating clean, readable, structured, and interpretable code. While you can make a program following no coding conventions that works well, following some form of conventions can make mistakes less likely and collaboration much, much easier. Furthermore, it can be helpful for impressing judges. Here are some conventions we've compiled that you may find useful for your programs.

## Naming conventions
### Be descriptive!!!
In general, strive for descriptive variable and function names. Imagine that someone else is trying to read your code. Would they be more likely to understand a variable named ```p```, or one named ```motor_power```? 

Unless it's for a loop, **avoid single-letter variable names**. Don't even think about creating single-letter function names.
### Use underscores
Use lowercase for variable and function names, with underscores between each word.
```cpp
// Variable examples
int AutonomousSelection; // No
int autonomous_selection; // Yes

int J1; // No
int right_x_axis; // Yes

motor LeftMotor(1); // No
motor left_motor(1); // Yes

int DriveCurve(int x); // No
int drive_curve(int input); // Yes
```
## Use header files
To be added
## Use comments (intelligently)
To be added

## Sources:
Descriptions + caveats to be added
1. https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-naming
2. https://google.github.io/styleguide/cppguide.html#Variable_Names