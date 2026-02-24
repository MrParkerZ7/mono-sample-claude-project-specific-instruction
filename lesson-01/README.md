# Lesson 01: DrawIO Architecture Diagrams

This lesson provides guidelines and sample diagrams for creating architecture documentation using DrawIO.

## Contents

### Guidelines

- **CLAUDE.md** - Comprehensive DrawIO guidelines for Claude Code covering:
  - Cloud platforms (AWS, Azure, GCP)
  - Kubernetes & container orchestration
  - Network & infrastructure diagrams
  - Software architecture (DDD, microservices)
  - Database diagrams (SQL/NoSQL)
  - Data workflow & ETL
  - BPMN, flowcharts, sequence diagrams

### Sample Diagrams

| File | Description |
|------|-------------|
| `sample-aws-ecs-architecture.drawio` | AWS ECS architecture with VPC, subnets, Fargate, RDS, Redis |
| `sample-aws-portal-k8s-insurance.drawio` | AWS + Kubernetes insurance portal architecture |
| `sample-core-banking-ddd.drawio` | Domain-Driven Design for core banking (deposit, withdraw, ITMX) |
| `sample-payment-flow-sequence.drawio` | Payment flow sequence diagram (Mobile to ITMX/PromptPay) |
| `sample-insurance-cobroker-portal-k8s-onprem.drawio` | On-premises Kubernetes architecture for insurance co-broker portal |

## Diagram Types Covered

- **Cloud Architecture** - AWS, Azure, GCP service diagrams
- **Kubernetes** - Cluster architecture, namespaces, deployments
- **Domain-Driven Design** - Bounded contexts, aggregates, domain events
- **Sequence Diagrams** - Request/response flows, API interactions
- **Network Diagrams** - Firewalls, load balancers, VPNs
- **Data Flow** - ETL pipelines, message queues, event streaming

## Usage

1. Open any `.drawio` file with [draw.io](https://app.diagrams.net/) or VS Code DrawIO extension
2. Refer to `CLAUDE.md` for shape references and style guidelines
3. Use the sample diagrams as templates for your own architecture documentation
