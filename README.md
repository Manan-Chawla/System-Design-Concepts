# 🏗️ System Design Masters: Architecture & Scalable Patterns

A comprehensive repository dedicated to the art of designing large-scale distributed systems. This space serves as a living document of architectural patterns, trade-offs, and deep dives into cloud-native infrastructure—all backed by **detailed notes** and **visual diagrams**.

---

## 🗺️ Learning Roadmap & Core Concepts

I've broken down the complexities of system design into digestible modules. Each section includes a deep-dive note and a pictorial representation of the workflow.

| Module | Core Concepts | Visual Focus |
| :--- | :--- | :--- |
| **01. Fundamentals** | Vertical vs Horizontal Scaling, CAP Theorem, PACELC | Scaling Diagrams |
| **02. Networking** | OSI Model, DNS, Load Balancing (L4 vs L7), CDNs | Traffic Flow |
| **03. Databases** | SQL vs NoSQL, Replication, Sharding, Indexing | Data Partitioning |
| **04. Communication** | REST, gRPC, WebSockets, Message Queues (Pub/Sub) | Async Messaging |
| **05. Caching** | Write-through, Write-back, Cache Eviction (LRU/LFU) | Cache Hit/Miss |
| **06. Reliability** | Circuit Breakers, Retries, Exponential Backoff | Failure Handling |

---

## 🎨 Pictorial Deep Dives

*Example of how I document architectures:*

### High-Level Web Architecture
> [!TIP]
> **Check out the `assets/diagrams/` folder for the high-resolution versions of these sketches.**

```mermaid
graph TD
    A[Client/User] -->|Request| B(DNS)
    B -->|IP Address| A
    A -->|HTTPS| C[Load Balancer]
    C --> D[Web Server 1]
    C --> E[Web Server 2]
    D --> F{Distributed Cache}
    E --> F
    F -->|Cache Miss| G[(Primary DB)]
    G -->|Replicate| H[(Read Replica)]
