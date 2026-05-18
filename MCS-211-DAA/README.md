# 🧮 Design & Analysis of Algorithms - MCS-211

**Master of Computer Applications (MCA) - Algorithms & Complexity Course**

This folder contains comprehensive study materials on algorithm design, analysis, complexity, and implementations for MCS-211.

---

## 📚 Course Overview

Design and Analysis of Algorithms is crucial for:
- Creating efficient solutions
- Understanding computational complexity
- Optimizing software performance
- Solving real-world problems effectively
- Preparing for technical interviews

**Core Topics:**
- Algorithm fundamentals and analysis
- Complexity analysis (Time & Space)
- Sorting and searching algorithms
- Divide and conquer
- Greedy algorithms
- Dynamic programming
- Graph algorithms
- NP-Completeness

---

## 🎯 Learning Objectives

By completing this course, you will:
- ✅ Understand algorithm design principles
- ✅ Analyze time and space complexity
- ✅ Master sorting algorithms
- ✅ Implement search techniques
- ✅ Apply divide-and-conquer strategies
- ✅ Use dynamic programming
- ✅ Solve graph problems
- ✅ Compare algorithm efficiency
- ✅ Optimize code performance

---

## 📖 Topics Covered

### 1. **Algorithm Basics** 🔧
```
├── Definition of Algorithm
├── Algorithm vs Program
├── Algorithm Properties
├── Problem Solving Approaches
├── Algorithm Design Paradigms
└── Pseudocode Writing
```

**Key Concepts:**
- Correctness and efficiency
- Deterministic vs Non-deterministic
- Algorithm specification
- Input/Output specifications

**Example:**
```
Algorithm: Linear Search
Input: Array arr[], target value x
Output: Index if found, -1 otherwise

1. for i = 0 to length(arr)-1
2.     if arr[i] == x
3.         return i
4. return -1
```

