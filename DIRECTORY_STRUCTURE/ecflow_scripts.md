# Functions of ECF Files in the Unified STOFS Workflow

1. **stofs_suite.def**
   - Main ecFlow suite definition file
   - Defines the overall structure and flow of the entire workflow
   - Sets up dependencies and triggers between tasks

2. **init.ecf**
   - Initializes the workflow environment
   - Sets up basic variables and paths
   - Ensures all necessary directories exist

3. **setup_environment.ecf**
   - Loads required modules
   - Sets up system-specific environment variables
   - Prepares the runtime environment for subsequent tasks

4. **load_config.ecf**
   - Reads and loads configuration files (e.g., YAML configs)
   - Sets up system-specific parameters
   - Determines which STOFS system (3D or 2D Global) to run

5. **validate_config.ecf**
   - Checks the loaded configuration for consistency and completeness
   - Ensures all required parameters are present and valid
   - Flags any potential issues before proceeding with the workflow

6. **fetch_input_data.ecf**
   - Retrieves necessary input data i.e. RTOFS, GFS, HRRR etc. for the model run
   - May include downloading data i.e.GFS, HRRR or copying from local storage
   - Ensures all required input files are available

7. **validate_input_data.ecf**
   - Checks the integrity and completeness of input data
   - Verifies file formats, sizes, and content as needed
   - Ensures input data meets the requirements for model execution

8. **common_prep.ecf**
   - Performs preparation tasks common to both STOFS3D and STOFS2D Global
   - May include data preprocessing or setup tasks shared by both systems

9. **stofs3d_prep.ecf**
   - Executes STOFS3D-specific preparation tasks 
   - May include grid generation, initial condition setup, etc.
   - Calls relevant Python scripts (e.g., using pyschism) from $USH directory for  prep tasks

10. **stofs2d_global_prep.ecf**
    - Executes STOFS2D Global-specific preparation tasks
    - Similar to stofs3d_prep.ecf, but for the ADCIRC based 2D Global system

11. **verify_prep.ecf**
    - Checks that all preparation steps completed successfully
    - Verifies that the system is ready for model execution

12. **allocate_resources.ecf**
    - Determines and allocates computational resources for the model run
    - May interact with job scheduling system to request necessary nodes/cores

13. **stofs3d_run.ecf**
    - Executes the STOFS3D model (SCHISM)
    - Manages the main model run process for 3D simulations

14. **stofs2d_global_run.ecf**
    - Executes the STOFS2D Global model (ADCIRC)
    - Manages the main model run process for 2D Global simulations

15. **verify_model_run.ecf**
    - Checks that the model run completed successfully
    - Verifies output files are present and valid

16. **process_output.ecf**
    - Performs initial processing of model output files
    - May include format conversions or data extractions

17. **generate_products.ecf**
    - Creates final products from processed model outputs
    - May include generating specific file formats required by end-users

18. **create_visualizations.ecf**
    - Generates plots, maps, or other visual representations of model results

19. **prepare_distribution.ecf**
    - Prepares files for distribution to various systems or end-users
    - May include packaging, compression, or metadata addition

20. **verify_post.ecf**
    - Ensures all post-processing steps completed successfully
    - Verifies that all required products are generated and ready for distribution

21. **cleanup.ecf**
    - Removes temporary files and directories
    - Frees up resources no longer needed

22. **send_notifications.ecf**
    - Sends notifications about job completion or any issues encountered
    - May email reports or update monitoring systems