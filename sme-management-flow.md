# SME Management Workflow

```mermaid
flowchart TD
    Start([Start: SME Management]) --> Assign[SME Assigned to Project]

    Assign --> SMEPath[SME Activities]
    Assign --> PartnerPath[Partner Resource Activities]

    %% SME Path
    SMEPath --> SMEForm[SME Fills Out Form]
    SMEForm --> UpdateTracker[(Update SME Tracker<br/>in Airtable)]
    UpdateTracker --> SMEComplete[Information Updated]

    %% Partner Resource Path
    PartnerPath --> RequestForm[Partner Resource<br/>Submits Request Form]
    RequestForm --> RequestType{Request<br/>Type}

    RequestType -->|General Request| ProcessRequest[Process Request]
    RequestType -->|Specific Ask| ProcessRequest

    ProcessRequest --> Email[Send Email<br/>to SME]
    ProcessRequest --> LogDB[(Log Request<br/>in Database)]

    Email --> Notify[SME Notified]
    LogDB --> Track[Request Tracked]

    Notify --> End([Complete])
    Track --> End
    SMEComplete --> End

    %% Styling
    style Start fill:#e1f5e1
    style End fill:#e1f5e1
    style Assign fill:#d4edda,stroke:#28a745,stroke-width:2px
    style SMEForm fill:#fff4e1
    style RequestForm fill:#fff4e1
    style UpdateTracker fill:#e1e5f5
    style LogDB fill:#e1e5f5
    style Email fill:#ffe1e1
    style RequestType fill:#ffe1f5
    style SMEPath fill:#f0f8ff,stroke:#4682b4,stroke-width:2px
    style PartnerPath fill:#fff8f0,stroke:#ff8c42,stroke-width:2px
```

## Workflow Overview

This diagram illustrates the SME (Subject Matter Expert) management process, showing both SME self-service updates and partner resource request handling.

### Key Components:

1. **SME Assignment** - SME is assigned to a project as the starting point
2. **SME Tracker (Airtable)** - Central database tracking all SME information and activities
3. **Request Database** - Logs all partner resource requests for tracking and analytics
4. **Email Notification System** - Automatically notifies SMEs of incoming requests

### Two Primary Workflows:

#### SME Self-Service (Blue Path):
- SME fills out form with updates
- Information automatically syncs to Airtable SME Tracker
- Keeps SME information current and accessible

#### Partner Resource Requests (Orange Path):
- Partner resource submits request form
- System sends email notification to assigned SME
- Request is logged in database for tracking
- Creates audit trail of all SME interactions

### Benefits:
- **Centralized tracking** - All SME activities in one place
- **Automated notifications** - SMEs receive requests immediately
- **Complete audit trail** - Every request is logged and trackable
- **Self-service updates** - SMEs can update their own information
```
