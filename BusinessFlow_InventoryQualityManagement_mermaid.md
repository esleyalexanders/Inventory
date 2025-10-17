# Business Flow: Inventory & Quality Management (Mermaid)

```mermaid
flowchart TD
    A[Goods received in-house or outsource] --> B[System logs receipt]
    B --> C[System triggers QC]
    C --> D{QC pass?}
    D -->|Yes| E[System updates inventory: available]
    D -->|No| F[System blocks non-conforming stock]
    F --> G[System alerts for non-conformance]
    E --> H[System checks for low stock]
    H --> I{Low stock?}
    I -->|Yes| J[System sends automated alert]
    I -->|No| K[No action needed]
    E --> L[System updates order/production status]

    classDef system fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef decision fill:#ffebee,stroke:#c62828,stroke-width:2px
    classDef automated fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    classDef alert fill:#fff3e0,stroke:#ef6c00,stroke-width:2px
    
    class A,B,C,E,F,H,L automated
    class D,I decision
    class G,J alert
    class K system
```

---

## Key Automation Points
- Goods receipt, QC, and inventory update are automated
- Non-conforming stock is blocked and alerts triggered
- Low stock alerts are automatic
- Order/production status updated in real time
