```mermaid
flowchart TD
    A(["jstofs_2d_glo_post_ncdiff.ecf"]) -- Calls --> B(["JSTOFS_2D_GLO_POST_NCDIFF"])
    B -- Calls --> C(["exstofs_2d_glo_post_ncdiff.sh"])
    C -- Copies --> D(["Copy NetCDF output files"])
    C -- Computes --> E(["Compute sub-tidal water level using ncdiff"])
    C -- Adds --> F(["Add geographic coordinates"])
    C -- Sends --> G(["Send NetCDF files to directories"])
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    style E fill:#bff,stroke:#333,stroke-width:2px
    style F fill:#dff,stroke:#333,stroke-width:2px
    style G fill:#dfd,stroke:#333,stroke-width:2px
