# Variables
Variables are names associated with values. Different variables are specified by their name so other programmers can easily identify what the variable is for and what type of value it is associated.

## Initialization
variables definitions follow the pattern of:
```
datatype name = value;
```

for example:
```cpp
int number = 42;
```
In this example, we create a variable called number. It has value 42. We can display this value by using a print statement.

```cpp
printf("%i\n",number);
//will display 42 to the terminal
```
> Note: \n indicates a newline. We will cover printf more in depth in a later chapter.
## Datatypes
If you've used a language like python or javascipt before, these will be unfamiliar to you. Each variable in C++ must be annotated with a datatype. Datatypes include:
```cpp
char character = 'b';
std::string word = "Hello!";
int number = 42;
float decimal = 4.2;
bool condition = false; // Can also be true
```
## Strong Typing
C++ is a strongly typed language. This means that you cannot do operations on variables that do not have a matching type. This means that you cannot add a string to a number. You also cannot assign a value to a variable that doesn't match it's datatype.
```cpp
char character = "abcdefg"; // This will not work
int number = 4.2; // This will not work
int num = 42; // This will work
std::string word =  "word" + num; // This will not work
```

