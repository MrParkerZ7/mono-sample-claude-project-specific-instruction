# DrawIO CLAUDE.md Research

Project-specific instructions (CLAUDE.md) for Claude Code to generate DrawIO architecture diagrams.

## Purpose

This folder contains research and reference materials for creating `CLAUDE.md` files that enable Claude Code to generate professional DrawIO diagrams.

## Contents

### CLAUDE.md

The main reference file containing:
- DrawIO XML structure and syntax
- Shape references for all major platforms (AWS, Azure, GCP, Kubernetes)
- Network and infrastructure shapes
- Software architecture patterns (DDD, microservices, UML)
- Database diagrams (SQL/NoSQL)
- Data workflow and ETL shapes
- BPMN, flowcharts, sequence diagrams
- Style guidelines, colors, and best practices

### Sample Diagrams

Reference diagrams demonstrating the CLAUDE.md guidelines:

| File | Description |
|------|-------------|
| `sample-aws-ecs-architecture.drawio` | AWS ECS with VPC, subnets, Fargate, RDS, Redis |
| `sample-aws-portal-k8s-insurance.drawio` | AWS + Kubernetes insurance portal |
| `sample-core-banking-ddd.drawio` | Domain-Driven Design for core banking (ITMX) |
| `sample-payment-flow-sequence.drawio` | Payment sequence diagram (Mobile to ITMX) |
| `sample-insurance-cobroker-portal-k8s-onprem.drawio` | On-premises K8s architecture |
| `sample-property-agent-database-erd.drawio` | Property agent system ERD (SQL/NoSQL/Cache) |

## Usage

1. Copy `CLAUDE.md` to your project root or `.claude/` folder
2. Claude Code will use the instructions when generating DrawIO diagrams
3. Reference sample diagrams for expected output format

## Diagram Types Supported

- Cloud Architecture (AWS, Azure, GCP)
- Kubernetes cluster architecture
- Domain-Driven Design diagrams
- Sequence diagrams
- Network topology
- Data flow and ETL pipelines
- BPMN workflow diagrams
- Database ERD (Entity-Relationship Diagrams)
