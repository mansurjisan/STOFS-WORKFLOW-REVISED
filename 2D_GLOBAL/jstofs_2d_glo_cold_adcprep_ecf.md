```mermaid
flowchart TD
    A(["jstofs_2d_glo_cold_adcprep.ecf"]) -- Calls --> B(["JSTOFS_2D_GLO_COLD_ADCPREP"])
    B -- Calls --> C(["exstofs_2d_glo_cold_adcprep.sh"])
    C -- Calls --> D(["adcprep with partmesh"])
    C -- Calls --> E(["adcprep with prepall"])
    D -- Generates --> F(["Mesh and Grid Files"])
    E -- Prepares --> F
    F -- Packed into --> G(["Tarball for Model Input"])
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    style E fill:#bff,stroke:#333,stroke-width:2px
    style F fill:#dff,stroke:#333,stroke-width:2px
    style G fill:#dfd,stroke:#333,stroke-width:2px
