# System Design Basics

## Think about

- Data:
  - How much data do we have? (Volume)
  - How fast is the data growing? (Growth)
  - How often is the data changing? (Change - Velocity)
  - Is the data structured or unstructured? (SQL or NoSQL)
  - Is the data read-heavy or write-heavy? (Read or Write)
  - Is the data time-series or non-time-series? (Time-series or non-time-series)
  - Is the data public or private? (Public or Private)
  - Is the data real-time or batch? (Real-time or Batch)
  - Is the data static or dynamic? (Cache or Database)
  - Is the data strongly consistent or eventually consistent? (Consistency)
  - Is the data small Files or large Files? (Small or Large)
  - Is the data streaming or non-streaming? (Streaming or Non-streaming)
- Traffic:
  - How many requests per second? (QPS)
  - How many requests per second per user? (RPS)
  - Is the traffic constant or bursty? (Constant or Bursty)
  - Is the traffic predictable or unpredictable? (Predictable or Unpredictable)
  - Is the traffic global or local? (Global or Local)
  - Is the session long or short? (Long or Short)
- Service:
  - is the compute CPU-bound or memory-bound? (CPU or Memory)
  - is the storage I/O-bound or network-bound? (I/O or Network)
  - is the network bandwidth-bound or latency-bound? (Bandwidth or Latency)
  - is the service stateless or stateful? (Stateless or Stateful)
  - is the service synchronous or asynchronous? (Synchronous or Asynchronous)
  - is the service real-time or batch? (Real-time or Batch)
  - is it monolithic or microservices? (Monolithic or Microservices)
  - is it vertical or horizontal scaling? (Vertical or Horizontal)
- Users:
  - How many users do we have? (Users)
  - How many users are active at the same time? (Concurrent Users)
  - How many users are active per day? per month? per year? (DAU, MAU, WAU)
  - How fast is the user base growing? (Growth)
- Performance:
  - How fast do we need to respond? (Latency)
  - How much latency can we tolerate? (Tolerance)
  - How much throughput do we need? (Throughput)
- Availability:
  - How much downtime can we tolerate? (Tolerance)
  - How much data loss can we tolerate? (Data Loss)
- Scalability:
  - How much traffic can we handle? (Traffic)
  - How much data can we store? (Data)
- Reliability:

## System Design Process

## Design Your System App (DYSAPP)

Problem Statement: Create a software system where users can practice the system design problems by creating a solution
to the system design problem and then the software system should be able to review the solution and provide feedback.

- The software should be able to create the code for the system design solution as defined by the user.
- On the left side of the screen, the user should be able to see the building blocks of the system design solution. The
  user should be able to drag and drop the building blocks to create the system design solution.
- The user should be able to add the details of the system design solution in the text area on the right side of the screen.
- The user should be able to save the system design solution
- The system should be able to test the system design solution and find the issues in the system design solution.

- The building blocks includes:
  - Server (Web, Application, Database)
    - Database (SQL, NoSQL)
    - Cache (Redis, Memcached)
  - Cache (Read-Through, Write-Through, Write-Behind)
  - Queue (FIFO, Priority, Delay)
  - Message Broker (Pub/Sub, Fan-out, Fan-in)
  - Network (CDN, VPN, Firewall)
  - Load Balancer (Hash, Round Robin, Least Connections, Custom)
  - DNS (Round Robin, Geo-Location, Latency)
  - Storage (Block, Object, File)
  - Compute (VM, Container, Serverless)
  - Monitoring (Push, Pull, Polling)
  - Logging (Structured, Unstructured, Centralized)
  - Tracing (Distributed, Centralized, Sampling)
  - Alerting (Threshold, Anomaly, Correlation)
  - Security (Authentication, Authorization, Encryption)
  - Deployment (Blue-Green, Canary, Rolling)
  - API (REST, GraphQL, gRPC)
  - Flow Control (Rate Limiting, Circuit Breaker, Bulkhead)
  - Flags (Feature, Kill, Experiment)
  - Scaling (Vertical, Horizontal)
  - Availability (Active-Active, Active-Passive)
  - Backup (Full, Incremental, Differential)
  - Restore (Point-in-Time, Continuous, Snapshot)
  - Disaster Recovery (Backup, Restore, Failover)
  - Documentation (API, Architecture, User)
