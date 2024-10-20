```mermaid
flowchart TD
    E["Post_Processing"] --> E1["Common_Post"]
    E --> E2{"System-Specific Post"}
    E2 --> E2a["STOFS3D_Post"]
    E2 --> E2b["STOFS2D_Global_Post"]
    
    E1 --> E1a["Generate_Station_Output"]
    E1 --> E1b["Create_NetCDF_Files"]
    E1 --> E1c["Generate_GRIB2_Files"]
    
    E2a --> E2a1["3D_Field_Processing"]
    E2a --> E2a2["SCHISM_Specific_Output"]
    
    E2b --> E2b1["2D_Field_Processing"]
    E2b --> E2b2["ADCIRC_Specific_Output"]

    classDef postNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef commonNode fill:#fea,stroke:#333,stroke-width:2px;
    classDef stofs3dNode fill:#fda,stroke:#333,stroke-width:2px;
    classDef stofs2dNode fill:#afd,stroke:#333,stroke-width:2px;

    class E,E2 postNode;
    class E1,E1a,E1b,E1c commonNode;
    class E2a,E2a1,E2a2 stofs3dNode;
    class E2b,E2b1,E2b2 stofs2dNode;