# DrawIO Diagram Style Guide (Universal)

## Overview

This document defines **universal styling rules** for all DrawIO diagrams including:
- **Cloud Architecture** (AWS, Azure, GCP, Kubernetes)
- **C4 Model** (Context, Container, Component)
- **Sequence Diagrams**
- **ERD** (Entity-Relationship Diagrams)
- **Data Flow / ETL Diagrams**
- **Network / Security Diagrams**
- **DDD** (Domain-Driven Design)
- **CI/CD Pipeline Diagrams**
- **Flowcharts / BPMN**
- **State Machine Diagrams**

---

## Grid System

- Grid size: `10px` (1 block)
- All spacing values are **minimums**

### Grid Snap Rule (MANDATORY)

**All positions and sizes MUST end with `0` (multiples of 10px)**

| Property | Rule | Valid Examples | Invalid Examples |
|----------|------|----------------|------------------|
| Position X | Must end with 0 | `10`, `20`, `100`, `250` | `15`, `23`, `108`, `255` |
| Position Y | Must end with 0 | `10`, `20`, `100`, `250` | `15`, `23`, `108`, `255` |
| Width | Must end with 0 | `60`, `100`, `200`, `450` | `65`, `98`, `215`, `448` |
| Height | Must end with 0 | `60`, `100`, `200`, `450` | `65`, `98`, `215`, `448` |

---

## Minimum Spacing Rules

### Containers/Groups

| Rule | Minimum Value | Description |
|------|---------------|-------------|
| Margin from parent | `10px` (1 block) | Minimum distance from parent container edge |
| Title padding | `+20px` (2 blocks) | Additional top space for containers with titles |
| Content start Y | `30px` minimum | For titled containers: 10px margin + 20px title |

### Shapes/Icons

| Rule | Minimum Value | Description |
|------|---------------|-------------|
| Margin from edges | `10px` (1 block) | Minimum distance from container edge |
| Bottom label space | `+20px` (2 blocks) | Additional space for shapes with bottom text labels |
| Horizontal gap | `30px` minimum | Minimum space between adjacent icons (edge-to-edge) |

### Icon/Shape Size Standard

**Rule: The shorter side must be at least 6 blocks (60px)**

| Aspect Ratio | Size (blocks) | Size (px) | Example |
|--------------|---------------|-----------|---------|
| 1:1 (square) | 6 x 6 | 60 x 60 | Standard service icons, C4 boxes |
| 1:2 | 6 x 12 | 60 x 120 | Tall icons (person, server rack) |
| 2:1 | 12 x 6 | 120 x 60 | Wide icons (load balancer banner) |
| ERD Table | 20 x variable | 200 x auto | Database tables |
| Sequence Lifeline | 6 x variable | 60 x auto | Sequence participants |

---

## CRITICAL: Arrows/Connections (MANDATORY)

**Every diagram MUST include arrows/connections showing relationships between elements.** A diagram without connections is incomplete and meaningless.

### Universal Arrow Rules

| Rule | Description |
|------|-------------|
| **All elements must connect** | No orphan/floating elements without connections |
| **Direction matters** | Arrows show data/control flow direction |
| **Labels are helpful** | Add labels to clarify connection meaning |
| **Consistent styling** | Use same style for same connection type |

### Arrow Style by Diagram Type

#### Cloud Architecture / Infrastructure

| Connection Type | Color | Style | Arrow |
|-----------------|-------|-------|-------|
| HTTP/HTTPS/API | `#232F3E` | Solid | `endArrow=classic` |
| Database (SQL/NoSQL) | `#C925D1` | Solid | Bidirectional |
| Cache (Redis/Memcached) | `#DC382D` | Solid | Bidirectional |
| Message Queue (Async) | `#E7157B` | Dashed | `endArrow=classic` |
| Storage (S3/Blob) | `#7AA116` | Solid | `endArrow=classic` |
| Authentication | `#DD344C` | Solid | `endArrow=classic` |
| External API | `#232F3E` | Dashed | `endArrow=classic` |
| Analytics/ETL | `#8C4FFF` | Dashed | `endArrow=classic` |

