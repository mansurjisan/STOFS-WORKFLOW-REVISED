```mermaid
flowchart TD
    A(["**jstofs_3d_atl_prep.ecf**"]) -- Calls --> B(["**JSTOFS_3D_ATL_PREP**"])
    B -- Calls --> C(["**exstofs_3d_atl_prep_processing.sh**"])
    C -- Prepares files --> D(["Forcing files and model controls"])

    subgraph ""   
        C1(["stofs_3d_atl_create_param_nml.sh"]):::shStyle
        C2(["stofs_3d_atl_create_bctides_in.sh"]):::shStyle
        C3(["stofs_3d_atl_create_river_forcing_nwm.sh"]):::shStyle
        C4(["stofs_3d_atl_create_surface_forcing_gfs.sh"]):::shStyle
        C5(["stofs_3d_atl_create_surface_forcing_hrrr.sh"]):::shStyle
        C6(["stofs_3d_atl_create_river_st_lawrence.sh"]):::shStyle
        C7(["stofs_3d_atl_create_obc_3d_th.sh"]):::shStyle
        C8(["stofs_3d_atl_create_obc_nudge.sh"]):::shStyle
        C --> C1 & C2 & C3 & C4 & C5 & C6 & C7 & C8
    end

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ffa,stroke:#333,stroke-width:2px
    style C fill:#ffa,stroke:#333,stroke-width:2px
    style D fill:#bff,stroke:#333,stroke-width:2px
    classDef shStyle fill:#ffa,stroke:#333,stroke-width:2px,font-family:'Times New Roman',serif,font-weight:bold;
    classDef default font-family:'Times New Roman',serif,font-weight:bold;
