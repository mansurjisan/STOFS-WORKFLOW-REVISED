```mermaid
flowchart LR
    A["STOFS_Main"] --> B["Configuration"]
    B --> C["Preparation"]
    C --> D["Model_Run"]
    D --> E["Post_Processing"]

    subgraph Config ["Configuration"]
        direction TB
        B1["Load_Common_Config"]
        B2["Set_Common_Environment"]
        B3{"Select System"}
        B3 --> B3a["STOFS3D_Config"]
        B3 --> B3b["STOFS2D_Global_Config"]
        B --> B1 --> B2 --> B3
    end

    subgraph Prep ["Preparation"]
        direction TB
        C1["Common_Prep"]
        C2{"System-Specific Prep"}
        C2 --> C2a["STOFS3D_Prep"]
        C2 --> C2b["STOFS2D_Global_Prep"]
        C2a --> C2a1["Prep_Forcing"]
        C2a --> C2a2["Prep_Model_Controls"]
        C2a --> C2a3["Temp_Salt_Restart"]
        C2b --> C2b1["Cold_Start_Prep"]
        C2b --> C2b2["Spinup"]
        C2b --> C2b3["Nowcast_Prep"]
        C2b --> C2b4["Forecast_Prep"]
        C --> C1 --> C2
    end

    subgraph Model ["Model_Run"]
        direction TB
        D1{"Run Model"}
        D1 --> D1a["Run_SCHISM_3D"]
        D1 --> D1b["Run_ADCIRC_2D"]
        D --> D1
    end

    subgraph Post ["Post_Processing"]
        direction TB
        E1["Common_Post"]
        E2{"System-Specific Post"}
        E2 --> E2a["STOFS3D_Post"]
        E2 --> E2b["STOFS2D_Global_Post"]
        E1 --> E1a["Generate_Station_Output"]
        E1 --> E1b["Create_NetCDF_Files"]
        E1 --> E1c["Generate_GRIB2_Files"]
        E2a --> E2a1["3D_Field_Processing"]
        E2a --> E2a2["SCHISM_Specific_Output"]
        E2b --> E2b1["2D_Field_Processing"]
        E2b --> E2b2["ADCIRC_Specific_Output"]
        E --> E1
        E --> E2
    end

    classDef mainNode fill:#f9f,stroke:#333,stroke-width:4px;
    classDef commonNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef decisionNode fill:#fea,stroke:#333,stroke-width:2px;
    classDef stofs3dNode fill:#fda,stroke:#333,stroke-width:2px;
    classDef stofs2dNode fill:#afd,stroke:#333,stroke-width:2px;

    class A mainNode;
    class B,C,D,E,B1,B2,C1,E1,E1a,E1b,E1c commonNode;
    class B3,C2,D1,E2 decisionNode;
    class B3a,C2a,C2a1,C2a2,C2a3,D1a,E2a,E2a1,E2a2 stofs3dNode;
    class B3b,C2b,C2b1,C2b2,C2b3,C2b4,D1b,E2b,E2b1,E2b2 stofs2dNode;