```mermaid
flowchart TD
    A(["jstofs_2d_glo_gempak.ecf"]) -- Calls --> B(["JSTOFS_2D_GLO_GEMPAK"])
    B -- Calls --> C(["exstofs_2d_glo_gempak.sh"])
    C -- Copies --> D(["Copy GRIB2 forecast files"])
    C -- Converts --> E(["Convert GRIB2 to GEMPAK format using nagrib2"])
    C -- Processes --> F(["Generate GEMPAK grids for different regions"])
    C -- Sends --> G(["Send GEMPAK grids to directories"])
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    style E fill:#bff,stroke:#333,stroke-width:2px
    style F fill:#dff,stroke:#333,stroke-width:2px
    style G fill:#dfd,stroke:#333,stroke-width:2px
