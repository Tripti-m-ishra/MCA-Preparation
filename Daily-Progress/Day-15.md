# Day 15 - MCA Preparation Progress

**Date:** June 1, 2026  
**Time Spent:** 8 hours  
**Mood:** 😊  
**Overall Progress:** 8.5/10

---

## ✅ What I Did Today:

### 1. Heap Data Structure & Heap Sort
**What I Learned:**
- Max heap and Min heap properties
- Heap implementation using arrays
- Heapify operations (top-down, bottom-up)
- Heap insertion and deletion
- Heap sort algorithm
- Priority queue implementation
- Applications of heaps (Dijkstra's, Prim's algorithm)
- Heap complexity analysis

**Resources Used:**
- [Heap Data Structure - GeeksforGeeks](https://www.geeksforgeeks.org/heap-data-structure/)
- [Priority Queues - TutorialsPoint](https://www.tutorialspoint.com/)
- MCS-211 Algorithm Design

**Code Practiced:**
```c
// Max Heap Heapify Operation
void heapify(int arr[], int n, int i) {
    int largest = i;
    int left = 2 * i + 1;
    int right = 2 * i + 2;
    
    if(left < n && arr[left] > arr[largest])
        largest = left;
    if(right < n && arr[right] > arr[largest])
        largest = right;
    
    if(largest != i) {
        int temp = arr[i];
        arr[i] = arr[largest];
        arr[largest] = temp;
        heapify(arr, n, largest);
    }
}

// Heap Sort Algorithm
void heapSort(int arr[], int n) {
    // Build max heap
    for(int i = n / 2 - 1; i >= 0; i--)
        heapify(arr, n, i);
    
    // Extract elements one by one
    for(int i = n - 1; i > 0; i--) {
        int temp = arr[0];
        arr[0] = arr[i];
        arr[i] = temp;
        heapify(arr, i, 0);
    }
}

// Priority Queue using Min Heap - Insert
void insertMin(int heap[], int *size, int value) {
    heap[*size] = value;
    int i = *size;
    (*size)++;
    
    while(i > 0 && heap[(i - 1) / 2] > heap[i]) {
        int temp = heap[i];
        heap[i] = heap[(i - 1) / 2];
        heap[(i - 1) / 2] = temp;
        i = (i - 1) / 2;
    }
}

// Priority Queue - Extract Min
int extractMin(int heap[], int *size) {
    if(*size == 0) return -1;
    
    int min = heap[0];
    heap[0] = heap[*size - 1];
    (*size)--;
    heapify(heap, *size, 0);
    return min;
}
```

---

### 2. Cryptography & Security Basics
**What I Learned:**
- Encryption and decryption concepts
- Symmetric vs Asymmetric encryption
- Caesar cipher and substitution ciphers
- RSA algorithm basics
- Digital signatures
- Hash functions (MD5, SHA)
- SSL/TLS concepts
- Security best practices

**Resources Used:**
- [Cryptography - GeeksforGeeks](https://www.geeksforgeeks.org/cryptography-and-network-security/)
- [Security Basics - OWASP](https://owasp.org/)
- MCS-217 Cryptography course

**Key Concepts:**
```
Symmetric Encryption:
- Same key for encryption and decryption
- Examples: AES, DES
- Fast but key distribution problem
- Time Complexity: O(n) for n-bit message

Asymmetric Encryption:
- Public and Private keys
- Examples: RSA, ECC
- Slower but solves key distribution
- Security depends on factorization difficulty

Hash Functions:
- One-way function (cannot be reversed)
- Same input → Same output (deterministic)
- Even small change → Different output (avalanche effect)
- Examples: MD5, SHA-1, SHA-256
- Applications: password storage, data integrity

RSA Steps:
1. Choose two large primes: p, q
2. Calculate n = p * q
3. Calculate φ(n) = (p-1) * (q-1)
4. Choose e where 1 < e < φ(n) and gcd(e, φ(n)) = 1
5. Calculate d where (d * e) mod φ(n) = 1
6. Public Key: (e, n), Private Key: (d, n)
```

---

### 3. Competitive Programming - Heap & Hash Problems
**What I Did:**
- Solved 12+ problems
- LeetCode problems (8 Medium, 4 Hard)
- Mix of heap and hash table problems

**Problems Solved:**
1. Kth Largest Element in Array (Easy)
2. Top K Frequent Elements (Medium)
3. Merge k Sorted Lists (Hard)
4. Find Median in Data Stream (Hard)
5. Reorganize String (Medium)
6. Task Scheduler (Medium)
7. Sliding Window Maximum (Hard)
8. Rearrange String K Distance Apart (Hard)
9. Largest Rectangle in Histogram (Hard)
10. Trapping Rain Water (Hard)
11. Two Sum (Easy)
12. Valid Anagram (Easy)

---

## 🔍 Challenges Faced:

| Challenge | Reason | Solution |
|---|---|---|
| **Heapify Logic** | Comparing parent and children indices confusing | Drew heap trees, traced through operations step-by-step |
| **Heap Sort Visualization** | Hard to visualize the sorting process | Used array diagrams, traced multiple examples |
| **RSA Algorithm** | Mathematical concepts complex | Studied step-by-step with numerical examples |
| **Sliding Window with Heap** | Combining two concepts difficult | Practiced multiple problems incrementally |
| **Hash Collisions** | Understanding collision handling | Studied chaining and open addressing |

---

## 📊 Daily Metrics:

| Metric | Value |
|---|---|
| Topics Covered | 3 |
| Programs Written | 8 |
| Problems Solved | 12 |
| Time Spent | 8 hours |
| Motivation Level | ⭐⭐⭐⭐⭐ |

---

## 📝 Key Takeaways:

1. Heaps are efficient for priority-based operations - O(log n)
2. Heap sort has O(n log n) time complexity with O(1) space
3. Cryptography is essential for modern data security
4. Hash functions are one-way by design for security
5. RSA encryption uses mathematical principles (prime factorization)
6. Priority queues have numerous real-world applications
7. Understanding hash collisions improves data structure design

---

**Next Session:** Day 16  
**Estimated Duration:** 8 hours

---

*"Heaps organize data efficiently. Cryptography protects it. Master both! 🔐🚀"*
