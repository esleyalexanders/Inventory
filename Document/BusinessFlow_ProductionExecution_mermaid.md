# Business Flow: Production Execution (Mermaid)

```mermaid
flowchart TD
    A[System triggers production work order] --> B{Production type?}
    B -->|In-house| C[System generates in-house work order]
    C --> D[Material picking auto-generated]
    D --> E[Production progress tracked in system]
    E --> F[QC checkpoints auto-triggered]
    F --> G{QC pass?}
    G -->|Yes| H[Update inventory: finished/semi-finished]
    G -->|No| I[System flags for rework/non-conformance]
    B -->|Outsource| J[System generates outsource work order]
    J --> K[Send work order to vendor portal/API]
    K --> L[Vendor updates status/progress]
    L --> M[Vendor delivers goods]
    M --> N[System triggers QC and inventory update]
    N --> O{QC pass?}
    O -->|Yes| P[Update inventory: finished/semi-finished]
    O -->|No| Q[System flags for rework/non-conformance]

    classDef system fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef decision fill:#ffebee,stroke:#c62828,stroke-width:2px
    classDef automated fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    
    class A,C,D,E,F,H,I,J,K,L,M,N,P,Q automated
    class B,G,O decision
```

---

## Key Automation Points
- Work orders, material picking, and QC are system-driven
- Vendor collaboration and status updates are digital
- Inventory and QC updates are automated
- Exception handling for rework/non-conformance
