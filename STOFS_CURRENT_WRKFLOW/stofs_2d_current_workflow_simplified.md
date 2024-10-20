```mermaid
flowchart TD
    A1["jstofs_2d_glo_cold_adcprep.ecf"] --> B1["JSTOFS_2D_GLO_COLD_ADCPREP"]
    B1 --> C1["exstofs_2d_glo_cold_adcprep.sh"]
    
    A2["jstofs_2d_glo_cold_spinup.ecf"] --> B2["JSTOFS_2D_GLO_COLD_SPINUP"]
    B2 --> C2["exstofs_2d_glo_cold_spinup.sh"]
    
    A3["jstofs_2d_glo_prep_nowcast.ecf"] --> B3["JSTOFS_2D_GLO_PREP_NOWCAST"]
    B3 --> C3["exstofs_2d_glo_prep_nowcast.sh"]
    
    A4["jstofs_2d_glo_prep_forecast.ecf"] --> B4["JSTOFS_2D_GLO_PREP_FORECAST"]
    B4 --> C4["exstofs_2d_glo_prep_forecast.sh"]
    
    A5["jstofs_2d_glo_fcst_nowcast.ecf"] --> B5["JSTOFS_2D_GLO_FCST_NOWCAST"]
    B5 --> C5["exstofs_2d_glo_fcst_nowcast.sh"]
    C5 --> D5["Run ADCIRC for nowcast"]
    
    A6["jstofs_2d_glo_fcst_forecast.ecf"] --> B6["JSTOFS_2D_GLO_FCST_FORECAST"]
    B6 --> C6["exstofs_2d_glo_fcst_forecast.sh"]
    C6 --> D6["Run ADCIRC for forecast"]
    
    A7["jstofs_2d_glo_post_anomaly.ecf"] --> B7["JSTOFS_2D_GLO_POST_ANOMALY"]
    B7 --> C7["exstofs_2d_glo_post_anomaly.sh"]
    
    A8["jstofs_2d_glo_post_ncdiff.ecf"] --> B8["JSTOFS_2D_GLO_POST_NCDIFF"]
    B8 --> C8["exstofs_2d_glo_post_ncdiff.sh"]
    
    A9["jstofs_2d_glo_post_grib2.ecf"] --> B9["JSTOFS_2D_GLO_POST_GRIB2"]
    B9 --> C9["exstofs_2d_glo_post_grib2.sh"]
    
    A10["jstofs_2d_glo_gempak.ecf"] --> B10["JSTOFS_2D_GLO_GEMPAK"]
    B10 --> C10["exstofs_2d_glo_gempak.sh"]

    classDef ecfNode fill:#f9f,stroke:#333,stroke-width:2px;
    classDef jobNode fill:#ffa,stroke:#333,stroke-width:2px;
    classDef scriptNode fill:#aef,stroke:#333,stroke-width:2px;
    classDef modelNode fill:#afa,stroke:#333,stroke-width:2px;

    class A1,A2,A3,A4,A5,A6,A7,A8,A9,A10 ecfNode;
    class B1,B2,B3,B4,B5,B6,B7,B8,B9,B10 jobNode;
    class C1,C2,C3,C4,C5,C6,C7,C8,C9,C10 scriptNode;
    class D5,D6 modelNode;