```mermaid
flowchart TD
    A(["jstofs_2d_glo_post_grib2.ecf"]) -- Calls --> B(["JSTOFS_2D_GLO_POST_GRIB2"])
    B -- Calls --> C(["exstofs_2d_glo_post_grib2.sh"])
    C -- Copies --> D(["Copy NetCDF output files"])
    C -- Converts --> E(["Convert NetCDF to SHEF format"])
    C -- Converts --> F(["Convert NetCDF to GRIB2 format"])
    C -- Sends --> G(["Send SHEF/GRIB2 files to directories"])
    C -- Distributes --> H(["Distribute files to AWIPS/WMO"])
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    style E fill:#bff,stroke:#333,stroke-width:2px
    style F fill:#dff,stroke:#333,stroke-width:2px
    style G fill:#dff,stroke:#333,stroke-width:2px
    style H fill:#dfd,stroke:#333,stroke-width:2px
