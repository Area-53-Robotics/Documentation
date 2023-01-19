# Buttons
There are many use cases for buttons. Maybe you want to trigger an action on a subsystem, toggle a piston, or select an autonomous. Regardless, reading input from the buttons is simple.
```cpp
using namespace pros;
void opcontrol(){
  Controller controller (CONTROLLER_MASTER);
  Motor arm(1);
  while (true) {
    if (controller.get_digital(DIGITAL_R1)) {
      arm.move_velocity(100); // This is 100 because it's a 100rpm motor
    }
    else if (controller.get_digital(DIGITAL_R2)) {
      arm.move_velocity(-100); 
    }
    else {
      arm.move_velocity(0); // Default condition
    }
    delay(2);
  }
}
```
However, this will only work for held actions. This code will continually set the arm's velocity to 100. If you only want an action to trigger once, you have to use the get_digital_new_press method of the controller.
```cpp
void opcontrol(){
  Controller controller (CONTROLLER_MASTER);
  Motor arm(1);
  bool is_arm_spinning = false;
  while (true) {
    if (controller.get_digital_new_press(DIGITAL_R1)) {
      is_arm_spinning = !is_arm_spinning; // If its true, set to false, and vice versa
    }
    if (is_arm_spinning) {
        arm.move_velocity(100) ; 
      } else {
          arm.move_velocity(0);
        }
        delay(2);
    }
  }
}
```
You need this alternative method because of how fast the loop runs. You cannot guarantee how many times the loop will run while the drive presses the button. This method only registers true once per button press, regardless of how long the drive presses the button.
