```mermaid
flowchart TD
    E["Post_Processing"] --> E1["Process Output"]
    E1 --> E1a["common post-process"] & E1b{"system specific post-process"}
    E1a --> E2["Generate Products"] & E1a1["Generate_Station_Output"] & E1a2["Create_NetCDF_Files"] & E1a3["Generate_GRIB2_Files"]
    E1b --> E2 & E1b1["STOFS3D_Post"] & E1b2["STOFS2D_Global_Post"]
    E2 --> E3["Create Visualizations"]
    E3 --> E4["Prepare Distribution"]
    E4 --> E5["Verify Post"]

     E:::commonNode
     E1:::commonNode
     E1a:::stofs2dNode
     E1a:::commonNode
     E1b:::stofs3dNode
     E2:::commonNode
     E1a1:::commonNode
     E1a2:::stofs2dNode
     E1a2:::commonNode
     E1a3:::stofs2dNode
     E1a3:::commonNode
     E1b1:::stofs3dNode
     E1b2:::stofs3dNode
     E1b2:::stofs2dNode
     E3:::commonNode
     E4:::commonNode
     E5:::commonNode
    classDef mainNode fill:#f9f,stroke:#333,stroke-width:4px
    classDef decisionNode fill:#fea,stroke:#333,stroke-width:2px
    classDef commonNode fill:#aef, stroke:#333, stroke-width:2px
    classDef stofs3dNode fill:#fda, stroke:#333, stroke-width:2px
    classDef stofs2dNode fill:#afd, stroke:#333, stroke-width:2px


