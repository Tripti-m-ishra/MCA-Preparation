# Day 12 - MCA Preparation Progress

**Date:** May 29, 2026  
**Time Spent:** 8 hours  
**Mood:** 😊  
**Overall Progress:** 8.5/10

---

## ✅ What I Did Today:

### 1. Tree Data Structures - Binary Trees & BST
**What I Learned:**
- Binary tree basics (properties, types)
- Binary Search Trees (BST) and operations
- Tree traversals:
  - Inorder (Left-Root-Right)
  - Preorder (Root-Left-Right)
  - Postorder (Left-Right-Root)
  - Level Order (BFS)
- BST insertion, deletion, and search
- Balanced trees and AVL basics
- Tree height and depth concepts

**Resources Used:**
- [Binary Trees - GeeksforGeeks](https://www.geeksforgeeks.org/binary-tree-data-structure/)
- [BST Operations - TutorialsPoint](https://www.tutorialspoint.com/data_structures_algorithms/binary_search_tree.htm)
- Abdul Bari Tree YouTube series
- MCS-211 course materials

**Code Practiced:**
```c
// Binary Tree Node Structure
typedef struct Node {
    int data;
    struct Node* left;
    struct Node* right;
} Node;

// BST Search
Node* search(Node* root, int key) {
    if(root == NULL || root->data == key)
        return root;
    
    if(key < root->data)
        return search(root->left, key);
    
    return search(root->right, key);
}

// BST Insertion
Node* insert(Node* root, int data) {
    if(root == NULL) {
        Node* newNode = (Node*)malloc(sizeof(Node));
        newNode->data = data;
        newNode->left = newNode->right = NULL;
        return newNode;
    }
    
    if(data < root->data)
        root->left = insert(root->left, data);
    else if(data > root->data)
        root->right = insert(root->right, data);
    
    return root;
}

// Inorder Traversal
void inorder(Node* root) {
    if(root == NULL) return;
    inorder(root->left);
    printf("%d ", root->data);
    inorder(root->right);
}

// Level Order Traversal using Queue
void levelOrder(Node* root) {
    if(root == NULL) return;
    
    Queue* queue = createQueue();
    enqueue(queue, root);
    
    while(!isQueueEmpty(queue)) {
        Node* temp = dequeue(queue);
        printf("%d ", temp->data);
        
        if(temp->left != NULL)
            enqueue(queue, temp->left);
        if(temp->right != NULL)
            enqueue(queue, temp->right);
    }
}
```

---

### 2. Advanced SQL & Database Operations
**What I Learned:**
- Advanced SQL queries (JOINs, subqueries)
- View creation and usage
- Stored procedures and triggers
- Transaction handling and ACID properties
- Database indexing and query optimization
- Query execution plans

**Resources Used:**
- [Advanced SQL - W3Schools](https://www.w3schools.com/sql/)
- [Database Indexing - GeeksforGeeks](https://www.geeksforgeeks.org/indexing-in-databases-set-1/)
- MCS-202 Database Management Systems

**SQL Queries Practiced:**
```sql
-- Complex JOIN with subquery
SELECT e.name, d.department_name, 
       (SELECT COUNT(*) FROM employees WHERE dept_id = d.id) as emp_count
FROM employees e
INNER JOIN departments d ON e.dept_id = d.id
WHERE e.salary > (SELECT AVG(salary) FROM employees);

-- View Creation
CREATE VIEW high_earners AS
SELECT name, salary, department_id
FROM employees
WHERE salary > 75000;

-- Stored Procedure
DELIMITER //
CREATE PROCEDURE GetEmployeesByDept(IN dept_id INT)
BEGIN
    SELECT * FROM employees WHERE department_id = dept_id;
END //
DELIMITER ;

-- Transaction with ACID properties
START TRANSACTION;
UPDATE employees SET salary = salary * 1.10 WHERE department_id = 5;
UPDATE departments SET budget = budget - 50000 WHERE id = 5;
COMMIT;
```

---

### 3. Competitive Programming - Tree Problems
**What I Did:**
- Solved 12+ tree-related problems
- LeetCode Medium level problems (7 problems)
- HackerRank tree algorithms (5 problems)

**Problems Solved:**
1. Maximum Depth of Binary Tree (Easy)
2. Invert Binary Tree (Easy)
3. Balanced Binary Tree (Easy)
4. Binary Tree Level Order Traversal (Medium)
5. Lowest Common Ancestor (Medium)
6. Binary Search Tree Iterator (Medium)
7. Validate Binary Search Tree (Medium)
8. Serialize and Deserialize BST (Hard)
9. Binary Tree Right Side View (Medium)
10. Path Sum III (Medium)
11. Kth Smallest Element in BST (Medium)
12. Binary Tree Maximum Path Sum (Hard)

---

## 🔍 Challenges Faced:

| Challenge | Reason | Solution |
|---|---|---|
| **Tree Traversals** | Multiple traversal methods confusing | Practiced all 4 traversals multiple times with visual diagrams |
| **BST Deletion** | Deleting node with two children was tricky | Studied step-by-step deletion process, implemented carefully |
| **Query Optimization** | Understanding execution plans was complex | Analyzed EXPLAIN plans with multiple queries |
| **Recursive vs Iterative** | Both approaches seemed similar | Practiced both, understanding trade-offs |

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

1. Tree traversals are fundamental for many algorithms
2. Understanding BST properties helps with problem-solving
3. Database optimization requires understanding internal structures
4. Competitive programming builds pattern recognition skills
5. Recursion is powerful for tree problems

---

**Next Session:** Day 13  
**Estimated Duration:** 8 hours

---
