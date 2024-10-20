```mermaid
flowchart TD
    C2a["STOFS3D Prep"] --> C2a1["Prep Forcing"] & C2a2["Prep Model Controls"] & C2a3["Temp Salt Restart"]
    C2b["STOFS2D Global Prep"] --> C2b1["Cold Start Prep"] & C2b2["Spinup"] & C2b3["Nowcast Prep"] & C2b4["Forecast Prep"]
    C["Preparation"] --> C1["Common Prep"] & C2{"System-Specific Prep"}
    C2 --> C2a & C2b
    C1 --> C3["Verify Prep"]
    C2 --> C3["Verify Prep"]

    C2a:::stofs3dNode
    C2a1:::stofs3dNode
    C2a2:::stofs3dNode
    C2a3:::stofs3dNode
    C2b:::stofs2dNode
    C2b1:::stofs2dNode
    C2b2:::stofs2dNode
    C2b3:::stofs2dNode
    C2b4:::stofs2dNode
    C:::prepNode
    C1:::prepNode
    C2:::prepNode
    C3:::prepNode

    classDef prepNode fill:#aef,stroke:#333,stroke-width:2px
    classDef stofs3dNode fill:#fea,stroke:#333,stroke-width:2px
    classDef stofs2dNode fill:#afa, stroke:#333, stroke-width:2px
    class E2a,E2a1,E2a2 stofs3dNode;
    class E2b,E2b1,E2b2 stofs2dNode;
