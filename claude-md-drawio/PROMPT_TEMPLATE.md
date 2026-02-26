# Diagram Generation Prompt Template

## Full Application Analysis & Diagram Generation

```
Use diagram standards from: [CLAUDE_DIAGRAMS_STANDARD_FORMAT]

Analyze and generate a comprehensive architecture diagram for the following project.

## Scope of Analysis

Perform a complete codebase analysis and create an all-in-one diagram covering:

### 1. Architecture Overview
- Application layers and structure
- Technology stack identification
- Design patterns used (MVC, MVVM, Clean Architecture, etc.)

### 2. User Integration
- Entry points (UI, API, CLI)
- User interactions and workflows
- Input validation and processing

### 3. Data Workflow
- Data flow from input to output
- In-memory processing (RAM/state management)
- Persistence flow (storage/database/files)
- Data transformations at each layer

### 4. Data Models & Relationships
- All entities/models with properties
- Relationships (1:1, 1:N, M:N)
- Data types and constraints

### 5. Service Integration
- Internal services and their responsibilities
- External/third-party integrations (APIs, SDKs)
- Authentication and authorization flow

### 6. Storage & Persistence
- Database connections and queries
- File system operations
- Cache layers
- Configuration storage

## Requirements

- Analyze ALL files and components (do not skip anything)
- Include services and integrations I may not be aware of
- Show the complete data lifecycle from user input to final storage
- Use swimlane format for data models
- Follow all CLAUDE.md standards (shadows, colors, arrows)

## Output

Save diagram to: [YOUR_PROJECT_PATH]/docs/architecture-overview.drawio

---

Project: [YOUR_PROJECT_PATH]
```

---

## Example Usage

```
Use diagram standards from:  [CLAUDE_DIAGRAMS_STANDARD_FORMAT]

Analyze and generate a comprehensive architecture diagram for the following project.

## Scope of Analysis

Perform a complete codebase analysis and create an all-in-one diagram covering:

### 1. Architecture Overview
- Application layers and structure
- Technology stack identification
- Design patterns used (MVC, MVVM, Clean Architecture, etc.)

### 2. User Integration
- Entry points (UI, API, CLI)
- User interactions and workflows
- Input validation and processing

### 3. Data Workflow
- Data flow from input to output
- In-memory processing (RAM/state management)
- Persistence flow (storage/database/files)
- Data transformations at each layer

### 4. Data Models & Relationships
- All entities/models with properties
- Relationships (1:1, 1:N, M:N)
- Data types and constraints

### 5. Service Integration
- Internal services and their responsibilities
- External/third-party integrations (APIs, SDKs)
- Authentication and authorization flow

### 6. Storage & Persistence
- Database connections and queries
- File system operations
- Cache layers
- Configuration storage

## Requirements

- Analyze ALL files and components (do not skip anything)
- Include services and integrations I may not be aware of
- Show the complete data lifecycle from user input to final storage
- Use swimlane format for data models
- Follow all CLAUDE.md standards (shadows, colors, arrows)

## Output

Save diagram to:  [YOUR_PROJECT_PATH]\docs\architecture-overview.drawio


## Parameters:
- CLAUDE_DIAGRAMS_STANDARD_FORMAT:
- YOUR_PROJECT_PATH:
- YOUR_OUT_PUT_DIAGRAM_PROJECT_PATH:
```
