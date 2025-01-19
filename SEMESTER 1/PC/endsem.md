# Pointers in C

Pointers are a fundamental concept in C programming, enabling direct memory access and manipulation. Understanding them is crucial for dynamic memory allocation, array and string handling, and implementing data structures.

---

## **What Are Pointers?**
A **pointer** is a variable that stores the memory address of another variable.

### **Declaration and Initialization of Pointers**
**Syntax:**
```c
data_type *pointer_name;
```

**Example:**
```c
int x = 10;
int *p = &x;  // p holds the address of x
```
- `*p`: Dereferences the pointer to access the value stored at the address.
- `&x`: Address-of operator gives the memory address of `x`.

---

## **Memory Representation**
Every variable in C is stored at a specific **memory location**. A pointer variable stores the **address** of another variable, not its actual value.

---

## **Pointer Operations**

### 1. **Dereferencing a Pointer:**
Access the value at the memory address the pointer points to.
```c
int a = 5;
int *p = &a;
printf("Value of a: %d\n", *p);  // Output: 5
```

### 2. **Pointer Arithmetic:**
Pointers can be incremented (`p++`), decremented (`p--`), or used in expressions.
- Incrementing a pointer moves it to the next memory location based on the data type size.
```c
int arr[3] = {10, 20, 30};
int *p = arr;
printf("%d\n", *p);   // Output: 10
p++;
printf("%d\n", *p);   // Output: 20
```

---

## **Pointers and Arrays**
- The name of an array acts as a pointer to its first element.

**Example:**
```c
int arr[3] = {1, 2, 3};
int *p = arr;
printf("%d\n", *(p + 1));  // Access second element: Output: 2
```

---

## **Pointers and Strings**
Strings in C are arrays of characters and can be manipulated using pointers.

**Example:**
```c
char str[] = "Hello";
char *p = str;
while (*p != '\0') {
    printf("%c", *p);
    p++;
}
```

---

## **Pointers and Functions**

### 1. **Pass by Value vs Reference:**
- Pass by value: Changes in the function do not affect the original variable.
- Pass by reference: Use pointers to pass the address of a variable. Changes affect the original variable.

**Example:**
```c
void modify(int *x) {
    *x = 20;  // Modifies the value at the address
}
int main() {
    int a = 10;
    modify(&a);
    printf("%d", a);  // Output: 20
}
```

### 2. **Pointers to Pointers:**
A pointer to a pointer stores the address of another pointer.
```c
int x = 10;
int *p = &x;
int **pp = &p;
printf("%d\n", **pp);  // Output: 10
```

---

## **Dynamic Memory Allocation**
Pointers are essential for dynamic memory allocation using functions like:
- `malloc()`: Allocates memory.
- `calloc()`: Allocates and initializes memory.
- `free()`: Frees allocated memory.

**Example:**
```c
int *ptr = (int *)malloc(sizeof(int));
*ptr = 50;
printf("%d\n", *ptr);  // Output: 50
free(ptr);  // Free the allocated memory
```

---

## **Common Use Cases of Pointers**
1. **Dynamic Arrays:** Efficient memory allocation and resizing.
2. **Structures:** Pass large data structures efficiently.
3. **Strings:** Manipulate and traverse strings.
4. **Data Structures:** Implement linked lists, trees, graphs, etc.

---

## **Common Errors and Pitfalls**
1. **Dangling Pointers:** A pointer pointing to freed or invalid memory.
2. **Null Pointers:** Always initialize pointers to `NULL` if not assigned.
   ```c
   int *p = NULL;
   ```
3. **Segmentation Fault:** Dereferencing an invalid or uninitialized pointer.
4. **Pointer Arithmetic:** Ensure arithmetic stays within valid memory bounds.

---

## **Example Programs**

### **1. Swapping Two Numbers Using Pointers**
```c
#include <stdio.h>

void swap(int *x, int *y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}

int main() {
    int a = 10, b = 20;
    printf("Before swap: a = %d, b = %d\n", a, b);
    swap(&a, &b);
    printf("After swap: a = %d, b = %d\n", a, b);
    return 0;
}
```

---

