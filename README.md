# Unnamed-protocol
TrustNet is an AI-powered financial crime intelligence platform that analyzes millions of banking transactions using graph analytics, behavioral risk detection, and explainable AI to identify money mule networks, trace stolen fund flows, and generate evidence-backed investigation reports.
# 🛡️ TrustNet
## AI-Powered Money Mule Network Detection & Digital Forensics Platform

### Void Hacks 8.0
### Theme: Cyber Security & Digital Forensics

---

# 📌 Overview

TrustNet is an offline high-throughput cyber financial crime investigation platform designed to analyze millions of banking transactions and identify suspicious money mule networks.

The system transforms traditional transaction records into an intelligent transaction graph, detects laundering patterns using graph analytics and temporal behavior analysis, traces stolen money flows, and generates evidence-backed investigation reports.

The goal is to help law enforcement investigators quickly answer:

> "Where did the victim's money go, who handled it, and where did it finally reach?"

---

# 🚨 Problem Statement

Modern financial cybercrimes involve complex money mule networks where criminals rapidly move stolen funds through multiple accounts.

Traditional transaction analysis struggles because of:

- Millions of transaction records
- Multi-hop money movement
- Layered mule networks
- Time-sensitive investigation requirements
- Manual evidence preparation

TrustNet solves this by combining:

- High-performance data processing
- Graph-based analysis
- Behavioral risk detection
- Explainable investigation intelligence

---

# 🎯 Objectives

## Core Goals

✅ Process millions of transaction records efficiently

✅ Convert banking transactions into a searchable graph

✅ Detect suspicious mule account behavior

✅ Trace victim money trails up to multiple hops

✅ Provide explainable risk analysis

✅ Generate evidence-grounded investigation reports

---

# 🏗️ System Architecture


```
                 Banking Transactions
                         |
                         |
                         v

              High Speed Data Engine
              (DuckDB + Parquet)

                         |
                         v

              Transaction Graph Builder

                         |
        -----------------------------------
        |                |                |
        v                v                v

   Fan-In Analysis   Fan-Out Analysis   Velocity Analysis

        |                |                |

        -----------------------------------
                         |
                         v

                 Mule Risk Engine

                         |
                         v

              4-Hop Money Trail Engine
                    (BFS)

                         |
                         v

                 Evidence Graph

                         |
        --------------------------------
        |                              |
        v                              v

 Interactive Graph UI          AI Case Officer

        |                              |

        v                              v

 Investigation View        Case Diary & Freeze Request

```

---

# 🚀 Key Features

## 1. High-Speed Transaction Processing

- Handles large banking transaction datasets
- Uses DuckDB optimized analytical queries
- Memory-efficient processing

---

## 2. Transaction Graph Construction

Converts:

```
Sender Account → Receiver Account
```

into:

```
Account Node
      |
      |
Transaction Edge
```

Each edge stores:

- Transaction ID
- Amount
- Timestamp
- Payment Mode
- IFSC information

---

# 3. Money Flow Fingerprint

Every account receives a behavioral profile:

Example:

```
Account: XXXXX

Fan-In:
Multiple incoming connections

Fan-Out:
Multiple outgoing connections

Velocity:
Fast movement of received funds

Terminal:
Connection to final cash-out points
```

---

# 4. Mule Detection Engine

The system detects suspicious patterns using:

## Fan-In Detection

Identifies accounts receiving money from multiple sources.

Example:

```
A ----\
B -----\
C ------> Account X
D -----/
```

---

## Fan-Out Detection

Identifies accounts distributing money to multiple accounts.

Example:

```
             B
             |
A ---------- C
             |
             D

```

---

## Velocity Detection

Detects rapid movement of funds.

Example:

```
10:00
Victim → Account X
₹1,00,000


10:05
Account X → Multiple Accounts
₹90,000

High Velocity Pattern
```

---

## Terminal Detection

Identifies possible final destinations:

- Payment wallets
- Crypto related destinations
- Suspicious device/IP patterns

---

# 5. Explainable Mule Risk Score

Instead of only giving a score:

```
Risk Score: 92
```

The system explains:

```
Reasons:

✓ High Fan-In
✓ High Fan-Out
✓ 90% funds transferred quickly
✓ Connected to terminal node

```

---

# 6. 4-Hop Money Trail Analysis

Given a victim account:

```
Victim

   |
   v

Layer 1 Mule

   |
   v

Layer 2 Distributor

   |
   v

Layer 3 Terminal

```

The BFS-based engine traces the complete money movement path.

---

# 7. Evidence Graph

Every detection decision is connected with original evidence.

Example:

```
Risk Score: 91

Evidence:

Transaction ID:
TX12345

Amount:
₹50,000

Timestamp:
10:05:23

Payment:
UPI

```

---

# 8. Money Flow Replay

Investigators can visualize:

```
10:00
Victim → Mule


10:05
Mule → Distributor


10:10
Distributor → Terminal

```

to understand how funds moved over time.

---

# 9. Reverse Investigation

Supports tracing:

Forward:

```
Victim → Mule → Terminal
```

Reverse:

```
Terminal → Mule → Victim
```

---

# 10. AI Case Officer

AI is used only for documentation.

Flow:

```
Verified Transaction Evidence

          |

          v

AI Report Generator

          |

          v

Case Diary
Freeze Requisition

```

The AI does not create facts.
All generated information comes from verified transaction evidence.

---

# 🛠️ Technology Stack

## Backend

- Python
- FastAPI
- DuckDB
- Polars
- Pandas
- PyArrow

## Graph Processing

- Custom Graph Engine
- BFS Traversal

## Frontend

- React / Next.js
- Cytoscape.js
- D3.js

## AI Layer

- LLM-based Report Generation
- Evidence Validation

## Storage

- Parquet
- DuckDB Database

---

# 📂 Project Structure

```
TrustNet/

│
├── backend/
│
│   ├── ingestion/
│   │     └── loader.py
│
│   ├── graph/
│   │     ├── builder.py
│   │     └── bfs.py
│
│   ├── detection/
│   │     ├── fan_in.py
│   │     ├── fan_out.py
│   │     ├── velocity.py
│   │     ├── terminal.py
│   │     └── risk_engine.py
│
│   ├── evidence/
│   │     └── evidence_graph.py
│
│   ├── reports/
│   │     └── case_generator.py
│
│   └── api/
│         └── main.py
│
├── frontend/
│
├── data/
│
├── README.md
│
└── requirements.txt

```

---

# ⚙️ Installation

Clone repository:

```bash
git clone <repository-url>

cd TrustNet
```

Create environment:

```bash
python -m venv venv

venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# ▶️ Running the Project

Backend:

```bash
uvicorn backend.api.main:app --reload
```

Frontend:

```bash
npm install

npm run dev
```

---

# 📊 Evaluation Metrics

The system focuses on:

- Transaction processing speed
- Detection accuracy
- Money trail tracing speed
- Explainability
- Evidence generation quality

---

# 🔮 Future Enhancements

- Graph Neural Networks for advanced pattern detection
- Real-time transaction monitoring
- More advanced anomaly detection
- Multi-bank intelligence integration
- Automated investigation workflow

---

# 👨‍💻 Team

Developed for:

**Void Hacks 8.0**

Theme:

**Cyber Security & Digital Forensics**

---

# 📜 License

This project is developed for educational and cybersecurity research purposes.
