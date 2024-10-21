```mermaid
flowchart TD
    A(["jstofs_3d_atl_post2.ecf"]) -- Sets up environment --> B(["JSTOFS_3D_ATL_POST_II"])
    B -- Prepares job structure --> C(["exstofs_3d_atl_post_2.sh"])
    C --> D["Check model completion"]
    D --> E["Merge hotstart files"]
    E --> F["Create 2D field files (10 parallel processes)"]
    F --> G["Create GeoPackage files"]

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px