# DrawIO Diagram Standards

Standards and templates for generating professional DrawIO architecture diagrams with Claude Code.

## Purpose

This folder contains reference materials and standards for creating DrawIO diagrams.

## Contents

### CLAUDE-DIAGRAMS-STANDARD-FORMAT.md

The main standards file containing:
- DrawIO XML structure and syntax
- Shape references for all major platforms (AWS, Azure, GCP, Kubernetes)
- Network and infrastructure shapes
- C4 Model architecture diagrams
- Software architecture patterns (DDD, microservices, UML)
- Database ERD (Entity-Relationship Diagrams)
- Data workflow and ETL shapes
- BPMN, flowcharts, sequence diagrams
- Arrow color standards (protocol-based)
- Style guidelines, colors, and best practices

### Sample Diagrams

Reference diagrams organized by category:

| Folder | Description | Samples |
|--------|-------------|---------|
| [sample-architecture/](./sample-architecture/) | Cloud & infrastructure diagrams | AWS ECS, Azure WebApp, AWS+K8s, On-Prem K8s |
| [sample-c4-model/](./sample-c4-model/) | C4 Model architecture | Core Banking (Context, Container, Component) |
| [sample-domain-driven-design/](./sample-domain-driven-design/) | DDD diagrams | Core Banking bounded contexts |
| [sample-entity-erd/](./sample-entity-erd/) | Database ERD | Property Agent (PostgreSQL, MongoDB, Redis, ES) |
| [sample-sequence/](./sample-sequence/) | Sequence diagrams | Payment Flow |
| [sample-autoclickkey-workflow/](./sample-autoclickkey-workflow/) | Application workflow | [AutoClickKey](https://github.com/MrParkerZ7/app-auto-key-click-x-claude) data flow |

### Preview

#### Cloud Architecture
![AWS ECS](./sample-architecture/sample-architecture-aws-ecs.png)

#### C4 Model
![C4 Model](./sample-c4-model/sample-c4-model-core-banking.png)

#### Entity-Relationship Diagram
![ERD](./sample-entity-erd/sample-entity-property-agent-database.png)

### PROMPT_TEMPLATE.md

Ready-to-use prompt template for generating comprehensive diagrams. Copy, paste, and replace the project path.

## Usage

**Option 1: Copy to your project (auto-load)**
1. Copy `CLAUDE-DIAGRAMS-STANDARD-FORMAT.md` to your project root as `CLAUDE.md`
2. Claude Code will automatically load the instructions
3. Ask Claude to create DrawIO diagrams

**Option 2: Reference in prompt (no copy needed)**
1. Use the prompt from `PROMPT_TEMPLATE.md`
2. It references the standards file directly
3. Replace `[YOUR_PROJECT_PATH]` with your project path

## Arrow Color Standards

Protocol-based colors for consistent architecture diagrams:

| Protocol | Color | Hex |
|----------|-------|-----|
| HTTP/HTTPS/API | Gray | `#232F3E` |
| Database (SQL) | Purple | `#C925D1` |
| Cache (Redis) | Red | `#DC382D` |
| Message Queue | Pink | `#E7157B` |
| Storage | Green | `#7AA116` |
| Auth/Security | Dark Red | `#DD344C` |

## Diagram Types Supported

- Cloud Architecture (AWS, Azure, GCP)
- Kubernetes cluster architecture
- C4 Model (Context, Container, Component)
- Domain-Driven Design diagrams
- Sequence diagrams
- Network topology
- Data flow and ETL pipelines
- BPMN workflow diagrams
- Database ERD (multi-database: SQL, NoSQL, Cache, Search)
- Application data workflow