### **2. Traversing and Modifying an Array Using Pointers**
```c
#include <stdio.h>

void modifyArray(int *arr, int size) {
    for (int i = 0; i < size; i++) {
        *(arr + i) += 5;  // Increment each element by 5
    }
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int size = sizeof(arr) / sizeof(arr[0]);

    printf("Original Array: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }

    modifyArray(arr, size);

    printf("\nModified Array: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

---

# Functions in C

Functions are reusable blocks of code that perform a specific task. They enhance code modularity, readability, and reusability in C programs.

---

## **What Are Functions?**
A function is a self-contained block of code designed to perform a specific task.

### **Types of Functions**
1. **Built-in Functions:** Provided by C libraries (e.g., `printf`, `scanf`, `sqrt`).
2. **User-defined Functions:** Created by the programmer to perform specific tasks.

---

## **Advantages of Functions**
1. **Code Reusability:** Avoid rewriting the same code.
2. **Modularity:** Divide a program into smaller, manageable parts.
3. **Ease of Debugging:** Debug smaller functions independently.
4. **Reduced Redundancy:** Use function calls to execute the same logic multiple times.

---

## **Syntax of a Function**
```c
return_type function_name(parameter_list) {
    // Function body
    return value; // Optional, only if the function has a non-void return type
}
```

**Example:**
```c
int add(int a, int b) { // Function declaration and definition
    return a + b;      // Returns the sum of a and b
}
```

---

## **Types of Function Parameters**
1. **Pass by Value:** A copy of the argument is passed. Changes in the function do not affect the original variable.
2. **Pass by Reference:** The address of the argument is passed. Changes in the function affect the original variable.

---

## **Example Programs**

### **1. Function to Add Two Numbers (Pass by Value)**
```c
#include <stdio.h>

// Function to add two numbers
int add(int a, int b) {
    // The sum is calculated inside the function
    return a + b;
}

int main() {
    int num1 = 5, num2 = 10;

    // Call the function and store the result
    int result = add(num1, num2);

    // Output the result
    printf("The sum of %d and %d is %d\n", num1, num2, result);

    return 0;
}
```
**Output:**
```
The sum of 5 and 10 is 15
```
---

### **2. Swapping Two Numbers (Pass by Reference)**
```c
#include <stdio.h>

// Function to swap two numbers using pointers
void swap(int *x, int *y) {
    int temp = *x; // Store the value of x temporarily
    *x = *y;      // Assign the value of y to x
    *y = temp;    // Assign the stored value of x to y
}

int main() {
    int a = 5, b = 10;

    printf("Before swap: a = %d, b = %d\n", a, b);

    // Call the function with the addresses of a and b
    swap(&a, &b);

    printf("After swap: a = %d, b = %d\n", a, b);

    return 0;
}
```
**Output:**
```
Before swap: a = 5, b = 10
After swap: a = 10, b = 5
```
---

### **3. Factorial Using Recursion**
```c
#include <stdio.h>

// Recursive function to calculate factorial
int factorial(int n) {
    if (n == 0 || n == 1) { // Base case: factorial of 0 or 1 is 1
        return 1;
    } else {
        return n * factorial(n - 1); // Recursive step
    }
}

int main() {
    int num = 5;

    // Call the recursive function
    int result = factorial(num);

    printf("The factorial of %d is %d\n", num, result);

    return 0;
}
```
**Output:**
```
The factorial of 5 is 120
```
---

### **4. Checking Prime Numbers Using Functions**
```c
#include <stdio.h>
#include <stdbool.h>

// Function to check if a number is prime
bool isPrime(int n) {
    if (n <= 1) {
        return false; // Numbers <= 1 are not prime
    }
    for (int i = 2; i <= n / 2; i++) {
        if (n % i == 0) {
            return false; // Found a divisor, not prime
        }
    }
    return true; // Prime if no divisors are found
}

int main() {
    int num = 17;

    // Call the function and store the result
    if (isPrime(num)) {
        printf("%d is a prime number\n", num);
    } else {
        printf("%d is not a prime number\n", num);
    }

    return 0;
}
```
**Output:**
```
17 is a prime number
```
---

### **Key Points to Remember**
1. Functions improve code modularity and readability.
2. Use **pass by reference** when you want the changes made inside the function to reflect outside.
3. Recursive functions are powerful but can lead to stack overflow if not carefully implemented.
