# IdemLedger 🏦

**IdemLedger** is a high-availability, idempotency-first banking ledger built on **PostgreSQL 17** and **Go**. 

Designed for mission-critical financial environments, it ensures that even in the face of network partitions, service restarts, or "double-click" user errors, every transaction is processed exactly once.

Current Status: 🏗️ Alpha / Active Development > Phase 1: Core Ledger & Idempotency Engine (Current Focus)

## 🗺 Project Roadmap

- [x] **Phase 1: Schema Design** (Postgres 17, Idempotency-first tables)
- [x] **Phase 2: HA Topology** (Patroni + Etcd + HAProxy configuration)
- [ ] **Phase 3: Core API** (Go implementation of Idempotency Middleware)
- [ ] **Phase 4: Resilience Testing** (Chaos engineering & automated failover drills)
- [ ] **Phase 5: Observability** (Grafana Dashboards for Transaction Correctness)
      
---

## 🛠 High-Availability Architecture
This project implements a "Zero-Trust" infrastructure approach:
* **Consensus-Driven Failover:** Managed by **Patroni** and **Etcd** to ensure zero data loss during primary node failure.
* **Deterministic Idempotency:** Custom Go middleware utilizing PostgreSQL `UNIQUE` constraints to handle distributed race conditions.
* **Observability:** Built-in Prometheus metrics for tracking "Idempotency Hits" vs. "New Transactions."
* **Reliability:** Automated point-in-time recovery (PITR) configurations for DBRE-grade durability.



## 🚀 Key Features
- **Strict Idempotency:** Header-based key tracking with state-machine locking.
- **Double-Entry Standard:** Guaranteed balance integrity via atomic transactions.
- **Postgres 17 Optimized:** Leveraging the latest JSONB improvements for audit trails.
- **Cloud-Native:** Ready for deployment on **Kubernetes** with default-deny NetworkPolicies.

## ⚖️ License
Distributed under the MIT License. See `LICENSE` for more information.
