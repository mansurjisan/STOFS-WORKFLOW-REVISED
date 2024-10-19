```mermaid
flowchart TD
    A(["jstofs_3d_atl_now_forecast.ecf"]) -- Calls --> B(["JSTOFS_3D_ATL_NOW_FORECAST"])
    B -- Calls --> C(["exstofs_3d_atl_now_forecast.sh"])
    C -- Runs --> D(["SCHISM model"])
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px