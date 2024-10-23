
# C Programming Example question solutions

## I've made sure to add common mistakes we would usually make while writting these programs as comments btw

## 1. Program to print "Hello World"
```c
#include <stdio.h>

int main() {
    printf("Hello World\n");
    return 0;
}
```

## 2. Program to initialize a keyword and attempt to change its value
```c
#include <stdio.h>

int main() {
    const int a = 10;  // 'const' keyword is used for constant values
    // a = 20;  // This will cause a compilation error because 'a' is constant
    printf("Value of a: %d\n", a);
    return 0;
}
```
Output: If you uncomment the line `a = 20;`, it will give a compilation error since you cannot modify a `const` variable.

## 3. Program to take a float value as input, multiply by 3, and print it
```c
#include <stdio.h>

int main() {
    float num;
    printf("Enter a float number: ");
    scanf("%f", &num);
    printf("Result: %.2f\n", num * 3);
    return 0;
}
```

## 4. Program to take input of variables of all built-in data types and print them with their sizes
```c
#include <stdio.h>

int main() {
    int i;
    float f;
    char c;
    double d;

    printf("Enter an integer: ");
    scanf("%d", &i);

    printf("Enter a float: ");
    scanf("%f", &f);

    printf("Enter a character: ");
    scanf(" %c", &c);

    printf("Enter a double: ");
    scanf("%lf", &d);

    printf("Integer: %d, Size: %lu bytes\n", i, sizeof(i));
    printf("Float: %f, Size: %lu bytes\n", f, sizeof(f));
    printf("Character: %c, Size: %lu bytes\n", c, sizeof(c));
    printf("Double: %lf, Size: %lu bytes\n", d, sizeof(d));

    return 0;
}
```

## 5. Program to take `int` and `float` input and print them with incorrect format specifiers
```c
#include <stdio.h>

int main() {
    int i;
    float f;

    printf("Enter an integer: ");
    scanf("%d", &i);

    printf("Enter a float: ");
    scanf("%f", &f);

    printf("Printing integer as float: %f\n", i);  // Incorrect specifier
    printf("Printing float as integer: %d\n", (int)f);  // Incorrect specifier
    return 0;
}
```
The output interpretation would show undefined behavior because the format specifiers are mismatched.

## 6. Program to multiply three integers and store the result in both `float` and `int`
```c
#include <stdio.h>

int main() {
    int a, b, c;
    int result_int;
    float result_float;

    printf("Enter three integers: ");
    scanf("%d %d %d", &a, &b, &c);

    result_int = a * b * c;
    result_float = (float)(a * b * c);

    printf("Result stored in int: %d\n", result_int);
    printf("Result stored in float: %.2f\n", result_float);

    return 0;
}
```

## 7. Program using `math.h` functions
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = -9.8;

    printf("Ceil of %f: %.2f\n", num, ceil(num));
    printf("Floor of %f: %.2f\n", num, floor(num));
    printf("Absolute value: %.2f\n", fabs(num));
    printf("Log of 10: %.2f\n", log(10));
    printf("Log base 10 of 100: %.2f\n", log10(100));

    return 0;
}
```
Ensure to compile with `-lm` to link the math library: `gcc program.c -lm`.

## 8. Program using a Macro
```c
#include <stdio.h>

#define PI 3.14

int main() {
    printf("Value of PI: %f\n", PI);
    // PI = 3.1415;  // Error: Macro values cannot be changed.
    return 0;
}
```

## 9. Program to demonstrate scope of variables
```c
#include <stdio.h>

int global_var = 10;

void printLocalVar() {
    int local_var = 20;
    printf("Local variable: %d\n", local_var);
}

int main() {
    printLocalVar();
    printf("Global variable: %d\n", global_var);
    // printf("Local variable outside function: %d\n", local_var);  // Error: Out of scope
    return 0;
}
```

## 10. Program using Macro as a function
```c
#include <stdio.h>

#define PRINT_VAR(x) printf("Variable: %d\n", x)

int main() {
    int var = 100;
    PRINT_VAR(var); // note that this is am extremely basic example, you probably would have to do something like adding two numbers to make the teacher happy with your program
    return 0;
}
```
