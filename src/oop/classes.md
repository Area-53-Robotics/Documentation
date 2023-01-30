# Classes
You can define a class as follows:
```cpp
class Car {
    public:
    int speed;
    Color color; // enum
    int wheel_size;
    void drive(); // you can define functions as a part of classes
};

// You can define a new object like this
Car volvo;
// Member variables are uninitialized by default
volvo.speed = 3;
volvo.color = Red;
volvo.wheel_size = 2
volvo.drive();
```
## Class Members
Almost anything can be part of a class. Enums, functions, objects, and of course variables, can all be a part of a class.


## Public vs Private
In our class definition, all of our members are public. This means that they can be accessed outside of the class. This is why we can assign values to the variables after the object is defined. Good practice is to only give public access to things that really need it. A good rule to follow is to make everything private by default, and then make things public as needed.

There are other member categories, like protected and friend, but those will not be covered here.

```cpp
class Car {
    private:
    int speed,
};

Car volvo;
volvo.speed = 3; // This will not work
```