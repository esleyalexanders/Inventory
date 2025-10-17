# Business Flow: Procurement & Outsourcing (Mermaid)

```mermaid
flowchart TD
    A[System identifies component/material shortage] --> B[Auto-generate RFQ/PO to vendor]
    B --> C[Send RFQ/PO via portal/email/API]
    C --> D[Vendor reviews and confirms lead time]
    D --> E{Lead time acceptable?}
    E -- No --> F[System flags for planner review]
    F --> G[Planner negotiates or finds alternate vendor]
    G --> B
    E -- Yes --> H[Vendor commits to delivery date]
    H --> I[System updates order plan]
    I --> J[System notifies relevant users]
    H --> K[Vendor ships components/materials]
    K --> L[System receives goods]
    L --> M[System triggers QC and inventory update]
    M --> N[System alerts if issues/delays]
```

---

## Key Automation Points
- RFQ/PO generation and sending is automatic
- Vendor lead time and delivery confirmation is tracked digitally
- System flags exceptions and supports alternate vendor selection
- Goods receipt, QC, and inventory update are automated
- Notifications and alerts for all relevant events
