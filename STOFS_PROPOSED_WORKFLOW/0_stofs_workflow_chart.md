```mermaid
flowchart LR
 subgraph Config["Configuration"]
    direction TB
        B1["Init"]
        B2["Setup Environment"]
        B3["Load Configuration"]
        B4["Validate Configuration"]
        B["Configuration"]
  end
 subgraph Prep["Preparation"]
    direction TB
        C1["Common Prep"]
        C2{"System-Specific Prep"}
        C2a["STOFS3D Prep"]
        C2b["STOFS2D Global Prep"]
        C3["Verify Prep"]
        C["Preparation"]
        C2a1["Prep Forcing"]
        C2a2["Prep Model Controls"]
        C2a3["Temp Salt Restart"]
        C2b1["Cold Start Prep"]
        C2b2["Spinup"]
        C2b3["Nowcast Prep"]
        C2b4["Forecast Prep"]
  end
 subgraph Model["Model Run"]
    direction TB
        D1["Allocate Resources"]
        D2{"Run Model"}
        D2a["Run STOFS3D (SCHISM)"]
        D2b["Run STOFS2D Global (ADCIRC)"]
        D3["Verify Model Run"]
        D["Model_Run"]
  end
 subgraph Post["Post Processing"]
    direction TB
        E1["Process Output"]
        E1a["common post-process"]
        E1a1["Generate_Station_Output"]
        E1a2["Create_NetCDF_Files"]
        E1a3["Generate_GRIB2_Files"]
        E1b{"system specific post-process"}
        E1b1["STOFS3D_Post"]
        E1b2["STOFS2D_Global_Post"]
        E2["Generate Products"]
        E3["Create Visualizations"]
        E4["Prepare Distribution"]
        E5["Verify Post"]
        E["Post_Processing"]
  end
    C --> D & C1 & C2 & C3
    A["STOFS_Main"] --> B
    B --> C & B1
    D --> E & D1
    B1 --> B2
    B2 --> B3
    B3 --> B4
    C2 --> C2a & C2b
    C2a --> C2a1 & C2a2 & C2a3
    C2b --> C2b1 & C2b2 & C2b3
    D2 --> D2a & D2b & D3
    D1 --> D2
    E --> E1 & F["Cleanup"]
    E1 --> E1a & E1b & E2
    E1a --> E1a1 & E1a2 & E1a3
    E1b --> E1b1 & E1b2
    E2 --> E3
    E3 --> E4
    E4 --> E5
    F --> G["Send Notifications"]

     B1:::commonNode
     B2:::commonNode
     B3:::commonNode
     B4:::commonNode
     B:::commonNode
     C1:::commonNode
     C2:::commonNode
     C2a:::decisionNode
     C2a:::stofs3dNode
     C2b:::stofs2dNode
     C3:::commonNode
     C:::commonNode
     C2a1:::decisionNode
     C2a1:::stofs3dNode
     C2a2:::stofs3dNode
     C2a3:::stofs3dNode
     C2b1:::stofs2dNode
     C2b2:::stofs2dNode
     C2b3:::stofs2dNode
     C2b4:::stofs2dNode
     D1:::commonNode
     D2:::commonNode
     D2a:::stofs3dNode
     D2b:::stofs2dNode
     D3:::commonNode
     D:::commonNode
     E1:::commonNode
     E1a:::stofs2dNode
     E1a:::commonNode
     E1a1:::commonNode
     E1a2:::stofs2dNode
     E1a2:::commonNode
     E1a3:::stofs2dNode
     E1a3:::commonNode
     E1b:::stofs3dNode
     E1b:::decisionNode
     E1b:::commonNode
     E1b1:::stofs3dNode
     E1b2:::stofs3dNode
     E1b2:::stofs2dNode
     E2:::commonNode
     E3:::commonNode
     E4:::commonNode
     E5:::commonNode
     E:::commonNode
     A:::mainNode
     F:::commonNode
     G:::commonNode
    classDef mainNode fill:#f9f,stroke:#333,stroke-width:4px
    classDef decisionNode fill:#fea, stroke:#333, stroke-width:2px
    classDef stofs3dNode fill:#fda, stroke:#333, stroke-width:2px
    classDef commonNode fill:#aef, stroke:#333, stroke-width:2px
    classDef stofs2dNode fill:#afd, stroke:#333, stroke-width:2px


