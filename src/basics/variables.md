# Variables
Variables are names associated with values. Different variables are specified by their name so other programmers can easily identify what the variable is for and what type of value it is associated.
## Data Types

Data types are used to categorize values that a variable is associated with.

Integer (Int)

- The integer data type classifies variables as whole numbers.

```cpp
int age;
```

Age would be classified as an integer because age is always a whole number.

#

Floating Point (float)

- The float data type classifies variables as decimals.

```cpp
float gpa;
```

GPA would be classified as a floating point because your GPA can vary between a whole number and a decimal.

#

Character (char)

- The character data type classifies variables as letters.

```cpp
char grade;
```

Your grade would be best classified as a character because letters are typically used to categorize them.

#

String (string)

- The string data type classifies variables as words, phrases, or sentences.

```cpp
std::string greeting = "Hello world!";
```

> Note: The string data type requires the std namespace ([explained here](basics/namespaces.md)) to function, unlike other data types.

A greeting would be classified as a string because greetings are conveyed with words.

#

Boolean (bool)

- The boolean data type classifies variables as either true (0) or false (1).

```cpp
bool lightbulb;
```

A lightbulb would be classified as a boolean because lights can either be on or off, which is two choices.

#

## Data Type Modifiers

Data type modifiers change the parameters of a data type, and are known as signed, unsigned, short, and long. Signed and unsigned modifiers can only be used with integers while short and long modifiers can be used with integers and characters.

### Signed and Unsigned

Signed variables are able to hold positive and negative values.

```cpp
signed int x;
signed int y;
```

If you are tracking a point on a grid, using signed variables for the x and y coordinates allows you to track the location of the point anywhere on the grid.

Unsigned variables, however, only hold positive values.

```cpp
unsigned int direction_degrees;
```

Degrees consist of values between 0 and 360, which never results in a negative integer. Therefore, an unsigned integer would be valid to use in this context.

### Short and Long

Short variables adjust the range of values, from −32,767 to +32,767.

```cpp
short int population_city;
```

Long variables adjust the range of values, from  -2,147,483,647 to +2,147,483,647.

```cpp
long int population_world;
```

These data type modifiers can be used interchangably, like `unsigned long int` or `signed short int`.

#

## Advanced Data Types

Certain data types vary based on the size of the value.

Integer (Int)

- int08_t

An 8-bit integer holds values up to 255.

- int16_t

A 16-bit integer holds values up to 32,767.

- int32_t

A 32-bit integer holds values up to 2,147,483,647

- int64_t

A 64-bit integer holds values up to 9,223,372,036,854,775,807.