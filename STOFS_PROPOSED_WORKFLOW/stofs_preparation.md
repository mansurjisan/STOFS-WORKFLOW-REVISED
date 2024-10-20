```mermaid
flowchart TD
    C["Preparation"] --> C1["Common_Prep"]
    C --> C2{"System-Specific Prep"}
    C2 --> C2a["STOFS3D_Prep"]
    C2 --> C2b["STOFS2D_Global_Prep"]
    
    C2a --> C2a1["Prep_Forcing"]
    C2a --> C2a2["Prep_Model_Controls"]
    C2a --> C2a3["Temp_Salt_Restart"]
    
    C2b --> C2b1["Cold_Start_Prep"]
    C2b --> C2b2["Spinup"]
    C2b --> C2b3["Nowcast_Prep"]
    C2b --> C2b4["Forecast_Prep"]

    classDef prepNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef stofs3dNode fill:#fea,stroke:#333,stroke-width:2px;
    classDef stofs2dNode fill:#afa,stroke:#333,stroke-width:2px;

    class C,C1,C2 prepNode;
    class C2a,C2a1,C2a2,C2a3 stofs3dNode;
    class C2b,C2b1,C2b2,C2b3,C2b4 stofs2dNode;