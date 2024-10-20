```mermaid
flowchart LR
    A["STOFS_Main"] --> B["Configuration"]
    B --> C["Preparation"]
    C --> D["Model_Run"]
    D --> E["Post_Processing"]

    subgraph Config ["Configuration"]
        direction TB
        B1["Init"]
        B2["Setup Environment"]
        B3["Load Configuration"]
        B4["Validate Configuration"]
        B --> B1 --> B2 --> B3 --> B4
    end

    subgraph Prep ["Preparation"]
        direction TB
        C1["Fetch Input Data"]
        C2["Validate Input Data"]
        C3["Common Prep"]
        C4{"System-Specific Prep"}
        C4 --> C4a["STOFS3D Prep"]
        C4 --> C4b["STOFS2D Global Prep"]
        C5["Verify Prep"]
        C --> C1 --> C2 --> C3 --> C4 --> C5
    end

    subgraph Model ["Model Run"]
        direction TB
        D1["Allocate Resources"]
        D2{"Run Model"}
        D2 --> D2a["Run STOFS3D"]
        D2 --> D2b["Run STOFS2D Global"]
        D3["Verify Model Run"]
        D --> D1 --> D2 --> D3
    end

    subgraph Post ["Post Processing"]
        direction TB
        E1["Process Output"]
        E2["Generate Products"]
        E3["Create Visualizations"]
        E4["Prepare Distribution"]
        E5["Verify Post"]
        E --> E1 --> E2 --> E3 --> E4 --> E5
    end

    F["Cleanup"]
    G["Send Notifications"]

    E --> F --> G

    classDef mainNode fill:#f9f,stroke:#333,stroke-width:4px;
    classDef commonNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef decisionNode fill:#fea,stroke:#333,stroke-width:2px;
    classDef stofs3dNode fill:#fda,stroke:#333,stroke-width:2px;
    classDef stofs2dNode fill:#afd,stroke:#333,stroke-width:2px;

    class A mainNode;
    class B,C,D,E,B1,B2,B3,B4,C1,C2,C3,C5,D1,D3,E1,E2,E3,E4,E5,F,G commonNode;
    class C4,D2 decisionNode;
    class C4a,D2a stofs3dNode;
    class C4b,D2b stofs2dNode;
