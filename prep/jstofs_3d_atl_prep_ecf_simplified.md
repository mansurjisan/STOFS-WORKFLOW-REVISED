```mermaid
flowchart TD
    A(["**jstofs_3d_atl_prep.ecf**"]) -- Calls --> B(["**JSTOFS_3D_ATL_PREP**"])
    B -- Calls --> C(["**exstofs_3d_atl_prep_processing.sh**"])
    C -- Prepares files --> D(["Forcing files and model controls"])

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
