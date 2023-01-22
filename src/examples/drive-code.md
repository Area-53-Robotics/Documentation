# Drive Code
The first step of creating the basic code to control your robot is to define your devices.
```cpp
using namespace pros;
void opcontrol() {
    Controllor controller(E_CONTROLLER_MASTER);
    Motor motor_left(1);
    Motor motor_left(2, true); //This motor is reversed
  }
```
This will define a controller, and two motors, one on port 1, and the other on port 2. The full options for defining motors can be found [here](https://pros.cs.purdue.edu/v5/api/cpp/motors.html#constructor-s).

> Note: Astute readers will notice that due to the rules of scope, these devices will not be accessible outside of the opcontrol function. If you want these to exist in other parts of your program, either for auton or for configuration during initialize, you will need to define them outside of a function. Best practice is to put them in a header, and include them where you need them.

Now we need to read from the controller, in order to figure out how fast the driver wants the robot to move.
```cpp
using namespace pros;
int left_y = controller.get_analog(ANALOG_LEFT_Y);
int right_y = controller.get_analog(ANALOG_RIGHT_Y);
```
This will return an integer from -127 to 127, based on the joysticks position.

We don't want to just get this value once, we want it to update as the drive moves the joysticks. For this, we'll use an infinite loop.
```cpp
using namespace pros;
void opcontrol() {
    Controllor controller(E_CONTROLLER_MASTER);
    Motor motor_left(1);
    Motor motor_left(2, true);
    int left_y;
    int right_y;
    while (true) {
      left_y = controller.get_analog(ANALOG_LEFT_Y);
      right_y = controller.get_analog(ANALOG_RIGHT_Y);
      pros::delay(2); // allows other threads to run
      }
  }
```
## Tank Drive
But this code doesn't actually do anything yet. We still need to move the motors. The motors have a move method, that takes an integer from -127 to 127. Fortunately, thats exactly what the get_analog method returns.

```cpp
using namespace pros;
void opcontrol() {
    Controllor controller(CONTROLLER_MASTER);
    Motor motor_left(1);
    Motor motor_left(2, true);
    int left_y;
    int right_y;
    while (true) {
      left_y = controller.get_analog(ANALOG_LEFT_Y);
      right_y = controller.get_analog(ANALOG_RIGHT_Y);
      motor_left.move(left_y);
      motor_right.move(left_x);

      pros::delay(2);
      }
  }
```
This code will result in the drive controlling one half on the robot with one joystick, and the other half with the other.

## Arcade Drive
This is an alternate control scheme where one joystick controls forwards and backwards, and the other controls turning. Most people use tank drive, but the option exists.
```cpp
void opcontrol() {
  pros::Motor motor_left (1);
  pros::Motor motor_right (2, true);
  pros::Controller controller (CONTROLLER_MASTER);

  while (true) {
    int power = master.get_analog(ANALOG_LEFT_Y);
    int turn = master.get_analog(ANALOG_RIGHT_X);
    int left = power + turn;
    int right = power - turn;
    motor_left.move(left);
    motor_right.move(right);

    pros::delay(2);
  }
}

```

