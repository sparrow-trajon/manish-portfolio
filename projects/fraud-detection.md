# 🛡️ Real-Time Fraud Detection System

## 🔍 Overview

As the Technical Lead at an RBI-authorized payment gateway and aggregator, I architected and built a real-time fraud detection system from scratch. The goal was to detect and prevent fraudulent financial transactions with **sub-second latency** and **zero false positives** under heavy transaction load.

---

## 🏗️ System Architecture

> Built using microservice-based architecture with real-time streaming and decisioning using Drools and Redis Streams.

**Key Components**:

- **Transaction Ingestion Service**: Accepts incoming financial transactions in real time.
- **Rule Engine (Drools)**: Applies dynamic business rules on-the-fly.
- **Redis Stream Processor**: Enables event-driven fraud analysis and tracking.
- **PostgreSQL**: Stores audit trail, decision logs, fraud flags, and customer behavior.
- **Redis Cache**: For hot data (merchant thresholds, blacklists, behavior patterns).

```plaintext
[Client] → [API Gateway] → [Fraud Detection Engine] → [Drools Evaluation]
                                              ↓
                                [Redis Cache + Redis Stream]
                                              ↓
                                   [DB + Alerting Service]
```

---

## 💻 Tech Stack

| Component            | Technology                        |
| -------------------- | --------------------------------- |
| Backend Language     | Java 17                           |
| Framework            | Spring Boot (Microservices)       |
| Rule Engine          | Drools 7.x                        |
| Cache + Stream       | Redis (cache + stream)            |
| Database             | PostgreSQL 13                     |
| Communication        | REST APIs, Redis Pub/Sub          |
| Logging & Monitoring | ELK Stack, Micrometer, Prometheus |
| Deployment           | Docker, Jenkins, GitHub Actions   |

---

## 👨‍💼 My Responsibilities

- Led the system design and architecture from scratch.
- Implemented Drools rule templates for merchant behavior, location mismatch, card pattern fraud, etc.
- Built high-throughput async stream processing using Redis Streams.
- Designed real-time fraud alerts & webhook notification service.
- Mentored a backend team of 4 engineers and conducted code reviews, design sessions.

---

## 🧠 Key Challenges & Solutions

| Challenge                         | Solution Implemented                                 |
| --------------------------------- | ---------------------------------------------------- |
| Sub-second detection latency      | Redis Streams + in-memory pattern caching            |
| Dynamic rule updates in runtime   | Drools rule templates with hot reload support        |
| High transaction volume (>50 TPS) | Stream sharding + multithreaded consumer workers     |
| Audit + traceability of decisions | Built audit trail with decision reasons & timestamps |

---

## 📈 Results & Impact

- ⏱️ Reduced fraud decision latency from ~500ms to ~50ms
- 📉 Blocked fraudulent transactions worth ₹7 Cr in first 3 months
- ⚙️ Scaled to handle over **1M transactions per day**
- 🚨 Zero major fraud incidents post-deployment

---

## 📄 Learnings

- Deep understanding of fraud patterns in the payments ecosystem
- Advanced Redis (streaming, consumer groups, pipelining)
- Real-time design patterns using async, parallel rule evaluation
- Designing systems with observability, auditability, and failover

---

> 💡 _“Build for accuracy first, scale second, and then tune for latency”_ — this became our team’s guiding principle.
