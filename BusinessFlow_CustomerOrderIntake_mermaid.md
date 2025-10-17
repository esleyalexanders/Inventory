# Business Flow: Customer Order Intake (Mermaid)

```mermaid
flowchart TD
    A[Customer submits PO portal/API/email] --> B[System receives PO]
    B --> C{PO data valid?}
    C -->|No| D[System notifies user: PO error]
    D --> E[User corrects PO and resubmits]
    E --> B
    C -->|Yes| F[System checks customer status]
    F --> G{Customer active & credit OK?}
    G -->|No| H[System flags for sales/finance review]
    H --> I[Sales/Finance approve or reject]
    I -->|Reject| J[System notifies customer: PO rejected]
    I -->|Approve| K[Continue order intake]
    G -->|Yes| K
    K --> L[System creates order record]
    L --> M[System triggers automated planning]
    M --> N[Order status: Intake complete]
    N --> O[Notify relevant users sales, planning, warehouse]

    classDef system fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef decision fill:#ffebee,stroke:#c62828,stroke-width:2px
    classDef manual fill:#fff3e0,stroke:#ef6c00,stroke-width:2px
    
    class A,B,D,E,F,H,I,J,L,M,N,O manual
    class C,G decision
```

---

## Key Automation Points
- PO validation is automatic (required fields, format, duplicates)
- Customer status and credit check are system-driven
- Exception handling for invalid PO or customer issues
- Order record creation and planning trigger are automated
- Notifications sent to all relevant roles
