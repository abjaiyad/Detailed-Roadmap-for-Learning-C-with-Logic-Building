# Roadmap for Learning C Programming with Logic Building

```plaintext
This roadmap provides a step-by-step guide for mastering C programming, 
focusing on building strong logic and problem-solving skills.

Phase 1: Basics of C Programming:
1. Set up your C development environment (e.g., GCC, Visual Studio Code).
2. Understand the structure of a C program.
3. Learn input/output functions (`printf` and `scanf`).
4. Study basic data types: `int`, `float`, `char`, etc.
5. Write simple programs like calculating area or displaying patterns.

Example: Hello World Program:
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}

Example: Simple Calculator:
#include <stdio.h>

int main() {
    float num1, num2, sum;

    printf("Enter two numbers: ");
    scanf("%f %f", &num1, &num2);

    sum = num1 + num2;

    printf("Sum: %.2f\n", sum);
    return 0;
}

Phase 2: Control Flow:
1. Learn conditional statements (`if-else`, `switch-case`).
2. Master loops (`for`, `while`, `do-while`) for iteration.
3. Practice solving logic problems such as finding even/odd numbers.
4. Explore nested loops for complex patterns.

Example: Check for Even or Odd Number:
#include <stdio.h>

int main() {
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (num % 2 == 0)
        printf("%d is even.\n", num);
    else
        printf("%d is odd.\n", num);

    return 0;
}

Example: Multiplication Table Using Loops:
#include <stdio.h>

int main() {
    int num, i;

    printf("Enter a number: ");
    scanf("%d", &num);

    for (i = 1; i <= 10; i++) {
        printf("%d x %d = %d\n", num, i, num * i);
    }

    return 0;
}

Phase 3: Functions and Recursion:
1. Understand how to create reusable code blocks with functions.
2. Learn about function arguments and return values.
3. Explore recursion to solve complex problems such as Fibonacci and factorials.

Example: Function to Calculate Square:
#include <stdio.h>

int square(int num) {
    return num * num;
}

int main() {
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    printf("Square of %d is %d\n", num, square(num));
    return 0;
}

Example: Fibonacci Sequence Using Recursion:
#include <stdio.h>

int fibonacci(int n) {
    if (n == 0)
        return 0;
    if (n == 1)
        return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    int n, i;

    printf("Enter the number of terms: ");
    scanf("%d", &n);

    printf("Fibonacci Series:\n");
    for (i = 0; i < n; i++) {
        printf("%d ", fibonacci(i));
    }
    printf("\n");

    return 0;
}

Phase 4: Arrays and Strings:
1. Work with single-dimensional arrays and multi-dimensional arrays.
2. Learn string manipulation using character arrays.
3. Solve problems such as searching and sorting arrays.

Example: Sum of Array Elements:
#include <stdio.h>

int main() {
    int arr[5], sum = 0, i;

    printf("Enter 5 numbers:\n");
    for (i = 0; i < 5; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }

    printf("Sum of elements: %d\n", sum);
    return 0;
}

Example: Reverse a String:
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], rev[100];
    int i, length;

    printf("Enter a string: ");
    gets(str);

    length = strlen(str);
    for (i = 0; i < length; i++) {
        rev[i] = str[length - i - 1];
    }
    rev[length] = '\0';

    printf("Reversed String: %s\n", rev);
    return 0;
}

Phase 5: Pointers and Dynamic Memory:
1. Understand pointers and pointer arithmetic.
2. Manage dynamic memory using `malloc`, `calloc`, and `free`.
3. Solve problems involving pointer-based logic.

Example: Swapping Numbers Using Pointers:
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x, y;

    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);

    printf("Before swap: x = %d, y = %d\n", x, y);
    swap(&x, &y);
    printf("After swap: x = %d, y = %d\n", x, y);

    return 0;
}

Example: Dynamic Memory Allocation:
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *arr, n, i;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    arr = (int*)malloc(n * sizeof(int));
    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Enter %d elements:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    printf("The elements are:\n");
    for (i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    free(arr);
    return 0;
}

Phase 6: Advanced Concepts:
1. Learn structures for grouping related data.
2. Explore file handling for reading/writing files.
3. Implement data structures like linked lists, stacks, and queues.
4. Practice advanced algorithms such as sorting and searching.

Example: File Handling (Write and Read):
#include <stdio.h>

int main() {
    FILE *file;
    char text[100];

    file = fopen("example.txt", "w");
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    printf("Enter text to write to the file: ");
    gets(text);

    fprintf(file, "%s", text);
    fclose(file);

    file = fopen("example.txt", "r");
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    printf("Content of the file:\n");
    while (fgets(text, sizeof(text), file)) {
        printf("%s", text);
    }
    fclose(file);

    return 0;
}

Tips for Learning:
1. Practice daily to strengthen logic and problem-solving skills.
2. Refer to classic books like "The C Programming Language" by Kernighan and Ritchie.
3. Solve coding challenges on platforms like LeetCode, HackerRank, or Codeforces.
