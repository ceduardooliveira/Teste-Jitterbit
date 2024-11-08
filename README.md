# Teste-Jitterbit

``` mermaid
flowchart TD
    A[Customer Browses Product Catalog] --> B[Customer Selects Product]
    B --> C[Customer Adds Product to Cart]
    C --> D[Customer Reviews Cart]
    D --> E[Customer Proceeds to Checkout]
    E --> F[Customer Enters Shipping Information]
    F --> G[Customer Chooses Payment Method]
    G --> H[Order Summary & Review]
    H --> I[Customer Confirms Order]
    I --> J[Payment Authorization]
    J --> K{Payment Success?}
    K -->|Yes| L[Order Confirmation]
    K -->|No| M[Payment Failed]
    L --> N[Order Preparation]
    N --> O[Shipping/Delivery]
    O --> P[Delivery Confirmation]
    P --> Q[Post-Delivery Support]
    
    %% Styling for decision node
    class K decision;
    class M error;
    
    %% Styling nodes
    class A,B,C,D,E,F,G,H,I,J,L,N,O,P,Q fill:#E0F7FA,stroke:#00796B,stroke-width:2px;
    class K fill:#FFF3E0,stroke:#FF7043,stroke-width:2px;
    class M fill:#FFEBEE,stroke:#F44336,stroke-width:2px;


```
