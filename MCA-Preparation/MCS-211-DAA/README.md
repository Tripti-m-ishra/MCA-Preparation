# 💻 Design & Analysis of Algorithms - MCS-211
Master of Computer Applications (MCA) - Core Algorithm Course

This folder contains comprehensive algorithm study materials, code examples, problem solutions, and learning resources for MCS-211.

---

## 📚 Course Overview
Design & Analysis of Algorithms is crucial for writing efficient software. This course covers:

✓ Algorithm design paradigms
✓ Complexity analysis (Big-O notation)
✓ Sorting and searching algorithms
✓ Graph algorithms
✓ Dynamic programming
✓ Greedy algorithms
✓ Problem-solving strategies

---

## 🎯 Learning Objectives
By the end of this course, you will:

✅ Analyze algorithm time and space complexity
✅ Design efficient algorithms
✅ Master classic sorting and searching
✅ Implement graph algorithms
✅ Solve problems using dynamic programming
✅ Choose appropriate algorithms for problems
✅ Optimize code performance
✅ Solve competitive programming problems

---

## 📖 Topics Covered

### 1. Algorithm Fundamentals 🔧
```
├── What is an Algorithm?
├── Algorithm Properties
├── Pseudocode Writing
├── Algorithm Analysis
├── Time Complexity Basics
├── Space Complexity
├── Big-O Notation
├── Big-Theta (Θ) Notation
├── Big-Omega (Ω) Notation
└── Asymptotic Analysis
```

**Key Concepts:**
- Time complexity measures how execution time grows with input size
- Space complexity measures memory usage
- Big-O represents worst-case scenario
- Common complexities: O(1), O(log n), O(n), O(n log n), O(n²), O(2ⁿ)

**Example - Linear Search Analysis:**
```c
int linearSearch(int arr[], int n, int x) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == x)
            return i;
    }
    return -1;
}
// Time: O(n), Space: O(1)
```

