# Constructors
The way we had to assign values to members in the last chapter was pretty clunky. It required multiple lines, and all of the variables had to be public. However, there is a solution to this problem called constructors. Constructors are a special type of functions that return an instance of a class. They must have the same name as class.

```cpp
class Car {
    public:
    Car(int input) {
        speed = input;
    }
    private:
    int speed;
};

// Now we can use our constructor like this:
Car volvo(3);
```

## Initializer Lists
C++ provides even more shorthand for initializing variables. Initializer lists are a quick way to assign values to members of a class.

```cpp
class Car {
    public:
    Car();
    private:
    int speed;
    int wheel_size;
};

Car::Car(int speed, int wheel_size):
    speed(speed),
    wheel_size(wheel_size),
{
    // More complicated stuff should go here
}