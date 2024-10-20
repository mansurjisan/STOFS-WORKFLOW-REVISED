```mermaid
flowchart TD
    D["Model_Run"] --> D1{"Run Model"}
    D1 --> D1a["Run_SCHISM_3D"]
    D1 --> D1b["Run_ADCIRC_2D"]

    classDef runNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef modelNode fill:#fea,stroke:#333,stroke-width:2px;

    class D,D1 runNode;
    class D1a,D1b modelNode;