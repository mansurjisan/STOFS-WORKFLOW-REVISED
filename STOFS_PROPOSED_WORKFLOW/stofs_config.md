```mermaid
flowchart TD
    B["Configuration"] --> B1["Load_Common_Config"]
    B --> B2["Set_Common_Environment"]
    B --> B3{"Select System"}
    B3 --> B3a["STOFS3D_Config"]
    B3 --> B3b["STOFS2D_Global_Config"]

    classDef configNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef systemNode fill:#fea,stroke:#333,stroke-width:2px;

    class B configNode;
    class B1,B2,B3 configNode;
    class B3a,B3b systemNode;