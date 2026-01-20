# Partner Onboarding Workflow

```mermaid
flowchart TD
    Start([Start: Partner Onboarding]) --> Form[Fill Out Onboarding Request Form]

    Form --> Input1[Select Resource Type:<br/>• Partner<br/>• Resource<br/>• Project]
    Input1 --> Input2[Enter Details:<br/>• Partner Name<br/>• Project Name<br/>• Resource Name if applicable<br/>• Choose SME Requirement<br/>• Additional Details]

    Input2 --> Generate[Click: Generate Checklist]

    Generate --> Template[(Onboarding Checklist<br/>Template)]
    Template --> Decision{Resource<br/>Type?}

    Decision -->|Partner| PartnerChecklist[Generate Partner Checklist]
    Decision -->|Resource| ResourceChecklist[Generate Resource Checklist]
    Decision -->|Project| ProjectChecklist[Generate Project Checklist]

    PartnerChecklist --> Assign[Assign Dates &<br/>Assigned To Fields]
    ResourceChecklist --> Assign
    ProjectChecklist --> Assign

    Assign --> SME[(SME Role Catalog)]
    SME --> LinkSME[Link & Assign SMEs<br/>as Applicable]

    LinkSME --> Final[Onboarding Checklist Created]
    Final --> Notify[Assignees Receive Tasks]

    Notify --> Complete[Assignees Complete Tasks]
    Complete --> Update[(Automatically Updated<br/>in Airtable)]

    Update --> End([Complete])

    style Start fill:#e1f5e1
    style End fill:#e1f5e1
    style Form fill:#fff4e1
    style Generate fill:#ffd700,stroke:#333,stroke-width:3px
    style Template fill:#e1e5f5
    style SME fill:#e1e5f5
    style Update fill:#e1e5f5
    style Decision fill:#ffe1f5
    style Final fill:#d4edda,stroke:#28a745,stroke-width:2px
    style Notify fill:#e1f0ff
    style Complete fill:#fff4e1
```

## Workflow Overview

This diagram illustrates the partner onboarding process from initial request through checklist generation and SME assignment.

### Key Components:

1. **Onboarding Request Form** - Entry point where users input partner/resource/project details
2. **Onboarding Checklist Template** - Master template with three category types
3. **Dynamic Checklist Generation** - Creates specific checklists based on resource type
4. **SME Role Catalog** - Database linking subject matter experts to checklist items
5. **Final Checklist** - Completed onboarding checklist with dates and assignments

### Process Flow:

- User fills out request form with resource type, details, and SME requirements
- System generates appropriate checklist from template
- Dates and assignments are automatically populated
- SMEs are linked from the catalog as needed
- Onboarding checklist is created and assignees receive their tasks
- Assignees complete their tasks
- Task completion is automatically updated in Airtable
```
