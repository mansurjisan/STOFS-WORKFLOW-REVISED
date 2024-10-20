```mermaid
flowchart TD
 subgraph Config["Configuration"]
    direction TB
        B1["Init"]
        B2["Setup Environment"]
        B3{"Load Configuration"}
        B3a["STOFS3D_Config"]
        B3b["STOFS2D_Global_Config"]
        B4["Validate Configuration"]
        B["Configuration"]
  end
    B --> B1
    B1 --> B2
    B2 --> B3
    B3 --> B3a & B3b
    B3a --> B4
    B3b --> B4

     B1:::configNode
     B2:::configNode
     B3:::configNode
     B3a:::systemNode
     B3b:::systemNode
     B4:::configNode
     B:::configNode
    classDef configNode fill:#aef,stroke:#333,stroke-width:2px,font-family:Times
    classDef systemNode fill:#fea,stroke:#333,stroke-width:2px,font-family:Times
