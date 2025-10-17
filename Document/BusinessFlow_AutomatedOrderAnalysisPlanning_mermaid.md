# Business Flow: Automated Order Analysis & Planning (Mermaid)

```mermaid
flowchart TD
    A[Order received & validated] --> B[System checks BOM stock]
    B --> C{BOM stock sufficient?}
    C -- Yes --> D[Reserve BOM for order]
    D --> E[Trigger shipping/invoicing]
    C -- No --> F[System checks semi-finished stock]
    F --> G{Semi-finished stock sufficient?}
    G -- Yes --> H[Plan final assembly]
    H --> I[Trigger production work order]
    G -- No --> J[System checks component stock]
    J --> K{Can in-house make enough components on time?}
    K -- Yes --> L[Auto-generate in-house production plan]
    L --> M[Trigger production work order]
    K -- No --> N[System auto-suggests outsourcing]
    N --> O[Generate vendor RFQ/PO]
    O --> P[Vendor confirms lead time]
    P --> Q[System calculates material available date]
    Q --> R[System calculates delivery date]
    R --> S[Update order plan & notify users]
    M --> Q
    I --> Q
```

---

## Key Automation Points
- System checks all stock levels in real time
- Prioritizes in-house production; outsources only if needed
- Automatically generates work orders and vendor RFQs/POs
- Calculates material available and delivery dates
- Notifies users of plan, exceptions, and changes
