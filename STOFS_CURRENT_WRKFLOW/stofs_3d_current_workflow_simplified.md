```mermaid
flowchart TD
    A1["jstofs_3d_atl_prep.ecf"] --> B1["JSTOFS_3D_ATL_PREP"]
    B1 --> C1["exstofs_3d_atl_prep_processing.sh"]
    
    A2["jstofs_3d_atl_temp_salt_restart.ecf"] --> B2["JSTOFS_3D_ATL_TEMP_SALT_RESTART"]
    B2 --> C2["exstofs_3d_atl_temp_salt_restart.sh"]
    
    A3["jstofs_3d_atl_now_forecast.ecf"] --> B3["JSTOFS_3D_ATL_NOW_FORECAST"]
    B3 --> C3["exstofs_3d_atl_now_forecast.sh"]
    C3 --> D3["Run SCHISM model"]
    
    A4["jstofs_3d_atl_post1.ecf"] --> B4["JSTOFS_3D_ATL_POST_I"]
    B4 --> C4["exstofs_3d_atl_post_1.sh"]
    
    A5["jstofs_3d_atl_post2.ecf"] --> B5["JSTOFS_3D_ATL_POST_II"]
    B5 --> C5["exstofs_3d_atl_post_2.sh"]

    classDef ecfNode fill:#f9f,stroke:#333,stroke-width:2px;
    classDef jobNode fill:#ffa,stroke:#333,stroke-width:2px;
    classDef scriptNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef modelNode fill:#afa,stroke:#333,stroke-width:2px;

    class A1,A2,A3,A4,A5 ecfNode;
    class B1,B2,B3,B4,B5 jobNode;
    class C1,C2,C3,C4,C5 scriptNode;
    class D3 modelNode;