**Resources:**
- [Big-O Complexity Cheat Sheet](https://www.bigocheatsheet.com/)
- [Asymptotic Analysis - GeeksforGeeks](https://www.geeksforgeeks.org/asymptotic-analysis/)

---

### 2. Sorting Algorithms 📊
```
├── Bubble Sort (O(n²))
├── Selection Sort (O(n²))
├── Insertion Sort (O(n²))
├── Merge Sort (O(n log n))
├── Quick Sort (O(n log n) avg)
├── Heap Sort (O(n log n))
├── Counting Sort (O(n+k))
├── Radix Sort (O(nk))
├── Bucket Sort (O(n+k))
└── Sorting Comparisons
```

**Key Concepts:**
- Simple sorts: Bubble, Selection, Insertion (O(n²))
- Efficient sorts: Merge, Quick, Heap (O(n log n))
- Stable sorts preserve relative order of equal elements
- Non-comparison sorts: Counting, Radix, Bucket

**Sorting Algorithm Comparison Table:**

| Algorithm | Best | Average | Worst | Space | Stable |
|-----------|------|---------|-------|-------|--------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) | No |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| **Merge Sort** | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes |
| **Quick Sort** | O(n log n) | O(n log n) | O(n²) | O(log n) | No |
| **Heap Sort** | O(n log n) | O(n log n) | O(n log n) | O(1) | No |

**Merge Sort Implementation:**
```c
void merge(int arr[], int left, int mid, int right) {
    int i = left, j = mid + 1, k = 0;
    int temp[right - left + 1];
    
    while (i <= mid && j <= right) {
        if (arr[i] <= arr[j])
            temp[k++] = arr[i++];
        else
            temp[k++] = arr[j++];
    }
    
    while (i <= mid) temp[k++] = arr[i++];
    while (j <= right) temp[k++] = arr[j++];
    
    for (int i = left, k = 0; i <= right; i++, k++)
        arr[i] = temp[k];
}

void mergeSort(int arr[], int left, int right) {
    if (left < right) {
        int mid = left + (right - left) / 2;
        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);
        merge(arr, left, mid, right);
    }
}
// Time: O(n log n), Space: O(n), Stable: Yes
```

**Resources:**
- [Sorting Algorithms - GeeksforGeeks](https://www.geeksforgeeks.org/sorting-algorithms/)
- [Sorting Visualizer](https://www.sortvisualizer.com/)

---

### 3. Searching Algorithms 🔍
```
├── Linear Search (O(n))
├── Binary Search (O(log n))
├── Jump Search (O(√n))
├── Interpolation Search
├── Exponential Search
└── Fibonacci Search
```

**Key Concepts:**
- Linear search works on unsorted arrays
- Binary search requires sorted array
- Binary search is much faster for large datasets

**Binary Search Implementation:**
```c
int binarySearch(int arr[], int n, int target) {
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
// Time: O(log n), Space: O(1)
```

---

### 4. Graph Algorithms 🌐
```
├── Graph Representations
│   ├── Adjacency Matrix
│   ├── Adjacency List
│   └── Edge List
├── Graph Traversal
│   ├── Depth First Search (DFS)
│   └── Breadth First Search (BFS)
├── Shortest Path Algorithms
│   ├── Dijkstra's Algorithm
│   ├── Bellman-Ford Algorithm
│   └── Floyd-Warshall Algorithm
├── Minimum Spanning Tree
│   ├── Kruskal's Algorithm
│   └── Prim's Algorithm
└── Advanced Concepts
    ├── Topological Sorting
    ├── Strongly Connected Components
    └── Bipartite Checking
```

**Key Concepts:**
- DFS: Uses stack (recursion), explores deeply
- BFS: Uses queue, explores level by level
- Dijkstra: Single source shortest path (non-negative weights)
- Bellman-Ford: Handles negative weights, detects negative cycles
- Kruskal: MST using sorting and Union-Find
- Prim: MST using priority queue

**DFS Implementation:**
```c
void DFS(int graph[V][V], int vertex, bool visited[]) {
    visited[vertex] = true;
    printf("%d ", vertex);
    
    for (int i = 0; i < V; i++) {
        if (graph[vertex][i] && !visited[i]) {
            DFS(graph, i, visited);
        }
    }
}
// Time: O(V + E), Space: O(V)
```

**BFS Implementation:**
```c
void BFS(int graph[V][V], int startVertex) {
    bool visited[V] = {false};
    int queue[V], front = 0, rear = 0;
    
    visited[startVertex] = true;
    queue[rear++] = startVertex;
    
    while (front < rear) {
        int vertex = queue[front++];
        printf("%d ", vertex);
        
        for (int i = 0; i < V; i++) {
            if (graph[vertex][i] && !visited[i]) {
                visited[i] = true;
                queue[rear++] = i;
            }
        }
    }
}
// Time: O(V + E), Space: O(V)
```

**Resources:**
- [Graph Algorithms - GeeksforGeeks](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)
- [Graph Visualization Tools](https://www.cs.usfca.edu/~galles/visualization/)

---

### 5. Dynamic Programming 💡
```
├── DP Fundamentals
│   ├── Overlapping Subproblems
│   ├── Optimal Substructure
│   └── Memoization vs Tabulation
├── Classic DP Problems
│   ├── Fibonacci Sequence
│   ├── 0/1 Knapsack Problem
│   ├── Longest Common Subsequence (LCS)
│   ├── Coin Change Problem
│   ├── Edit Distance
│   ├── Matrix Chain Multiplication
│   └── Longest Increasing Subsequence (LIS)
└── Advanced DP
    ├── Digit DP
    ├── Tree DP
    └── Game Theory DP
```

**Key Concepts:**
- Overlapping Subproblems: Same subproblems solved multiple times
- Optimal Substructure: Optimal solution built from optimal subproblems
- Memoization: Top-down, store results in lookup table
- Tabulation: Bottom-up, build solution iteratively

**0/1 Knapsack - DP Solution:**
```c
int knapsack(int weights[], int values[], int n, int capacity) {
    int dp[n+1][capacity+1];
    
    // Base case: if capacity is 0
    for (int i = 0; i <= n; i++)
        dp[i][0] = 0;
    
    // Fill DP table
    for (int i = 1; i <= n; i++) {
        for (int w = 1; w <= capacity; w++) {
            if (weights[i-1] <= w) {
                // Include item or exclude
                dp[i][w] = max(
                    values[i-1] + dp[i-1][w - weights[i-1]],
                    dp[i-1][w]
                );
            } else {
                // Can't include
                dp[i][w] = dp[i-1][w];
            }
        }
    }
    
    return dp[n][capacity];
}
// Time: O(n*W), Space: O(n*W)
```

**Longest Common Subsequence (LCS):**
```c
int lcs(char *text1, char *text2) {
    int m = strlen(text1);
    int n = strlen(text2);
    int dp[m+1][n+1];
    memset(dp, 0, sizeof(dp));
    
    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            if (text1[i-1] == text2[j-1]) {
                dp[i][j] = dp[i-1][j-1] + 1;
            } else {
                dp[i][j] = max(dp[i-1][j], dp[i][j-1]);
            }
        }
    }
    
    return dp[m][n];
}
// Time: O(m*n), Space: O(m*n)
```

**Resources:**
- [Dynamic Programming Guide](https://www.freecodecamp.org/news/dynamic-programming-explained/)
- [DP Problem List](https://www.geeksforgeeks.org/dynamic-programming/)

---

### 6. Greedy Algorithms 🎯
```
├── Greedy Strategy
├── Activity Selection Problem
├── Huffman Coding
├── Fractional Knapsack
├── Job Sequencing
├── Minimum Spanning Tree (Kruskal)
└── Dijkstra's Algorithm (Greedy approach)
```

**Key Concepts:**
- Make locally optimal choice at each step
- Hope for globally optimal solution
- Not always guaranteed to work
- Works for specific problem classes

**Activity Selection Problem:**
```c
void activitySelection(int start[], int end[], int n) {
    // Create array of activities
    int i = 0;
    printf("Activity 1\n");
    
    for (int j = 1; j < n; j++) {
        if (start[j] >= end[i]) {
            printf("Activity %d\n", j+1);
            i = j;
        }
    }
}
// Time: O(n log n), Space: O(1)
```

---

## 💻 Practice Problems

### Beginner Level 🟢
- Linear Search implementation
- Bubble Sort and Selection Sort
- Simple array operations
- Basic recursion problems
- Palindrome checking
- Factorial and Fibonacci

### Intermediate Level 🟡
- Binary Search variations
- Merge Sort and Quick Sort
- Array searching and sorting problems
- Graph DFS and BFS
- Basic Dynamic Programming (Fibonacci, LCS)
- Linked List operations

### Advanced Level 🔴
- Complex DP problems (Knapsack, Edit Distance)
- Dijkstra's and Bellman-Ford algorithms
- Minimum Spanning Trees
- Complex graph problems
- Greedy algorithm problems
- Optimization problems

---

## 📊 Progress Tracking

| Topic | Status | Level | Completion | Notes |
|-------|--------|-------|------------|-------|
| Algorithm Fundamentals | ✅ Completed | Beginner | 100% | Big-O analysis mastered |
| Sorting Algorithms | ✅ Completed | Intermediate | 100% | All major sorts covered |
| Searching Algorithms | ⏳ In Progress | Intermediate | 50% | Binary search done |
| Graph Algorithms | ✅ Completed | Advanced | 100% | DFS, BFS, Dijkstra done |
| Dynamic Programming | ✅ Completed | Advanced | 100% | DP fundamentals strong |
| Greedy Algorithms | ⏳ In Progress | Advanced | 40% | MST covered |

**Overall Progress: 75/100** 📈

---

## 📚 Recommended Resources

### Online Tutorials
- [GeeksforGeeks - Algorithms](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)
- [Abdul Bari Algorithm YouTube](https://www.youtube.com/watch?v=0IAPZzGSbME)
- [MIT OpenCourseWare - Algorithms](https://ocw.mit.edu/courses/6-046j-design-of-computer-algorithms-spring-2012/)
- [Tushar Roy - Coding Made Simple](https://www.youtube.com/user/tusharroy2525)

### Books
- "Introduction to Algorithms" (CLRS) - Most comprehensive
- "Algorithm Design Manual" by Steven Skiena
- "Algorithms Illuminated" by Tim Roughgarden
- "Cracking the Coding Interview" by Gayle Laakmann

### Practice Platforms
- [LeetCode](https://www.leetcode.com/) - 65+ problems solved ⭐
- [HackerRank](https://www.hackerrank.com/)
- [CodeChef](https://www.codechef.com/)
- [Codeforces](https://codeforces.com/)
- [InterviewBit](https://www.interviewbit.com/)

### Visualization Tools
- [Algorithm Visualizer](https://algorithm-visualizer.org/)
- [VisuAlgo](https://visualgo.net/) - Best visualization tool
- [Sorting Algorithms Visualization](https://www.sortvisualizer.com/)

---

## 🛠️ How to Use This Folder

1. **Study Topics** - Read theory and understand concepts
2. **Analyze Examples** - Study provided code examples
3. **Implement** - Write your own implementations
4. **Practice Problems** - Solve increasing difficulty levels
5. **Debug & Test** - Trace through code and test cases
6. **Optimize** - Improve time and space complexity
7. **Document** - Add comments and explanations
8. **Revise** - Regular revision of concepts

---

## 💡 Study Tips

✨ **Daily Practice** - Code every day (2-3 hours minimum)
✨ **Understand Logic First** - Before coding, understand algorithm logic
✨ **Trace by Hand** - Manually trace through examples
✨ **Visualize** - Use visualization tools to understand concepts
✨ **Code Multiple Times** - Implement algorithms multiple times
✨ **Analyze Complexity** - Always analyze time and space complexity
✨ **Read Others' Code** - Learn different approaches
✨ **Participate in Contests** - Try competitive programming

---

## 🎯 Common Mistakes to Avoid

❌ Memorizing without understanding
❌ Not analyzing time complexity
❌ Ignoring edge cases
❌ Not testing with multiple test cases
❌ Choosing wrong algorithm for problem
❌ Not optimizing code
❌ Ignoring space complexity
❌ Not handling base cases in recursion

---

## 📝 Quick Algorithm Reference

### Time Complexity Ranking
```
O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(n³) < O(2ⁿ) < O(n!)
Constant  Log    Linear  N-Log-N   Quadratic Cubic  Exponential Factorial
```

### When to Use Which Algorithm

| Problem Type | Best Algorithm | Why |
|--------------|----------------|-----|
| Find max/min | Linear Scan | Simple, O(n) |
| Sorted array search | Binary Search | O(log n) |
| Unsorted array sort | Quick/Merge Sort | O(n log n) avg |
| Shortest path | Dijkstra | Non-negative weights |
| Shortest path (negative) | Bellman-Ford | Handles negatives |
| MST | Kruskal/Prim | O(E log E) / O(E log V) |
| Graph traversal | DFS/BFS | Explore all nodes |
| Optimization | Dynamic Programming | Overlapping subproblems |
| Selection problem | Greedy | Locally optimal |

---

## 🏆 Learning Milestones

- **Week 1-2** ✅ Complexity Analysis & Basic Sorting
- **Week 3-4** ✅ Advanced Sorting & Searching
- **Week 5-6** ✅ Graph Algorithms (DFS, BFS)
- **Week 7-8** ✅ Shortest Path & MST
- **Week 9-10** ✅ Dynamic Programming
- **Week 11-12** ✅ Greedy Algorithms & Practice
- **Week 13-14** ✅ Revision & Mock Interviews

---

## 📞 Need Help?

📧 **Email:** tripti.m2026@gmail.com
🔗 **LinkedIn:** https://www.linkedin.com/in/tripti-mishra-4a68881ba/
💻 **GitHub:** https://github.com/Tripti-m-ishra

---

## 🎊 Success Markers

✅ Can analyze any algorithm's complexity
✅ Can choose right algorithm for problem
✅ Can implement all classic algorithms
✅ Can solve LeetCode hard problems
✅ Can optimize code for interviews
✅ Can explain algorithm choices
✅ Can handle competitive programming

---

*Master algorithms, master coding interviews!* 🚀

**Last Updated:** June 5, 2026
**Next Review:** June 12, 2026
**Performance Grade:** A (Excellent)