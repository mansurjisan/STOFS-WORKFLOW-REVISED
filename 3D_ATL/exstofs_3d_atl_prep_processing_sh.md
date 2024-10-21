```mermaid
flowchart TD
    C(["**exstofs_3d_atl_prep_processing.sh**"]) -- Calls --> C1(["stofs_3d_atl_create_param_nml.sh"]) & C2(["stofs_3d_atl_create_bctides_in.sh"]) & C3(["stofs_3d_atl_create_river_forcing_nwm.sh"]) & C4(["stofs_3d_atl_create_surface_forcing_gfs.sh"]) & C5(["stofs_3d_atl_create_surface_forcing_hrrr.sh"]) & C6(["stofs_3d_atl_create_river_st_lawrence.sh"]) & C7(["stofs_3d_atl_create_obc_3d_th.sh"]) & C8(["stofs_3d_atl_create_obc_nudge.sh"])

     C1:::shStyle
     C2:::shStyle
     C3:::shStyle
     C4:::shStyle
     C5:::shStyle
     C6:::shStyle
     C7:::shStyle
     C8:::shStyle
    classDef shStyle fill:#ffa,stroke:#333,stroke-width:2px,font-family:'Times New Roman',serif,font-weight:bold
    classDef default font-family:'Times New Roman',serif,font-weight:bold
