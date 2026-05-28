# Day 9 - MCA Preparation Progress

**Date:** May 26, 2026  
**Time Spent:** 7.5 hours  
**Mood:** 😊  
**Overall Progress:** 8.5/10

---

## ✅ What I Did Today:

### 1. Shortest Path Algorithms
**What I Learned:**
- Dijkstra's Algorithm
  - Greedy approach
  - Works with non-negative weights
  - Time Complexity: O((V+E)logV) with min heap
  - Applications: GPS, network routing
- Bellman-Ford Algorithm
  - Handles negative weights
  - Time Complexity: O(V*E)
  - Can detect negative cycles
- Floyd-Warshall Algorithm (All-pairs shortest path)
  - Dynamic programming approach
  - Time Complexity: O(V³)

**Resources Used:**
- [Dijkstra's Algorithm - GeeksforGeeks](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/)
- [Bellman-Ford Algorithm - TutorialsPoint](https://www.tutorialspoint.com/)
- Algorithms course (MCS-211)

**Code Practiced:**
```c
// Dijkstra's Algorithm
#define INF 99999
#define V 6

int minDistance(int dist[], bool visited[]) {
    int min = INF, minIndex = -1;
    for(int v = 0; v < V; v++) {
        if(!visited[v] && dist[v] < min) {
            min = dist[v];
            minIndex = v;
        }
    }
    return minIndex;
}

void dijkstra(int graph[V][V], int src) {
    int dist[V];
    bool visited[V];
    
    for(int i = 0; i < V; i++) {
        dist[i] = INF;
        visited[i] = false;
    }
    
    dist[src] = 0;
    
    for(int count = 0; count < V - 1; count++) {
        int u = minDistance(dist, visited);
        visited[u] = true;
        
        for(int v = 0; v < V; v++) {
            if(!visited[v] && graph[u][v] && dist[u] != INF &&
               dist[u] + graph[u][v] < dist[v]) {
                dist[v] = dist[u] + graph[u][v];
            }
        }
    }
    
    printf("Vertex Distance from Source\n");
    for(int i = 0; i < V; i++) {
        printf("%d \t\t %d\n", i, dist[i]);
    }
}

// Bellman-Ford Algorithm
void bellmanFord(int graph[V][V], int src) {
    int dist[V];
    for(int i = 0; i < V; i++) {
        dist[i] = INF;
    }
    dist[src] = 0;
    
    for(int i = 1; i < V - 1; i++) {
        for(int u = 0; u < V; u++) {
            for(int v = 0; v < V; v++) {
                if(graph[u][v] && dist[u] != INF &&
                   dist[u] + graph[u][v] < dist[v]) {
                    dist[v] = dist[u] + graph[u][v];
                }
            }
        }
    }
    
    // Check for negative cycles
    for(int u = 0; u < V; u++) {
        for(int v = 0; v < V; v++) {
            if(graph[u][v] && dist[u] != INF &&
               dist[u] + graph[u][v] < dist[v]) {
                printf("Graph has negative cycle\n");
                return;
            }
        }
    }
    
    printf("Vertex Distance from Source\n");
    for(int i = 0; i < V; i++) {
        printf("%d \t\t %d\n", i, dist[i]);
    }
}
```

---

### 2. Minimum Spanning Tree and Cryptography Basics
**What I Learned (MST):**
- Kruskal's Algorithm
  - Sort edges by weight
  - Use Union-Find (Disjoint Set Union)
  - Time Complexity: O(E log E)
- Prim's Algorithm
  - Start from a vertex
  - Greedy approach
  - Time Complexity: O(V²)
- Applications: Network design, web crawling

**What I Learned (Cryptography):**
- Basic encryption concepts
- Caesar cipher and shift cipher
- Symmetric vs Asymmetric cryptography
- RSA algorithm basics
- Hash functions and digital signatures
- HTTPS and SSL/TLS protocols

**Resources Used:**
- [Kruskal's Algorithm - GeeksforGeeks](https://www.geeksforgeeks.org/kruskals-minimum-spanning-tree-algorithm-greedy-algo-2/)
- [Cryptography Basics - TutorialsPoint](https://www.tutorialspoint.com/)
- Security course notes

---

## 🔍 Challenges Faced:

| Challenge | Reason | Solution |
|---|---|---|
| **Dijkstra implementation** | Complex to track visited and unvisited vertices | Used explicit visited array and traced through algorithm step by step |
| **Bellman-Ford negative cycles** | Hard to detect and understand | Visualized with examples of graphs with negative cycles |
| **Union-Find in Kruskal's** | Tricky pointer logic for union operation | Implemented path compression and union by rank |

---

## 🎯 Tomorrow's Goals:

- [ ] Complete Kruskal and Prim algorithms implementation
- [ ] Study Dynamic Programming (Fibonacci, DP basics)
- [ ] Solve 0/1 Knapsack problem
- [ ] Practice 12+ graph and DP problems
- [ ] Study encryption and authentication protocols
- [ ] Learn about digital certificates

---

## 📊 Progress Metrics:

| Metric | Today | Total |
|---|---|---|
| Topics Covered | 2.5 | 12.5 |
| Programs Written | 5 | 49 |
| Problems Solved | 9 | 55 |
| Time Spent | 7.5 hours | 54.5 hours |
| Motivation Level | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

---

## 📝 Key Takeaways:

1. Dijkstra's is best for non-negative weights with single source
2. Bellman-Ford can detect negative cycles making it more robust
3. MST algorithms are essential for network design problems
4. Cryptography is critical in modern secure communications
5. Algorithm choice depends on specific problem constraints

---

## 📌 Notes & Reflections:

**What Went Well:**
- Implemented complex shortest path algorithms successfully
- Understanding of MST algorithms coming along well
- Connecting algorithms to real-world applications
- Problem-solving confidence increasing

**What Needs Improvement:**
- Need to optimize Dijkstra's with proper priority queue
- Should practice more graph algorithm problems
- Need to understand cryptography more deeply
- Should start solving LeetCode hard problems

---

**Next Session:** Day 10  
**Estimated Duration:** 8 hours

---

*"Your learning journey is unique. Celebrate small wins!" 🚀*
