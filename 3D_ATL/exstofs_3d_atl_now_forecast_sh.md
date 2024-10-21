```mermaid
flowchart TD
    A(["Start exstofs_3d_atl_now_forecast.sh"])
    B["Initial Setup"]
    C["Copy Static Files"]
    D["Prepare Forcing Data"]
    E["Copy RTOFS Forcing"]
    F["Hot Restart Preparation"]
    G{"All input files\navailable?"}
    H["Run SCHISM Model"]
    I["Check Model Output"]
    J(["End"])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G -- Yes --> H
    G -- No --> J
    H --> I
    I --> J

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style G fill:#ffa,stroke:#333,stroke-width:2px
    style H fill:#bff,stroke:#333,stroke-width:2px
    style J fill:#f9f,stroke:#333,stroke-width:2px