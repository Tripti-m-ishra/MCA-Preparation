# Day 5 - MCA Preparation Progress

**Date:** May 22, 2026 
**Time Spent:** 6.5 hours  
**Mood:** 😊  
**Overall Progress:** 8/10

---

## ✅ What I Did Today:

### 1. Queue Data Structure - Full Implementation
**What I Learned:**
- Queue concept (FIFO - First In First Out)
- Enqueue and Dequeue operations
- Circular queue and its advantages
- Queue implementation using array and linked list
- Applications: BFS, scheduling, buffering
- Priority queue basics

**Resources Used:**
- [Queue Data Structure - GeeksforGeeks](https://www.geeksforgeeks.org/queue-data-structure/)
- [Circular Queue - TutorialsPoint](https://www.tutorialspoint.com/data_structures_algorithms/circular_queue.htm)

**Code Practiced:**
```c
// Linear Queue Implementation
struct Queue {
    int arr[MAX];
    int front, rear;
};

void initQueue(struct Queue *q) {
    q->front = -1;
    q->rear = -1;
}

void enqueue(struct Queue *q, int value) {
    if(q->rear == MAX - 1) {
        printf("Queue Full!\n");
        return;
    }
    if(q->front == -1) q->front = 0;
    q->arr[++q->rear] = value;
}

int dequeue(struct Queue *q) {
    if(q->front == -1 || q->front > q->rear) {
        printf("Queue Empty!\n");
        return -1;
    }
    return q->arr[q->front++];
}

// Circular Queue Implementation
struct CircularQueue {
    int arr[MAX];
    int front, rear;
};

void enqueueCircular(struct CircularQueue *q, int value) {
    if((q->rear + 1) % MAX == q->front) {
        printf("Queue Full!\n");
        return;
    }
    if(q->front == -1) q->front = 0;
    q->rear = (q->rear + 1) % MAX;
    q->arr[q->rear] = value;
}
```

---

### 2. Sorting Algorithms - Part 1
**What I Learned:**
- Bubble Sort (Time: O(n²), Space: O(1))
- Selection Sort (Time: O(n²), Space: O(1))
- Insertion Sort (Time: O(n²), Space: O(1))
- Algorithm analysis and Big-O notation
- Comparing sorting algorithms
- Stability in sorting

**Resources Used:**
- [Sorting Algorithms - GeeksforGeeks](https://www.geeksforgeeks.org/sorting-algorithms/)
- [Sorting Visualizer](https://www.sortvisualizer.com/)
- MCS-211 course materials

**Code Practiced:**
```c
// Bubble Sort
void bubbleSort(int arr[], int n) {
    for(int i = 0; i < n - 1; i++) {
        for(int j = 0; j < n - i - 1; j++) {
            if(arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

// Selection Sort
void selectionSort(int arr[], int n) {
    for(int i = 0; i < n - 1; i++) {
        int minIdx = i;
        for(int j = i + 1; j < n; j++) {
            if(arr[j] < arr[minIdx])
                minIdx = j;
        }
        int temp = arr[i];
        arr[i] = arr[minIdx];
        arr[minIdx] = temp;
    }
}

// Insertion Sort
void insertionSort(int arr[], int n) {
    for(int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while(j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
```

---

## 🔍 Challenges Faced:

| Challenge | Reason | Solution |
|---|---|---|
| **Circular queue logic** | Hard to manage modulo arithmetic for wrapping | Drew the queue visually and practiced with examples |
| **Big-O notation** | Couldn't count operations correctly | Learned to identify loops and their nesting levels |
| **Sorting stability** | Didn't understand what stable sorting means | Learned that stable sorts preserve relative order of equal elements |

---

## 🎯 Tomorrow's Goals:

- [ ] Study Merge Sort and Quick Sort
- [ ] Implement Merge Sort and Quick Sort
- [ ] Understand Heap Sort
- [ ] Practice 10 sorting algorithm problems
- [ ] Compare all sorting algorithms
- [ ] Study binary search

---

## 📊 Progress Metrics:

| Metric | Today | Total |
|---|---|---|
| Topics Covered | 2 | 9 |
| Programs Written | 5 | 22 |
| Problems Solved | 6 | 19 |
| Time Spent | 6.5 hours | 31.5 hours |
| Motivation Level | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

---

## 📝 Key Takeaways:

1. Queue is essentially a reversed stack - conceptually easy once you understand stack
2. Big-O notation is crucial for analyzing algorithm efficiency
3. Sorting algorithms form the foundation for advanced algorithms
4. Visualization tools help in understanding data structure operations

---

## 📌 Notes & Reflections:

**What Went Well:**
- Implemented both linear and circular queue successfully
- Sorting algorithm implementation was straightforward
- Progressing well with coding confidence

**What Needs Improvement:**
- Need to practice more complex sorting problems
- Should analyze time and space complexity for all algorithms
- Need to understand when to use which sorting algorithm

---

**Next Session:** Day 6  
**Estimated Duration:** 7 hours

---

*"Your learning journey is unique. Celebrate small wins!" 🚀*