#### C4 Model Diagrams

| Connection Type | Color | Style | Arrow |
|-----------------|-------|-------|-------|
| Uses/Calls | `#707070` | Solid | `endArrow=open` |
| Reads/Writes | `#707070` | Dashed | `endArrow=open` |
| Sends events | `#707070` | Dashed | `endArrow=async` |

#### Sequence Diagrams

| Connection Type | Color | Style | Arrow |
|-----------------|-------|-------|-------|
| Sync Request | `#232F3E` | Solid | `endArrow=classic` |
| Sync Response | `#232F3E` | Dashed | `endArrow=open` |
| Async Message | `#E7157B` | Solid | `endArrow=async` |
| Self-call | `#232F3E` | Solid | `endArrow=classic` |

#### ERD (Entity-Relationship)

| Relationship | Style | Arrow |
|--------------|-------|-------|
| One-to-One | Solid | `startArrow=ERone;endArrow=ERone` |
| One-to-Many | Solid | `startArrow=ERone;endArrow=ERmany` |
| Many-to-Many | Solid | `startArrow=ERmany;endArrow=ERmany` |
| Zero-or-One | Solid | `startArrow=ERzeroToOne;endArrow=...` |
| Zero-or-Many | Solid | `startArrow=ERzeroToMany;endArrow=...` |

#### Data Flow / ETL

| Connection Type | Color | Style | Arrow |
|-----------------|-------|-------|-------|
| Data extraction | `#7AA116` | Solid | `endArrow=classic` |
| Transformation | `#ED7100` | Solid | `endArrow=classic` |
| Load/Write | `#C925D1` | Solid | `endArrow=classic` |
| Stream/Real-time | `#E7157B` | Dashed | `endArrow=async` |

#### Flowchart / BPMN

| Connection Type | Color | Style | Arrow |
|-----------------|-------|-------|-------|
| Normal flow | `#232F3E` | Solid | `endArrow=classic` |
| Conditional (Yes/No) | `#232F3E` | Solid | `endArrow=classic` + label |
| Exception flow | `#DD344C` | Dashed | `endArrow=classic` |
| Message flow | `#E7157B` | Dashed | `endArrow=open` |

#### State Machine

| Connection Type | Color | Style | Arrow |
|-----------------|-------|-------|-------|
| Transition | `#232F3E` | Solid | `endArrow=classic` |
| Initial state | `#232F3E` | Solid | From filled circle |
| Final state | `#232F3E` | Solid | To bullseye |

---

## Arrow Templates

### Basic Connection
```xml
<mxCell id="conn-1" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#232F3E;strokeWidth=2;endArrow=classic;endFill=1;shadow=1;"
  parent="1" source="source-id" target="target-id" edge="1">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Labeled Connection
```xml
<mxCell id="conn-2" value="Label" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#232F3E;strokeWidth=2;endArrow=classic;endFill=1;shadow=1;fontSize=9;"
  parent="1" source="source-id" target="target-id" edge="1">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Bidirectional Connection
```xml
<mxCell id="conn-3" value="Read/Write" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#C925D1;strokeWidth=2;startArrow=classic;startFill=1;endArrow=classic;endFill=1;shadow=1;fontSize=9;"
  parent="1" source="source-id" target="target-id" edge="1">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Async/Dashed Connection
```xml
<mxCell id="conn-4" value="Event" style="edgeStyle=orthogonalEdgeStyle;rounded=1;html=1;strokeColor=#E7157B;strokeWidth=2;dashed=1;endArrow=classic;endFill=1;shadow=1;fontSize=9;"
  parent="1" source="source-id" target="target-id" edge="1">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### ERD Relationship
