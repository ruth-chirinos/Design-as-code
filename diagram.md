subgraph "1. Capa de Presentación"
        direction LR
        A[Usuarios] -- Tráfico Web --> B{Balanceador de Carga}
        B -- Distribuye --> C[Servidor Web]
        B -- Distribuye --> D[Servidor Web]
        B -- Distribuye --> E[Servidor Web]
    end

    subgraph "2. Capa de Lógica de Negocio"
        direction LR
        C -- API Calls --> F[Servicio de Autenticación]
        D -- API Calls --> G[Servicio de Pago]
        E -- API Calls --> H[Servicio de Catálogo]
    end

    subgraph "3. Capa de Datos"
        direction LR
        F --> I(Base de Datos Relacional)
        G --> J(Base de Datos No Relacional)
        H --> J(Base de Datos No Relacional)
    end

    class A,B,C,D,E,F,G,H,I,J style fill:#f0f8ff,stroke:#1e90ff,stroke-width:2px,color:#333
    class A,C,D,E,F,G,H,I,J style stroke-dasharray: 5, 5
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#9bf,stroke:#333,stroke-width:2px
    style D fill:#9bf,stroke:#333,stroke-width:2px
    style E fill:#9bf,stroke:#333,stroke-width:2px
    style F fill:#bbf,stroke:#333,stroke-width:2px
    style G fill:#bbf,stroke:#333,stroke-width:2px
    style H fill:#bbf,stroke:#333,stroke-width:2px
    style I fill:#f9f,stroke:#333,stroke-width:2px
    style J fill:#f9f,stroke:#333,stroke-width:2px
