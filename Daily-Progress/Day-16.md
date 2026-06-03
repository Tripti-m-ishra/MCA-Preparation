# Day 16 - MCA Preparation Progress

**Date:** June 2, 2026  
**Time Spent:** 8 hours  
**Mood:** 😊  
**Overall Progress:** 8.5/10

---

## ✅ What I Did Today:

### 1. Design Patterns - Creational & Structural
**What I Learned:**
- Singleton pattern (single instance)
- Factory pattern (object creation)
- Builder pattern (complex object construction)
- Abstract Factory pattern
- Prototype pattern
- Adapter pattern
- Decorator pattern
- Bridge pattern
- Facade pattern
- Proxy pattern

**Resources Used:**
- [Design Patterns - GeeksforGeeks](https://www.geeksforgeeks.org/design-patterns-set-1-introduction/)
- [Refactoring Guru](https://refactoring.guru/design-patterns)
- MCS-219 Object Orientation & Design

**Code Examples:**
```java
// Singleton Pattern
public class Database {
    private static Database instance;
    
    private Database() {}
    
    public static synchronized Database getInstance() {
        if(instance == null)
            instance = new Database();
        return instance;
    }
}

// Factory Pattern
public class ShapeFactory {
    public static Shape createShape(String type) {
        if("circle".equals(type))
            return new Circle();
        if("rectangle".equals(type))
            return new Rectangle();
        return null;
    }
}

// Builder Pattern
public class House {
    private String walls;
    private String roof;
    private String door;
    
    public static class Builder {
        private String walls;
        private String roof;
        private String door;
        
        public Builder withWalls(String walls) {
            this.walls = walls;
            return this;
        }
        
        public Builder withRoof(String roof) {
            this.roof = roof;
            return this;
        }
        
        public Builder withDoor(String door) {
            this.door = door;
            return this;
        }
        
        public House build() {
            House house = new House();
            house.walls = this.walls;
            house.roof = this.roof;
            house.door = this.door;
            return house;
        }
    }
}
```

---

### 2. System Design Basics
**What I Learned:**
- Scalability concepts (vertical, horizontal)
- Load balancing
- Caching strategies (LRU, LFU)
- Database design (SQL vs NoSQL)
- Microservices architecture
- API design best practices
- Rate limiting
- Monitoring and logging

**Resources Used:**
- [System Design Primer](https://github.com/donnemartin/system-design-primer)
- [High Scalability](http://highscalability.com/)
- MCS-221 Software Architecture

**Key Concepts:**
```
Horizontal Scaling:
- Add more servers
- Requires load balancing
- More complex but better for fault tolerance

Caching:
- LRU: Remove least recently used
- LFU: Remove least frequently used
- Can be in-memory or distributed

Database Replication:
- Master-Slave: Read replicas
- Master-Master: Multiple writes
- Trade-off between consistency and availability
```

---

### 3. Competitive Programming - System Design & Interview Questions
**What I Did:**
- Solved design-based interview problems
- Practiced LLD and HLD discussions

**Problems Solved:**
1. Design LRU Cache (Hard)
2. Design LFU Cache (Hard)
3. Design Twitter Feed (Medium)
4. Design Parking Lot (Medium)
5. Design URL Shortener (Medium)
6. Design Rate Limiter (Medium)
7. Design File Sharing System (Hard)
8. Design Search Autocomplete (Hard)
9. Design Online Judge (Hard)
10. Design Stock Exchange (Hard)

---

## 🔍 Challenges Faced:

| Challenge | Reason | Solution |
|---|---|---|
| **Pattern Selection** | Knowing which pattern to use difficult | Created decision tree, studied use cases |
| **System Design Complexity** | Too many components to consider | Started with simple systems, added complexity |
| **Trade-offs** | Understanding consistency vs availability | Studied CAP theorem in detail |
| **Interview Communication** | Explaining design decisions clearly | Practiced articulating thoughts |

---

## 📊 Daily Metrics:

| Metric | Value |
|---|---|
| Topics Covered | 3 |
| Programs Written | 7 |
| Problems Solved | 10 |
| Time Spent | 8 hours |
| Motivation Level | ⭐⭐⭐⭐⭐ |

---

## 📝 Key Takeaways:

1. Design patterns solve recurring problems
2. Each pattern has specific use cases
3. System design requires trade-off analysis
4. Scalability is crucial for modern systems
5. LRU cache is fundamental for caching

---

**Next Session:** Day 17 (Week 3 Review)  
**Estimated Duration:** 8 hours

---
