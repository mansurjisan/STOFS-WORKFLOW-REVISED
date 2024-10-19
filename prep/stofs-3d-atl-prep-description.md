# STOFS 3D Atlantic Preprocessing Workflow

## Overview

The preprocessing stage for the STOFS 3D Atlantic model involves a series of scripts that prepare the necessary input files and configurations for the model run. The main preprocessing script coordinates several sub-scripts, each responsible for generating specific components of the model input.

## Main Preprocessing Script

The core of the preprocessing workflow is handled by `exstofs_3d_atl_prep_processing.sh`. This script orchestrates the entire preprocessing procedure by calling various sub-scripts and managing their outputs.

## Preprocessing Steps

The `exstofs_3d_atl_prep_processing.sh` script performs the following key operations:

1. **Namelist File Creation**: Calls `stofs_3d_atl_create_param_nml.sh` to generate `param.nml`, which contains essential model parameters and settings.

2. **Tidal Boundary Conditions**: Executes `stofs_3d_atl_create_bctides_in.sh` to create `bctides.in`, defining tidal boundary conditions for the model.

3. **River Forcing**:
   - Uses `stofs_3d_atl_create_river_forcing_nwm.sh` to prepare river forcing data from the National Water Model.
   - Calls `stofs_3d_atl_create_river_st_lawrence.sh` to generate forcing files specifically for the St. Lawrence River.

4. **Surface Forcing**:
   - Runs `stofs_3d_atl_create_surface_forcing_gfs.sh` to create surface forcing files using Global Forecast System (GFS) data.
   - Executes `stofs_3d_atl_create_surface_forcing_hrrr.sh` to generate surface forcing files using High-Resolution Rapid Refresh (HRRR) data.

5. **Open Boundary Conditions**:
   - Calls `stofs_3d_atl_create_obc_3d_th.sh` to create 3D temperature and salinity boundary files.
   - Uses `stofs_3d_atl_create_obc_nudge.sh` to generate open boundary condition nudging files.

## Workflow Structure

The preprocessing workflow follows this general structure:

1. The main script (`exstofs_3d_atl_prep_processing.sh`) is initiated.
2. It sequentially calls each sub-script to perform specific tasks.
3. Each sub-script generates its respective output files or data.
4. The main script manages the overall process, ensuring all necessary inputs are prepared for the model run.

## Key Components

- **param.nml**: Contains model run parameters and settings.
- **bctides.in**: Specifies tidal boundary conditions.
- **River Forcing**: Includes data from the National Water Model and St. Lawrence River.
- **Surface Forcing**: Comprises atmospheric data from GFS and HRRR.
- **Open Boundary Conditions**: Includes 3D temperature and salinity files, and nudging data.

## Conclusion

The preprocessing stage is crucial for setting up the STOFS 3D Atlantic model run. It ensures that all necessary input files and configurations are properly prepared, integrating data from various sources to create a comprehensive set of forcing conditions for the model.
