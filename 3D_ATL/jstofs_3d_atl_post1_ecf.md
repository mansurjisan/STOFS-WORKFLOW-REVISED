```mermaid
flowchart TD
    A(["jstofs_3d_atl_post1.ecf"]) -- Sets up environment --> B(["JSTOFS_3D_ATL_POST_I"])
    B -- Prepares job structure --> C(["exstofs_3d_atl_post_1.sh"])
    C --> D["Check model completion"]
    D --> E["Add attributes to 2D/3D files"]
    E --> F["Create station output and SHEF files"]
    F --> G["Generate AWS/EC2 auto validation files"]
    G --> H["Create profile NetCDF files"]
    H --> I["Produce ADCIRC format water level fields"]
    I --> J["Create AWIPS GRIB2 files"]

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px