
# C Programming Language Notes

Some notes on the C programming language. To compile and run a C program using
`gcc`:

```bash
$ gcc hello.c -o hello
$ ./hello
Hello, World!
```

## Variables and Types

Variables and constants are the basic data objects that can be used
in a program. These are referenced by name, these names are made up of
letters and digits, but the first character of the name need to be
a letter (the underscore `_` counts as a letter).

### Declarations

All variables must be declared before use. A declaration specifies a
type and a list of one or more variables of that type, for example:
```C
int i;
char c;
```
or, using a list of variables
```C
int max, min, step;
```
Variables can be initialized in the declaration, for example:
```C
int max = 10, min = 0, step = 2;
```

### Basic Data Types

There are four basic data types:

* `int` for integer numbers, for example `int i = 0;`.
* `char` for single characters, for example `char c = 'a';`.
* `float` for single-precision floating point, for example `float f = 3.14;`.
* `double` for double-precision floating point, for example `double d = 9e+12;`.

The following modifiers can be applied to these basic types: `short`, `long`, 
`signed`, and `unsigned`.

### Constants

Constants are fixed values that do not change during program
execution. This prevents unintended changing their values.

There are two ways of defining constants:

* `#define` use the preprocessor to define a constants.
* `const` using the reserved keyword to declare a constant variable.

Examples of the first option are:
```C
#define MAX  1000
#define NEWLINE '\n'
```
Where the `#define` keyword is followed by the name of the constant, and
the value, i.e.:
```
#define <name> <value>
```
During the preprocessor run, all the instances of the constant in the
program are replaced by the value.

The second option is prefixing a variable declaration with the `const`
keyword:
```C
const int length = 10;
```

## Operators 

The binary (use two operands) arithmetic operators are:

* `+` for summing values.
* `-` for subtracting.
* `*` for multiplication.
* `/` for division.
* `%` for the remainder of integer division.

The relational operators used to compare values are:

* `>` to test for greater then.
* `>=` for greater or equal than.
* `<`  for less than.
* `<=` for less or equal than.
* `==` for equality.
* `!=` for not equal.

Logical operators:

* `&&`
* `||`

When operators have different types, they are converted to a common type
(this is not always possible). In general the only automatic conversions are those
from a "narrower" operand into a "wider" operand without loosing information
(for example, from integer to float).

Type casting can be used to force a conversion of a value, by including the intended
type between parentheses. For example:

```C
int sum = 17, count = 5;
double mean;
mean = (double) sum / count;
```

## Arrays

An array is a structure to store a sequential, fixed size, collection of
elements of the same type. Arrays indexes in C start a 0. The generic
way of declaring arrays is:
```
<type> <name>[<size>];
```
For example, declare an array of integers of size 10 (the index of this
array goes from 0 to 9):
```C
int array[10];
```
Arrays can also be initialized in the declaration, for example to initialize
the previous example with the numbers from 1 to 10::
```C
int array[10] = {1,2,3,4,5,6,7,8,9,10};
```
To access the values of an array declare an expression with the array name,
and the index of the intended value, for example to add the first two
elements of the previous array:
```C
add = array[0] + array[1];
```
To scroll through an list of elements of an array of size `N` a loop can
be used, the following `for` loop iterates over all the elements of the
array, starting at index 0, and finishing at index `N-1`
```C
for (i = 0; i < N; i++) {
   (...)
}
```

### Strings

Strings are a specific example of a one-dimension array. Where each element
in the data collection is a single character. One important detail, the
last element in a string is *always* the literal `\0`. An example of
declaring and initializing a new string following the previous array
examples is:
```C
char str[] = {'H', 'e', 'l', 'l', 'o', '\0'};
```
The following shortcut can be used to achieve the same declaration:
```C
char str[] = "Hello";
```
Note that in the second option there is no need to explicitly add the
trailing `'\0'` literal. Strings can be transversed and handled like
any other array.

## Functions

Functions are used to organize a set of statements that execute a specific
task. This isolates specific parts of the program, allowing to write code
that is easier to read, understand and maintain.

The generic way for defining a function is:
```
<return_type> <name>(<argument_list>) {
  <body>
}
```
For example to declare a function named `add` that has two arguments (two)
numbers, and returns the numbers addition:
```C
int add(int x, int y) {
  return x+y;
}
```
The `return` keyword is used to return the intended value and control flow
back to the function caller.
To call a function, use the function name, and use parentheses to declare the
arguments list. For example to call the `add` function example to sum the
numbers `3` and `5`:
```C
sum = add(3, 5);
```
All function argument are passed to functions
by value for default, this means that you can change the value of the argument
inside a function without changing the original variable from which was called.
Arrays and strings are always passed by reference by default, this means that
if you change an array inside a function the original array will also be
change, because they point to the same data.

Functions must be declared before used, a function prototype (just the function
signature) can be made explicitly before describing the function body. For example,
the function prototype for the `add` function is:
```C
int add(int x, int y);
```

## *Structs*

## Pointers

## Files
