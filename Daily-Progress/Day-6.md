# Day 6 - MCA Preparation Progress

**Date:** May 23, 2026 
**Time Spent:** 7.5 hours  
**Mood:** 😊  
**Overall Progress:** 8.5/10

---

## ✅ What I Did Today:

### 1. Advanced Sorting - Merge Sort and Quick Sort
**What I Learned:**
- Merge Sort (Divide and Conquer approach)
- Time Complexity: O(n log n) in all cases
- Space Complexity: O(n)
- Quick Sort and its pivot selection
- Quick Sort worst case and average case analysis
- Randomized Quick Sort
- In-place sorting vs. stable sorting

**Resources Used:**
- [Merge Sort and Quick Sort - GeeksforGeeks](https://www.geeksforgeeks.org/)
- Abdul Bari YouTube channel (Merge Sort and Quick Sort)
- MCS-211 Algorithm Design Analysis course

**Code Practiced:**
```c
// Merge Sort
void merge(int arr[], int left, int mid, int right) {
    int i = left, j = mid + 1, k = 0;
    int temp[right - left + 1];
    
    while(i <= mid && j <= right) {
        if(arr[i] <= arr[j]) {
            temp[k++] = arr[i++];
        } else {
            temp[k++] = arr[j++];
        }
    }
    
    while(i <= mid) temp[k++] = arr[i++];
    while(j <= right) temp[k++] = arr[j++];
    
    for(int i = left, k = 0; i <= right; i++, k++) {
        arr[i] = temp[k];
    }
}

void mergeSort(int arr[], int left, int right) {
    if(left < right) {
        int mid = left + (right - left) / 2;
        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);
        merge(arr, left, mid, right);
    }
}

// Quick Sort
int partition(int arr[], int low, int high) {
    int pivot = arr[high];
    int i = low - 1;
    
    for(int j = low; j < high; j++) {
        if(arr[j] < pivot) {
            i++;
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
        }
    }
    
    int temp = arr[i + 1];
    arr[i + 1] = arr[high];
    arr[high] = temp;
    
    return i + 1;
}

void quickSort(int arr[], int low, int high) {
    if(low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}
```

---

### 2. Tree Data Structure - Basics and Binary Trees
**What I Learned:**
- Tree terminologies (root, leaf, parent, child, height, depth)
- Binary Tree concept and properties
- Different types of binary trees (full, complete, perfect, balanced)
- Tree traversal methods:
  - Inorder (Left, Root, Right)
  - Preorder (Root, Left, Right)
  - Postorder (Left, Right, Root)
  - Level order (BFS)
- Binary Search Tree (BST) basics

**Resources Used:**
- [Tree Data Structure - GeeksforGeeks](https://www.geeksforgeeks.org/binary-tree-data-structure/)
- [Tree Traversal - TutorialsPoint](https://www.tutorialspoint.com/data_structures_algorithms/tree_traversal.htm)

**Code Practiced:**
```c
struct TreeNode {
    int data;
    struct TreeNode *left;
    struct TreeNode *right;
};

// Inorder Traversal (Left, Root, Right)
void inorder(struct TreeNode *root) {
    if(root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

// Preorder Traversal (Root, Left, Right)
void preorder(struct TreeNode *root) {
    if(root != NULL) {
        printf("%d ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}

// Postorder Traversal (Left, Right, Root)
void postorder(struct TreeNode *root) {
    if(root != NULL) {
        postorder(root->left);
        postorder(root->right);
        printf("%d ", root->data);
    }
}

// Level Order Traversal (BFS)
void levelOrder(struct TreeNode *root) {
    if(root == NULL) return;
    
    struct Queue q;
    initQueue(&q);
    enqueue(&q, (int)root);
    
    while(q.front != -1 && q.front <= q.rear) {
        struct TreeNode *node = (struct TreeNode*)dequeue(&q);
        printf("%d ", node->data);
        
        if(node->left != NULL) enqueue(&q, (int)node->left);
        if(node->right != NULL) enqueue(&q, (int)node->right);
    }
}
```

---

## 🔍 Challenges Faced:

| Challenge | Reason | Solution |
|---|---|---|
| **Merge Sort merging logic** | Merging two sorted arrays was confusing | Traced through manually with example arrays |
| **Quick Sort partitioning** | Pivot selection and partitioning logic | Drew diagrams and understood Lomuto partition scheme |
| **Tree traversal understanding** | Hard to remember all traversal orders | Created mnemonics and practiced with visual trees |

---

## 🎯 Tomorrow's Goals:

- [ ] Binary Search Tree implementation (insert, search, delete)
- [ ] AVL Trees and balancing
- [ ] Study Heap data structure
- [ ] Practice 12+ tree problems
- [ ] Study Graph basics
- [ ] Begin graph traversal (DFS, BFS)

---

## 📊 Progress Metrics:

| Metric | Today | Total |
|---|---|---|
| Topics Covered | 2 | 11 |
| Programs Written | 8 | 30 |
| Problems Solved | 8 | 27 |
| Time Spent | 7.5 hours | 39 hours |
| Motivation Level | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

---

## 📝 Key Takeaways:

1. Merge Sort is stable and O(n log n) but uses extra space
2. Quick Sort is O(n log n) average but O(n²) worst case
3. Tree traversal is about understanding recursion depth
4. Different traversals are used for different problems
5. Data structures and algorithms are interconnected

---

## 📌 Notes & Reflections:

**What Went Well:**
- Successfully implemented and understood Merge Sort
- Quick Sort partition logic finally clicked
- Tree traversal implementations were smooth
- Completed more complex coding problems

**What Needs Improvement:**
- Should practice more sorting problems with variations
- Need to implement more tree problems
- Should understand BST operations deeply

---

**Next Session:** Day 7 (Week 1 Review)  
**Estimated Duration:** 7.5 hours

---

*"Your learning journey is unique. Celebrate small wins!" 🚀*
