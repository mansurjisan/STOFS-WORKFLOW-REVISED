

Old (Current) Structure                | New (Proposed) Structure
---------------------------------------|---------------------------------------
stofs/                                 | stofs/
├── ecf/                               | ├── ecf/
│   ├── 2d_glo/                        | │   ├── stofs_suite.def
│   │   ├── jstofs_2d_glo_*.ecf        | │   ├── init.ecf
│   └── 3d_atl/                        | │   ├── setup_environment.ecf
│       ├── jstofs_3d_atl_*.ecf        | │   ├── load_config.ecf
├── exec/                              | │   ├── validate_config.ecf
│   ├── stofs_2d_glo/                  | │   ├── fetch_input_data.ecf
│   │   ├── stofs_2d_glo_*             | │   ├── validate_input_data.ecf
│   └── stofs_3d_atl/                  | │   ├── common_prep.ecf
│       ├── stofs_3d_atl_*             | │   ├── stofs3d_prep.ecf
├── jobs/                              | │   ├── stofs2d_global_prep.ecf
│   ├── JSTOFS_2D_GLO_*                | │   ├── verify_prep.ecf
│   └── JSTOFS_3D_ATL_*                | │   ├── allocate_resources.ecf
├── lib/                               | │   ├── stofs3d_run.ecf
│   └── stofs_2d_glo/                  | │   ├── stofs2d_global_run.ecf
├── parm/                              | │   ├── verify_model_run.ecf
│   ├── stofs_2d_glo/                  | │   ├── process_output.ecf
│   └── stofs_3d_atl/                  | │   ├── generate_products.ecf
├── scripts/                           | │   ├── create_visualizations.ecf
│   ├── stofs_2d_glo/                  | │   ├── prepare_distribution.ecf
│   │   ├── exstofs_2d_glo_*.sh        | │   ├── verify_post.ecf
│   └── stofs_3d_atl/                  | │   ├── cleanup.ecf
│       ├── exstofs_3d_atl_*.sh        | │   └── send_notifications.ecf
├── sorc/                              | ├── scripts/
│   ├── stofs_2d_glo/                  | │   ├── common/
│   └── stofs_3d_atl/                  | │   │   ├── init.sh
├── ush/                               | │   │   ├── setup_environment.sh
│   ├── stofs_2d_glo/                  | │   │   ├── load_config.sh
│   │   ├── *.py, *.sh, *.tcl, *.pl    | │   │   └── ...
│   └── stofs_3d_atl/                  | │   ├── stofs3d/
│       ├── *.sh                       | │   │   ├── prep.sh
│       └── pysh/                      | │   │   ├── run.sh
│           ├── *.py                   | │   │   └── ...
└── versions/                          | │   └── stofs2d_global/
    ├── stofs_2d_glo/                  | │       ├── prep.sh
    └── stofs_3d_atl/                  | │       ├── run.sh
                                       | │       └── ...
                                       | ├── exec/
                                       | │   ├── stofs3d_model
                                       | │   └── stofs2d_global_model
                                       | ├── ush/
                                       | │   ├── common/
                                       | │   │   ├── utilities.py
                                       | │   │   ├── data_processing.py
                                       | │   │   ├── nco_wrappers.sh
                                       | │   │   ├── error_handling.sh
                                       | │   │   ├── logging.sh
                                       | │   │   └── data_validation.sh
                                       | │   ├── stofs3d/
                                       | │   │   ├── specific_3d_script.py
                                       | │   │   └── ...
                                       | │   └── stofs2d_global/
                                       | │       ├── specific_2d_script.py
                                       | │       └── ...
                                       | ├── parm/
                                       | ├── sorc/
                                       | ├── config/
                                       | │   ├── stofs3d_config.yaml
                                       | │   └── stofs2d_global_config.yaml
                                       | ├── fix/
                                       | ├── versions/
                                       | └── modulefiles/
