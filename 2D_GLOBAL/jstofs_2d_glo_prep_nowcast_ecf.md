```mermaid
flowchart TD
    A(["jstofs_2d_glo_prep_nowcast.ecf"]) -- Calls --> B(["JSTOFS_2D_GLO_PREP_NOWCAST"])
    B -- Calls --> C(["exstofs_2d_glo_prep_nowcast.sh"])
    C -- Calls --> D(["adcprep for partmesh"])
    C -- Calls --> E(["adcprep for prepall"])
    C -- Calls --> F(["padcirc for tide-only nowcast"])
    D -- Generates --> G(["Mesh and Grid Files"])
    E -- Prepares --> G
    F -- Runs --> H(["Tide-Only Nowcast Simulation"])
    G -- Packed into --> I(["Tarball for Model Input"])
    H -- Outputs --> J(["Hotstart and Nowcast Files"])
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    style E fill:#bff,stroke:#333,stroke-width:2px
    style F fill:#bff,stroke:#333,stroke-width:2px
    style G fill:#dff,stroke:#333,stroke-width:2px
    style H fill:#dff,stroke:#333,stroke-width:2px
    style I fill:#dfd,stroke:#333,stroke-width:2px
    style J fill:#dfd,stroke:#333,stroke-width:2px
