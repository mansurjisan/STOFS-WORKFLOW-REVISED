```mermaid
flowchart TD
    D["Model Run"] --> D1["Allocate Resources"]
    D1 --> D2{"Run Model"}
    D2 --> D2a["Run STOFS-3D (SCHISM)"] & D2b["Run STOFS-2D Global (ADCIRC)"]
    D2a --> D3["Verify Model Run"]
    D2b --> D3

     D:::modelNode
     D1:::modelRunNode
     D1:::modelNode
     D2:::modelRunNode
     D2:::modelNode
     D2a:::modelRunNode
     D2b:::modelRunNode
     D2b:::verifyNode
     D3:::modelNode
    classDef modelRunNode fill:#fea,stroke:#333,stroke-width:2px
    classDef verifyNode fill:#afa, stroke:#333, stroke-width:2px
    classDef modelNode fill:#aef, stroke:#333, stroke-width:2px
