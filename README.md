Distributed Patient Management System:


Distributed healthcare backend is built using Java, Spring Boot, Kafka, gRPC, Docker, PostgreSQL where the system follows a microservices-based architecture to ensure modularity, resilience, and high performance.

Architecture Overview:

The system consists of four independent microservices:
Auth Service – Handles user authentication and JWT token generation.
Patient Service – Manages patient records and core business logic.
Billing Service – Handles billing operations using gRPC.
Analytics Service – Consumes system events using Kafka for real-time analytics.

All external requests are routed through a centralized API Gateway.


System Flow


1)  Authentication :
  a) Client sends request to API Gateway.
  b) Gateway routes it to Auth Service.
  c) On success, Auth Service returns a JWT token.

2)  Patient Operations :
  a) Client sends requests with JWT token.
  b) API Gateway validates and routes them to Patient Service.  
  c) Patient Service performs CRUD operations and business validations.

3) Billing Integration (gRPC):
  a) Patient Service acts as a gRPC client.
  b) Billing Service acts as a gRPC server.
  c) Communication is done via gRPC for:
                              i.Low latency
                              ii.High throughput

4) Analytics Integration (Kafka) :
  a) Patient Service publishes events to Kafka Broker.
  b) Analytics Service consumes events asynchronously.
  c) Enables real-time analytics and event-driven workflows.

<img width="1681" height="936" alt="64e35189-402d-49a7-a819-fe701987ba6b" src="https://github.com/user-attachments/assets/84a5cd9c-9e58-4954-aaa3-a3a820feae4c" />



Key Features

a) Microservices architecture
b) JWT-secured REST APIs
c) gRPC-based low-latency communication
d) Kafka-based event-driven analytics
e) API Gateway routing
f) Schema validation
g) Idempotent event handling
h) Centralized error propagation
i) Dockerized deployments


Reliability & Robustness

a) End-to-end integration tests
b) Contract-based schema validation
c) Idempotent Kafka consumers
d) Distributed error handling
e) Graceful failure recovery
Analytics Service consumes events asynchronously.

Enables real-time analytics and event-driven workflows.
