# 💻 C Programming - MCS-201

**Master of Computer Applications (MCA) - Core Programming Course**

This folder contains comprehensive C programming study materials, code examples, practice problems, and learning resources for MCS-201.

---

## 📚 Course Overview

C Programming is the foundation of computer science. This course covers:
- Procedural programming fundamentals
- Memory management and pointers
- Data structures (arrays, strings)
- Modular programming with functions
- File handling and I/O operations
- Problem-solving through algorithms

---

## 🎯 Learning Objectives

By the end of this course, you will:
- ✅ Write efficient C programs
- ✅ Understand pointers and memory management
- ✅ Create and manipulate data structures
- ✅ Use functions for modular code
- ✅ Handle files and I/O operations
- ✅ Solve real-world problems with C
- ✅ Write clean, documented code

---

## 📖 Topics Covered

### 1. **Basics & Fundamentals** 🔧
```
├── Introduction to C
├── Setting up environment
├── First program (Hello World)
├── Data types (int, float, char, etc.)
├── Variables and constants
├── Input/Output (printf, scanf)
├── Comments and code structure
└── Compilation and execution
```

**Key Concepts:**
- Variable declaration and initialization
- Data type sizes and ranges
- Type casting
- Format specifiers (%d, %f, %s, %c)

**Resources:**
- [C Data Types - GeeksforGeeks](https://www.geeksforgeeks.org/data-types-in-c/)
- [C Variables - TutorialsPoint](https://www.tutorialspoint.com/cprogramming/c_variables.htm)

---

### 2. **Operators & Expressions** ➕
```
├── Arithmetic operators (+, -, *, /, %)
├── Relational operators (==, !=, <, >, <=, >=)
├── Logical operators (&&, ||, !)
├── Assignment operators (=, +=, -=, etc.)
├── Bitwise operators (&, |, ^, ~, <<, >>)
├── Operator precedence
└── Expression evaluation
```

**Key Concepts:**
- Operator precedence and associativity
- Short-circuit evaluation
- Ternary operator (?:)

**Example Code:**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 5;
    
    printf("Arithmetic: %d + %d = %d\n", a, b, a + b);
    printf("Relational: %d > %d = %d\n", a, b, a > b);
    printf("Logical: %d && %d = %d\n", a, b, a && b);
    
    return 0;
}
```

---

### 3. **Control Flow - Conditional Statements** 🔀
```
├── if statement
├── if-else statement
├── if-else if-else ladder
├── Nested if statements
├── Switch case
└── Ternary operator
```

**Key Concepts:**
- Boolean evaluation
- Statement blocks
- Nested conditionals
- Switch vs if-else

**Example Code:**
```c
#include <stdio.h>

int main() {
    int marks = 85;
    char grade;
    
    if (marks >= 90) grade = 'A';
    else if (marks >= 80) grade = 'B';
    else if (marks >= 70) grade = 'C';
    else grade = 'F';
    
    printf("Grade: %c\n", grade);
    return 0;
}
```

**Resources:**
- [C if-else - GeeksforGeeks](https://www.geeksforgeeks.org/c-if-else-statement/)
- [C switch - TutorialsPoint](https://www.tutorialspoint.com/cprogramming/c_switch.htm)

---

### 4. **Loops** 🔁
```
├── for loop
├── while loop
├── do-while loop
├── Nested loops
├── Loop control (break, continue)
├── Infinite loops
└── Loop optimization
```

**Key Concepts:**
- Loop initialization, condition, update
- Break and continue statements
- Loop flow control
- Nested loops and complexity

**Example Code:**
```c
#include <stdio.h>

int main() {
    // For loop
    for (int i = 1; i <= 5; i++) {
        printf("%d ", i);
    }
    printf("\n");
    
    // While loop
    int j = 1;
    while (j <= 5) {
        printf("%d ", j);
        j++;
    }
    printf("\n");
    
    return 0;
}
```

---

### 5. **Functions** 📞
```
├── Function declaration
├── Function definition
├── Function call
├── Return values
├── Parameters (formal & actual)
├── Function prototypes
├── Scope and lifetime
├── Recursion
└── Pass by value vs Pass by reference
```

**Key Concepts:**
- Function signature
- Local and global variables
- Static variables
- Function pointers
- Recursive functions

**Example Code:**
```c
#include <stdio.h>

// Function prototype
int factorial(int n);

int main() {
    printf("Factorial of 5: %d\n", factorial(5));
    return 0;
}

// Function definition
int factorial(int n) {
    if (n == 0 || n == 1)
        return 1;
    return n * factorial(n - 1);
}
```

**Resources:**
- [C Functions - GeeksforGeeks](https://www.geeksforgeeks.org/functions-in-c/)
- [C Recursion - TutorialsPoint](https://www.tutorialspoint.com/cprogramming/c_recursion.htm)

---

### 6. **Arrays** 📊
```
├── 1D Arrays
├── 2D Arrays
├── Multi-dimensional arrays
├── Array initialization
├── Array traversal
├── String handling (character arrays)
├── Array as function parameter
└── Dynamic arrays (malloc, calloc)
```

**Key Concepts:**
- Array indexing and bounds
- Memory layout
- String functions (strlen, strcpy, strcmp, etc.)
- Array of pointers

**Example Code:**
```c
#include <stdio.h>
#include <string.h>

int main() {
    // 1D Array
    int arr[5] = {1, 2, 3, 4, 5};
    
    // Array traversal
    for (int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
    
    // String (character array)
    char str[20] = "Hello, C!";
    printf("String: %s, Length: %lu\n", str, strlen(str));
    
    // 2D Array
    int matrix[2][3] = {{1, 2, 3}, {4, 5, 6}};
    
    return 0;
}
```

---

### 7. **Pointers** 🎯
```
├── Pointer declaration
├── Address-of operator (&)
├── Dereference operator (*)
├── Pointer arithmetic
├── Array pointers
├── String pointers
├── Pointer to pointer
├── Function pointers
├── Void pointers
└── Pointer advantages & risks
```

**Key Concepts:**
- Memory addresses
- Pointer operations
- Dynamic memory allocation
- Null pointers
- Dangling pointers

**Example Code:**
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Basic pointer
    int x = 10;
    int *ptr = &x;
    
    printf("x = %d\n", x);
    printf("Address of x: %p\n", ptr);
    printf("Value at ptr: %d\n", *ptr);
    
    // Dynamic memory
    int *arr = (int *)malloc(5 * sizeof(int));
    for (int i = 0; i < 5; i++) {
        arr[i] = i * 10;
    }
    
    free(arr);  // Important: Always free memory
    return 0;
}
```

**Resources:**
- [C Pointers - GeeksforGeeks](https://www.geeksforgeeks.org/pointers-in-c/)
- [C Dynamic Memory - TutorialsPoint](https://www.tutorialspoint.com/cprogramming/c_memory_management.htm)

---

### 8. **Structures** 🏗️
```
├── Structure declaration
├── Structure members
├── Structure initialization
├── Accessing members (. and ->)
├── Array of structures
├── Structures and functions
├── Nested structures
├── Typedef
└── Unions and enums
```

**Key Concepts:**
- Structure definition and usage
- Memory layout of structures
- Padding and alignment
- Bit fields

**Example Code:**
```c
#include <stdio.h>

struct Student {
    int rollNo;
    char name[50];
    float cgpa;
};

int main() {
    struct Student s1 = {101, "Tripti Mishra", 8.5};
    
    printf("Roll: %d, Name: %s, CGPA: %.2f\n", 
           s1.rollNo, s1.name, s1.cgpa);
    
    return 0;
}
```

---

### 9. **File Handling** 📁
```
├── File operations (open, read, write, close)
├── File pointers
├── File modes (r, w, a, r+, w+, a+)
├── Sequential vs Random access
├── Text file operations
├── Binary file operations
├── Error handling
└── File status checking
```

**Key Concepts:**
- File I/O functions (fopen, fclose, fprintf, fscanf)
- File positioning
- EOF detection
- Error checking

**Example Code:**
```c
#include <stdio.h>

int main() {
    FILE *file = fopen("data.txt", "w");
    
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }
    
    fprintf(file, "Hello, File Handling!\n");
    fprintf(file, "Learning C programming.\n");
    
    fclose(file);
    return 0;
}
```

**Resources:**
- [C File Handling - GeeksforGeeks](https://www.geeksforgeeks.org/basics-of-file-handling-in-c/)

---

## 💻 Practice Problems

### **Beginner Level** 🟢
- [ ] Simple calculator (add, subtract, multiply, divide)
- [ ] Check if number is odd or even
- [ ] Find maximum of three numbers
- [ ] Print multiplication table
- [ ] Sum of first N natural numbers
- [ ] Check if number is prime
- [ ] Factorial of a number
- [ ] Fibonacci series

### **Intermediate Level** 🟡
- [ ] Bubble sort implementation
- [ ] Linear search and binary search
- [ ] Reverse an array
- [ ] Find duplicate elements
- [ ] String manipulation (reverse, palindrome)
- [ ] Matrix operations (addition, multiplication)
- [ ] Linked list basics
- [ ] Stack and Queue implementation

### **Advanced Level** 🔴
- [ ] Tree data structures
- [ ] Graph algorithms
- [ ] Sorting algorithms (quick sort, merge sort)
- [ ] File compression
- [ ] Database-like operations
- [ ] Pattern matching algorithms

---

## 📊 Progress Tracking

| Topic | Status | Level | Date | Notes |
|---|---|---|---|---|
| Basics | ⏳ In Progress | Beginner | - | Learning fundamentals |
| Operators | ⏳ In Progress | Beginner | - | Understanding precedence |
| Conditionals | ⏳ Pending | Beginner | - | - |
| Loops | ⏳ Pending | Beginner | - | - |
| Functions | ⏳ Pending | Intermediate | - | - |
| Arrays | ⏳ Pending | Intermediate | - | - |
| Pointers | ⏳ Pending | Advanced | - | Complex topic |
| Structures | ⏳ Pending | Intermediate | - | - |
| File Handling | ⏳ Pending | Advanced | - | - |

---

## 📚 Recommended Resources

### **Online Tutorials**
- [GeeksforGeeks - C Programming](https://www.geeksforgeeks.org/c-programming-language/)
- [TutorialsPoint - C](https://www.tutorialspoint.com/cprogramming/)
- [W3Schools - C Basics](https://www.w3schools.com/c/)
- [Programiz - C Course](https://www.programiz.com/c-programming)

### **Books**
- "The C Programming Language" by Kernighan & Ritchie (Classic)
- "Let Us C" by Yashavant Kanetkar
- "C Programming Absolute Beginner's Guide" by Greg Perry

### **Practice Platforms**
- [HackerRank - C Challenges](https://www.hackerrank.com/domains/c)
- [LeetCode - C Problems](https://leetcode.com/)
- [CodeChef - C Problems](https://www.codechef.com/)
- [Codeforces - C Problems](https://codeforces.com/)

---

## 🛠️ How to Use This Folder

1. **Read the Topics** - Start from basics
2. **Study Examples** - Understand the code
3. **Write Code** - Create your own programs
4. **Solve Problems** - Practice daily
5. **Debug** - Learn from mistakes
6. **Optimize** - Improve your solutions
7. **Document** - Keep notes
8. **Revise** - Regular revision

---

## 💡 Study Tips

✨ **Daily Practice** - Code every day (1-2 hours minimum)
✨ **Write by Hand** - Before typing, write logic on paper
✨ **Understand Before Memorizing** - Focus on concepts, not syntax
✨ **Debug Actively** - Use debugger to step through code
✨ **Create Variations** - Modify examples to understand better
✨ **Read Others' Code** - Learn from different approaches
✨ **Participate in Communities** - Ask questions, help others
✨ **Build Projects** - Apply knowledge to real problems

---

## 🎯 Common Mistakes to Avoid

❌ Forgetting to initialize variables
❌ Array index out of bounds
❌ Memory leaks (not freeing malloc)
❌ Using uninitialized pointers
❌ Off-by-one errors in loops
❌ Not closing files after use
❌ Ignoring compiler warnings
❌ Not handling edge cases

---

## 📝 Quick Reference

### **Format Specifiers**
| Specifier | Type | Example |
|---|---|---|
| %d | Integer | 42 |
| %f | Float | 3.14 |
| %c | Char | 'A' |
| %s | String | "Hello" |
| %x | Hexadecimal | FF |

### **Common Library Functions**
| Function | Purpose | Example |
|---|---|---|
| strlen() | String length | strlen("Hello") |
| strcpy() | Copy string | strcpy(dest, src) |
| strcmp() | Compare strings | strcmp(s1, s2) |
| printf() | Print output | printf("%d", x) |
| scanf() | Read input | scanf("%d", &x) |
| malloc() | Allocate memory | malloc(10 * sizeof(int)) |
| free() | Free memory | free(ptr) |

---

## 🏆 Learning Milestones

- **Week 1-2** ✅ Basics & Operators
- **Week 3-4** ✅ Control Flow & Loops
- **Week 5-6** ✅ Functions & Arrays
- **Week 7-8** ✅ Pointers & Structures
- **Week 9-10** ✅ File Handling & Projects
- **Week 11-12** ✅ Revision & Practice Tests

---

## 📞 Need Help?

- 📧 Email: tripti.m2026@gmail.com
- 🔗 LinkedIn: https://www.linkedin.com/in/tripti-mishra-4a68881ba/
- 💻 GitHub: https://github.com/Tripti-crpto

---

**Happy Coding! Remember: "The only way to learn programming is by programming!" 🚀**

---

*Last Updated: May 18, 2026*
