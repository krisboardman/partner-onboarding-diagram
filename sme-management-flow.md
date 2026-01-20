# SME Management Workflow

```mermaid
flowchart TD
    Start([Start: SME Management]) --> Assign[SME Assigned to Project]

    Assign --> SMEPath[SME Activities]
    Assign --> PartnerPath[Partner Resource Activities]

    %% SME Path
    SMEPath --> SMEForm[SME Fills Out<br/>Weekly Evaluation Form]
    SMEForm --> UpdateTracker[(SME Tracker in Airtable<br/>Automatically Updated)]
    UpdateTracker --> SMEComplete[Analysis Available]

    %% Partner Resource Path
    PartnerPath --> RequestForm[Partner Resource<br/>Submits Request Form]
    RequestForm --> FillDetails[Fill Out:<br/>• Priority<br/>• Request Details]

    FillDetails --> Email[Automated Email<br/>Sent to SME]
    Email --> LogDB[(Log Request<br/>in Database)]

    LogDB --> PartnerComplete[Analysis Available]

    PartnerComplete --> End([Complete])
    SMEComplete --> End

    %% Styling
    style Start fill:#e1f5e1
    style End fill:#e1f5e1
    style Assign fill:#d4edda,stroke:#28a745,stroke-width:2px
    style SMEForm fill:#fff4e1
    style RequestForm fill:#fff4e1
    style FillDetails fill:#fff4e1
    style UpdateTracker fill:#e1e5f5
    style LogDB fill:#e1e5f5
    style Email fill:#ffe1e1
    style SMEComplete fill:#d4edda,stroke:#28a745,stroke-width:2px
    style PartnerComplete fill:#d4edda,stroke:#28a745,stroke-width:2px
    style SMEPath fill:#f0f8ff,stroke:#4682b4,stroke-width:2px
    style PartnerPath fill:#fff8f0,stroke:#ff8c42,stroke-width:2px
```

## Workflow Overview

This diagram illustrates the SME (Subject Matter Expert) management process, showing both weekly SME evaluations and partner resource request handling.

### Key Components:

1. **SME Assignment** - SME is assigned to a project as the starting point
2. **SME Tracker (Airtable)** - Automatically updated database tracking all SME activities
3. **Request Database** - Logs all partner resource requests for tracking
4. **Automated Email System** - Sends notifications to SMEs for incoming requests
5. **Analysis Available** - Both workflows conclude with analysis ready for review

### Two Primary Workflows:

#### SME Weekly Evaluation (Blue Path):
- SME completes weekly evaluation form
- Form data automatically updates SME Tracker in Airtable
- Analysis becomes available for review and reporting

#### Partner Resource Requests (Orange Path):
- Partner resource submits request form
- Priority and request details are captured
- Automated email is sent to assigned SME
- Request is logged in database for tracking
- Analysis becomes available for review

### Benefits:
- **Automated tracking** - Weekly evaluations sync automatically to Airtable
- **Instant notifications** - SMEs receive automated emails immediately
- **Complete audit trail** - Every request is logged with priority
- **Analysis ready** - Both paths provide data for analysis and reporting
```
