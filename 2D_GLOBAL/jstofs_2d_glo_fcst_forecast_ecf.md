```mermaid
flowchart TD
    A(["jstofs_2d_glo_fcst_forecast.ecf"]) -- Calls --> B(["JSTOFS_2D_GLO_FCST_FORECAST"])
    B -- Calls --> C(["exstofs_2d_glo_fcst_forecast.sh"])
    C -- Calls --> D(["adcprep for partmesh"])
    C -- Calls --> E(["adcprep for prepall"])
    C -- Calls --> F(["padcirc for surface forcing forecast"])
    D -- Generates --> G(["Mesh and Grid Files"])
    E -- Prepares --> G
    F -- Runs --> H(["Surface Forcing Forecast Simulation"])
    G -- Packed into --> I(["Tarball for Model Input"])
    H -- Outputs --> J(["Forecast Files and Surface Forcing"])
    
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
