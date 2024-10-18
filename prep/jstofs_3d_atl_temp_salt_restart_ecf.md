```mermaid
flowchart TD
    A(["**jstofs_3d_atl_temp_salt_restart.ecf**"]) -- Calls --> B(["**JSTOFS_3D_ATL_TEMP_SALT_RESTART**"])
    B -- Calls --> C(["**exstofs_3d_atl_temp_salt_restart.sh**"])
    C -- Checks date --> D{"**Special restart condition?**"}
    D -- Yes --> E([**stofs_3d_atl_create_restart_combine_rtofs_stofs.sh**])
    D -- No --> F([**Continue normal processing**])

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    style E fill:#ffa,stroke:#333,stroke-width:2px
    style F fill:#aaf,stroke:#333,stroke-width:2px