**Resources:**
- [Algorithm Design - GeeksforGeeks](https://www.geeksforgeeks.org/algorithm/)

---

### 2. **Complexity Analysis** 📊
```
├── Time Complexity
├── Space Complexity
├── Best, Average, Worst Cases
├── Asymptotic Notations
├── Big O, Big Omega, Big Theta
├── Complexity Classes
└── Recurrence Relations
```

**Key Concepts:**
- Analyzing algorithm performance
- Identifying bottlenecks
- Comparing algorithms
- Scalability assessment

**Big O Complexity Chart:**
```
┌─────────────────────┬──────────────────┐
│ Notation | Name      │ Growth Rate      │
├─────────────────────┼──────────────────┤
│ O(1)     | Constant  │ Fastest          │
│ O(log n) | Logarithmic│ Very Fast        │
│ O(n)     | Linear    │ Fast             │
│ O(n log n)| Linearithmic│ Moderate       │
│ O(n²)    | Quadratic │ Slow             │
│ O(n³)    | Cubic     │ Slower           │
│ O(2ⁿ)    | Exponential│ Very Slow       │
│ O(n!)    | Factorial │ Extremely Slow   │
└─────────────────────┴──────────────────┘
```

**Example Analysis:**
```c
// O(1) - Constant
int first_element = arr[0];

// O(n) - Linear
for (int i = 0; i < n; i++) {
    printf("%d ", arr[i]);
}

// O(n²) - Quadratic
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        printf("%d ", matrix[i][j]);
    }
}

// O(log n) - Logarithmic
while (low <= high) {
    mid = (low + high) / 2;
    // binary search logic
}
```

**Resources:**
- [Big O Notation - GeeksforGeeks](https://www.geeksforgeeks.org/analysis-of-algorithms-set-1-asymptotic-analysis/)
- [Big O Cheat Sheet](https://www.bigocheatsheet.com/)

---

### 3. **Sorting Algorithms** 🔀
```
├── Bubble Sort
├── Insertion Sort
├── Selection Sort
├── Merge Sort
├── Quick Sort
├── Heap Sort
├── Counting Sort
├── Radix Sort
└── Shell Sort
```

**Comparison Table:**
| Algorithm | Time (Avg) | Time (Worst) | Space | Stable | Use Case |
|---|---|---|---|---|---|
| Bubble Sort | O(n²) | O(n²) | O(1) | Yes | Small datasets, simple |
| Insertion Sort | O(n²) | O(n²) | O(1) | Yes | Nearly sorted data |
| Merge Sort | O(n log n) | O(n log n) | O(n) | Yes | Large datasets, stability |
| Quick Sort | O(n log n) | O(n²) | O(log n) | No | General purpose, efficient |
| Heap Sort | O(n log n) | O(n log n) | O(1) | No | In-place sorting |

**Merge Sort Example:**
```c
void merge_sort(int arr[], int left, int right) {
    if (left < right) {
        int mid = left + (right - left) / 2;
        
        // Sort left and right halves
        merge_sort(arr, left, mid);
        merge_sort(arr, mid + 1, right);
        
        // Merge sorted halves
        merge(arr, left, mid, right);
    }
}
```

**Resources:**
- [Sorting Algorithms - GeeksforGeeks](https://www.geeksforgeeks.org/sorting-algorithms/)
- [Visualgo - Sorting Visualization](https://visualgo.net/en/sorting)

---

### 4. **Searching Algorithms** 🔍
```
├── Linear Search
├── Binary Search
├── Ternary Search
├── Exponential Search
├── Interpolation Search
└── Jump Search
```

**Binary Search Example:**
```c
int binary_search(int arr[], int target, int n) {
    int left = 0, right = n - 1;
    
    while (left <= right) {
        int mid = left + (right - left) / 2;
        
        if (arr[mid] == target)
            return mid;
        else if (arr[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }
    
    return -1;  // Not found
}
```

**Complexity Comparison:**
- Linear Search: O(n) - Works on unsorted data
- Binary Search: O(log n) - Requires sorted data

---

### 5. **Divide & Conquer** ✂️
```
├── Merge Sort
├── Quick Sort
├── Binary Search
├── Strassen's Matrix Multiplication
└── Closest Pair of Points
```

**Key Concepts:**
- Break problem into subproblems
- Solve subproblems recursively
- Combine solutions

**Quick Sort Example:**
```c
int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = low - 1;
    
    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            i++;
            swap(&arr[i], &arr[j]);
        }
    }
    swap(&arr[i + 1], &arr[high]);
    return i + 1;
}

void quick_sort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quick_sort(arr, low, pi - 1);
        quick_sort(arr, pi + 1, high);
    }
}
```

---

### 6. **Greedy Algorithms** 🎯
```
├── Activity Selection
├── Huffman Coding
├── Fractional Knapsack
├── Job Sequencing
├── Dijkstra's Algorithm
└── Kruskal's Algorithm
```

**Key Concepts:**
- Local optimal choice at each step
- Hope to find global optimum
- Fast but not always optimal

**Activity Selection Example:**
```c
void activity_selection(int start[], int end[], int n) {
    // Sort by end time
    // Select activities greedily
    int selected = 0;
    selected = start[0];  // Always select first
    
    for (int i = 1; i < n; i++) {
        if (start[i] >= end[selected]) {
            selected = i;
            printf("Activity %d\n", i);
        }
    }
}
```

---

### 7. **Dynamic Programming** 💾
```
├── Fibonacci Sequence
├── 0/1 Knapsack
├── Longest Common Subsequence
├── Matrix Chain Multiplication
├── Coin Change Problem
├── Edit Distance
└── Longest Increasing Subsequence
```

**Key Concepts:**
- Overlapping subproblems
- Optimal substructure
- Memoization and Tabulation

**Fibonacci with DP:**
```c
int fib(int n, int dp[]) {
    if (n <= 1)
        return n;
    
    if (dp[n] != -1)
        return dp[n];  // Already computed
    
    dp[n] = fib(n - 1, dp) + fib(n - 2, dp);
    return dp[n];
}
```

**0/1 Knapsack Problem:**
```c
int knapsack(int capacity, int weights[], int values[], int n) {
    int dp[capacity + 1];
    memset(dp, 0, sizeof(dp));
    
    for (int i = 0; i < n; i++) {
        for (int w = capacity; w >= weights[i]; w--) {
            dp[w] = max(dp[w], dp[w - weights[i]] + values[i]);
        }
    }
    
    return dp[capacity];
}
```

---

### 8. **Graph Algorithms** 🕸️
```
├── Breadth-First Search (BFS)
├── Depth-First Search (DFS)
├── Dijkstra's Shortest Path
├── Bellman-Ford Algorithm
├── Kruskal's MST
├── Prim's MST
├── Topological Sort
└── Floyd-Warshall Algorithm
```

**Graph Representation:**
```c
// Adjacency List
struct Node {
    int data;
    struct Node* next;
};

// BFS Example
void bfs(int start, int adj[][V], int V) {
    int visited[V];
    memset(visited, 0, sizeof(visited));
    
    queue q;
    q.enqueue(start);
    visited[start] = 1;
    
    while (!q.isEmpty()) {
        int u = q.dequeue();
        printf("%d ", u);
        
        for (int v = 0; v < V; v++) {
            if (adj[u][v] && !visited[v]) {
                q.enqueue(v);
                visited[v] = 1;
            }
        }
    }
}
```

---

### 9. **NP-Completeness** 🎲
```
├── P vs NP
├── NP-Hard Problems
├── NP-Complete Problems
├── Traveling Salesman Problem
├── Subset Sum Problem
├── Graph Coloring
└── Approximation Algorithms
```

**Key Concepts:**
- Polynomial time
- NP problems
- NP-complete problems
- Approximation algorithms

---

## 💻 Practice Problems

### **Beginner Level** 🟢
- [ ] Implement bubble sort
- [ ] Implement linear search
- [ ] Analyze time complexity of loops
- [ ] Find GCD using Euclidean algorithm
- [ ] Count prime numbers up to N
- [ ] Fibonacci using recursion

### **Intermediate Level** 🟡
- [ ] Implement merge sort
- [ ] Implement binary search
- [ ] 0/1 Knapsack problem
- [ ] Longest Common Subsequence
- [ ] Implement BFS and DFS
- [ ] Dijkstra's shortest path

### **Advanced Level** 🔴
- [ ] Implement quick sort with worst-case analysis
- [ ] Graph coloring problem
- [ ] Traveling Salesman Problem
- [ ] Matrix chain multiplication
- [ ] Floyd-Warshall algorithm
- [ ] Topological sorting

---

## 📊 Progress Tracking

| Topic | Status | Difficulty | Date | Notes |
|---|---|---|---|---|
| Algorithm Basics | ⏳ Pending | Beginner | - | - |
| Complexity Analysis | ⏳ Pending | Intermediate | - | - |
| Sorting Algorithms | ⏳ Pending | Intermediate | - | - |
| Searching Algorithms | ⏳ Pending | Beginner | - | - |
| Divide & Conquer | ⏳ Pending | Advanced | - | - |
| Greedy Algorithms | ⏳ Pending | Advanced | - | - |
| Dynamic Programming | ⏳ Pending | Advanced | - | Most important |
| Graph Algorithms | ⏳ Pending | Advanced | - | Complex |
| NP-Completeness | ⏳ Pending | Advanced | - | Theory heavy |

---

## 📚 Recommended Resources

### **Online Platforms**
- [GeeksforGeeks - Algorithms](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)
- [Visualgo - Algorithm Visualizer](https://visualgo.net/)
- [Big O Cheat Sheet](https://www.bigocheatsheet.com/)
- [LeetCode - Algorithm Problems](https://leetcode.com/)

### **Books**
- "Introduction to Algorithms" (CLRS) - Classic textbook
- "Algorithm Design Manual" by Steven Skiena
- "Algorithms" by Robert Sedgewick

### **YouTube Channels**
- [Abdul Bari - Algorithms](https://www.youtube.com/c/AbdulBariOfficial)
- [Neso Academy - Data Structures & Algorithms](https://www.youtube.com/c/nesoacademy)
- [Jenny's Lectures - Algorithms](https://www.youtube.com/c/JennyslecturesCSIT)

---

## 🛠️ How to Use This Folder

1. **Start with Basics** - Understand fundamental concepts
2. **Learn Complexity** - Master Big O notation
3. **Study Algorithms** - Learn each algorithm in depth
4. **Implement** - Code algorithms from scratch
5. **Analyze** - Compare time/space complexity
6. **Practice** - Solve problems on LeetCode/HackerRank
7. **Optimize** - Improve your solutions
8. **Visualize** - Use algorithm visualizers

---

## 💡 Study Tips

✨ **Understand Before Memorizing** - Focus on "why", not "what"
✨ **Draw Diagrams** - Visualize algorithms
✨ **Implement Yourself** - Don't just read code
✨ **Trace Through** - Step through manually
✨ **Compare Approaches** - Learn multiple solutions
✨ **Analyze Complexity** - Always compute Big O
✨ **Practice Daily** - Consistency is key
✨ **Read Explanations** - Study others' solutions

---

## 📝 Algorithm Template

```c
/*
Algorithm Name: [Name]
Time Complexity: O(?) - [Explanation]
Space Complexity: O(?) - [Explanation]
Best Case: O(?)
Average Case: O(?)
Worst Case: O(?)

Approach:
1. [Step 1]
2. [Step 2]
3. [Step 3]
*/

#include <stdio.h>

void algorithm(int arr[], int n) {
    // Implementation
}

int main() {
    int arr[] = {/* test data */};
    int n = sizeof(arr) / sizeof(arr[0]);
    algorithm(arr, n);
    return 0;
}
```

---

## 🏆 Learning Milestones

- **Week 1** ✅ Algorithm Basics & Complexity
- **Week 2** ✅ Sorting Algorithms
- **Week 3** ✅ Searching Algorithms
- **Week 4-5** ✅ Divide & Conquer
- **Week 6** ✅ Greedy Algorithms
- **Week 7-9** ✅ Dynamic Programming
- **Week 10-11** ✅ Graph Algorithms
- **Week 12** ✅ NP-Completeness & Revision

---

## 📞 Need Help?

- 📧 Email: tripti.m2026@gmail.com
- 🔗 LinkedIn: https://www.linkedin.com/in/tripti-mishra-4a68881ba/
- 💻 GitHub: https://github.com/Tripti-crpto

---

**Remember: "An algorithm is like a recipe - you must follow the steps precisely!" 🚀**

---

*Last Updated: May 18, 2026*