```xml
<mxCell id="rel-1" style="edgeStyle=entityRelationEdgeStyle;rounded=0;html=1;strokeColor=#232F3E;strokeWidth=2;startArrow=ERone;startFill=0;endArrow=ERmany;endFill=0;"
  parent="1" source="table-1" target="table-2" edge="1">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

---

## Required Connections by Diagram Type

### Cloud Architecture
| From | To | Required |
|------|-----|----------|
| Users | Edge services (CDN, LB, API GW) | ✓ |
| Edge | Application services | ✓ |
| Services | Databases | ✓ |
| Services | Cache | If applicable |
| Services | Message queues | If applicable |
| Services | External APIs | If applicable |

### C4 Model
| From | To | Required |
|------|-----|----------|
| Person | System | ✓ |
| System | System | ✓ |
| Container | Container | ✓ |
| Component | Component | ✓ |
| Component | External | ✓ |

### Sequence Diagram
| From | To | Required |
|------|-----|----------|
| Actor | First participant | ✓ |
| Participant | Participant | ✓ |
| Every request | Must have response | ✓ |

### ERD
| From | To | Required |
|------|-----|----------|
| Entity | Related entity | ✓ |
| All FKs | Referenced PKs | ✓ |

### Data Flow / ETL
| From | To | Required |
|------|-----|----------|
| Source | Extraction | ✓ |
| Extraction | Transformation | ✓ |
| Transformation | Load | ✓ |
| Load | Target | ✓ |

### Flowchart
| From | To | Required |
|------|-----|----------|
| Start | First step | ✓ |
| Every step | Next step | ✓ |
| Decision | Both branches | ✓ |
| Last step | End | ✓ |

---

## Legends (MANDATORY)

### Arrow Legend
**Required when using multiple arrow colors or styles.**

```xml
<mxCell id="arrow-legend" value="Arrow Legend" style="swimlane;startSize=0;strokeWidth=2;fillColor=#f5f5f5;strokeColor=#666666;fontSize=12;fontStyle=1;shadow=1;"
  parent="1" vertex="1">
  <mxGeometry x="40" y="800" width="400" height="150" as="geometry"/>
</mxCell>
```

### Component Legend
**Required for diagrams with color-coded components.**

```xml
<mxCell id="component-legend" value="Component Legend" style="swimlane;startSize=0;strokeWidth=2;fillColor=#f5f5f5;strokeColor=#666666;fontSize=12;fontStyle=1;shadow=1;"
  parent="1" vertex="1">
  <mxGeometry x="460" y="800" width="380" height="150" as="geometry"/>
</mxCell>
```

---

## Validation Checklist

### Universal Checks
| Check | Description |
|-------|-------------|
| ☐ | All positions/sizes are multiples of 10px |
| ☐ | Icons are at least 60px on shorter side |
| ☐ | Containers have 10px+ margins |
| ☐ | **All elements have connections** |
| ☐ | **No orphan/floating elements** |
| ☐ | Arrow colors are consistent |
| ☐ | Legends included (if using colors) |

### Architecture Diagram Checks
| Check | Description |
|-------|-------------|
| ☐ | Users connect to edge services |
| ☐ | Services connect to databases |
| ☐ | Async flows use dashed lines |
| ☐ | External integrations connected |

### Sequence Diagram Checks
| Check | Description |
|-------|-------------|
| ☐ | All participants have lifelines |
| ☐ | Requests have responses |
| ☐ | Messages are numbered/ordered |

### ERD Checks
| Check | Description |
|-------|-------------|
| ☐ | All tables have PK indicated |
| ☐ | FKs connect to referenced tables |
| ☐ | Cardinality shown on all relationships |

### Flowchart Checks
| Check | Description |
|-------|-------------|
| ☐ | Has start and end nodes |
| ☐ | Decision branches labeled (Yes/No) |
| ☐ | No dead-end paths |

---

## Key Principles

1. **Grid alignment** - All elements snap to 10px grid
2. **Minimum spacing** - Use at least the minimum values, more if needed
3. **Connections are mandatory** - A diagram without arrows is incomplete
4. **Consistent styling** - Same connection type = same color/style
5. **Include legends** - When using multiple colors or styles
6. **No orphans** - Every element must connect to something
