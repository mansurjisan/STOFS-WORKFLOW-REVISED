```mermaid
flowchart TD
    A(["jstofs_2d_glo_post_anomaly"]) -- Calls --> B(["JSTOFS_2D_GLO_POST_ANOMALY"])
    B -- Calls --> C(["exstofs_2d_glo_post_anomaly.sh"])
    C -- Copies --> D(["Copy output files from $COMIN"])
    C -- Generates --> E(["Compute anomalies for stations"])
    C -- Combines --> F(["Combine water level and anomaly for each station"])
    C -- Creates --> G(["Generate NetCDF file for combined data"])
    C -- Sends --> H(["Send output files to storage"])

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    style E fill:#bff,stroke:#333,stroke-width:2px
    style F fill:#dff,stroke:#333,stroke-width:2px
    style G fill:#dff,stroke:#333,stroke-width:2px
    style H fill:#dfd,stroke:#333,stroke-width:2px
