```mermaid
flowchart TD
    A["STOFS_Main"] --> B["Configuration"]
    A --> C["Preparation"]
    A --> D["Model_Run"]
    A --> E["Post_Processing"]

    classDef mainNode fill:#f9f,stroke:#333,stroke-width:2px;
    classDef subNode fill:#aef,stroke:#333,stroke-width:2px;

    class A mainNode;
    class B,C,D,E subNode;