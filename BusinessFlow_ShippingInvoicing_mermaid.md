# Business Flow: Shipping & Invoicing (Mermaid)

```mermaid
flowchart TD
    A[Order ready for shipment] --> B[System generates pick/pack list]
    B --> C[Warehouse picks and packs goods]
    C --> D[System generates shipping docs]
    D --> E[Goods shipped]
    E --> F[System triggers invoice]
    F --> G[Customer notified with tracking]
    E --> H[System updates delivery status]
    H --> I{Delivery confirmed?}
    I -- Yes --> J[System closes order]
    I -- No --> K[System monitors for issues]
```

---

## Key Automation Points
- Pick/pack lists and shipping docs are system-generated
- Invoice triggered automatically on shipment/delivery
- Customer notification and delivery status tracking are automated
- Exception handling for delivery issues
