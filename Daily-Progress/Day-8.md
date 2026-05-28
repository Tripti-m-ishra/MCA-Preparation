# Day 8 - MCA Preparation Progress

**Date:** May 25, 2026 
**Time Spent:** 8 hours  
**Mood:** 😊  
**Overall Progress:** 8.5/10

---

## ✅ What I Did Today:

### 1. Graph Data Structure - Fundamentals and Traversals
**What I Learned:**
- Graph terminology (vertices, edges, degree, path, cycle)
- Types of graphs (directed, undirected, weighted, unweighted)
- Graph representation (adjacency matrix, adjacency list)
- Depth First Search (DFS) and implementation
- Breadth First Search (BFS) and implementation
- Applications of DFS and BFS

**Resources Used:**
- [Graph Data Structure - GeeksforGeeks](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)
- Abdul Bari Graph Algorithms YouTube series
- MCS-211 course materials

**Code Practiced:**
```c
// Adjacency List representation
struct Node {
    int vertex;
    struct Node *next;
};

struct Graph {
    int numVertices;
    struct Node **adjList;
};

// DFS using recursion
void DFS(struct Graph *graph, int vertex, bool *visited) {
    visited[vertex] = true;
    printf("%d ", vertex);
    
    struct Node *temp = graph->adjList[vertex];
    while(temp) {
        if(!visited[temp->vertex]) {
            DFS(graph, temp->vertex, visited);
        }
        temp = temp->next;
    }
}

// BFS using queue
void BFS(struct Graph *graph, int startVertex) {
    bool *visited = (bool*)malloc(graph->numVertices * sizeof(bool));
    memset(visited, false, graph->numVertices * sizeof(bool));
    
    struct Queue q;
    initQueue(&q);
    
    visited[startVertex] = true;
    enqueue(&q, startVertex);
    
    while(q.front != -1 && q.front <= q.rear) {
        int vertex = dequeue(&q);
        printf("%d ", vertex);
        
        struct Node *temp = graph->adjList[vertex];
        while(temp) {
            if(!visited[temp->vertex]) {
                visited[temp->vertex] = true;
                enqueue(&q, temp->vertex);
            }
            temp = temp->next;
        }
    }
}
```

---

### 2. Transport Layer Protocols (TCP/IP)
**What I Learned:**
- TCP (Transmission Control Protocol)
  - Connection-oriented
  - Three-way handshake (SYN, SYN-ACK, ACK)
  - Flow control and congestion control
  - Reliability mechanisms
- UDP (User Datagram Protocol)
  - Connectionless
  - Fast but unreliable
  - No congestion control
  - Applications (DNS, video streaming, online games)
- Port numbers and sockets
- DNS protocol and resolution

**Resources Used:**
- [TCP/IP Protocol - GeeksforGeeks](https://www.geeksforgeeks.org/tcp-ip-model/)
- [TCP vs UDP - TutorialsPoint](https://www.tutorialspoint.com/)
- Networking course materials (MCS-218)

**Key Concepts:**
```
TCP Three-Way Handshake:
1. Client sends SYN (synchronization) packet
2. Server responds with SYN-ACK (synchronization-acknowledgment)
3. Client sends ACK (acknowledgment)

TCP/IP Stack:
- Application Layer: HTTP, HTTPS, FTP, SMTP, DNS
- Transport Layer: TCP, UDP, SCTP
- Internet Layer: IP (IPv4, IPv6), ICMP, IGMP
- Link Layer: Ethernet, PPP, ARP
```

---

## 🔍 Challenges Faced:

| Challenge | Reason | Solution |
|---|---|---|
| **Graph adjacency list** | Hard to manage pointer logic for linked lists | Implemented carefully and tested with small graphs |
| **DFS vs BFS** | When to use which algorithm | Understood use cases: DFS for paths/cycles, BFS for shortest path |
| **TCP handshake** | Three-way process was confusing | Memorized and drew diagrams for each step |

---

## 🎯 Tomorrow's Goals:

- [ ] Study shortest path algorithms (Dijkstra, Bellman-Ford)
- [ ] Implement Dijkstra's algorithm
- [ ] Study minimum spanning tree (Kruskal, Prim)
- [ ] Practice 10+ graph algorithm problems
- [ ] Study HTTP/HTTPS protocols
- [ ] Learn socket programming basics

---

## 📊 Progress Metrics:

| Metric | Today | Total |
|---|---|---|
| Topics Covered | 2 | 10 |
| Programs Written | 4 | 44 |
| Problems Solved | 7 | 46 |
| Time Spent | 8 hours | 47 hours |
| Motivation Level | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

---

## 📝 Key Takeaways:

1. Graph algorithms are powerful for solving complex real-world problems
2. DFS uses recursion/stack (implicit), BFS uses queue
3. TCP is reliable but slower, UDP is fast but unreliable
4. Understanding network protocols helps in web development
5. Adjacency list is more efficient than adjacency matrix for sparse graphs

---

## 📌 Notes & Reflections:

**What Went Well:**
- Successfully implemented graph traversal algorithms
- Understanding of network protocols improving
- Able to visualize graph algorithms mentally
- Connected theory with practical applications

**What Needs Improvement:**
- Need more practice with graph problems
- Should implement Dijkstra and other shortest path algorithms
- Need to understand advanced networking concepts
- Should practice more complex graph scenarios

---

**Next Session:** Day 9  
**Estimated Duration:** 8 hours

---

*"Your learning journey is unique. Celebrate small wins!" 🚀*
