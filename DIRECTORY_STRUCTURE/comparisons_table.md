| Aspect | Old Workflow | New Workflow |
|--------|--------------|--------------|
| Overall Structure | Separate 2D and 3D workflows | Unified workflow with system-specific branches |
| ECF Files | System-specific .ecf files in separate directories | Generalized .ecf files in single directory |
| Job Scripts | Separate JSTOFS_* files for different tasks | No separate job scripts, functionality in .ecf files |
| Main Scripts | exstofs_*.sh scripts in system-specific directories | Unified scripts directory with common and system-specific subdirectories |
| Configuration Management | Scattered across various directories | Centralized in config directory, using YAML files |
| Error Handling | Implicit in individual scripts | Explicit validation and verification tasks |
| System Selection | Hardcoded in separate workflows | Dynamic using STOFS_SYSTEM variable |
| Utility Scripts | System-specific ush directories | Focused on common utilities in single ush directory |
| Workflow Definition | Implicit in job scheduling | Explicit in ecFlow suite definition file |
| Modularity | Highly separated between 2D and 3D | More unified, easier to extend to additional systems |
| Post-processing | System-specific post-processing scripts | More generalized with system-specific branches |
| Version Control | Separate version files for 2D and 3D | Centralized version management |
| Environment Setup | Scattered across job scripts | Dedicated environment setup task |
| Data Validation | Limited, system-specific | Enhanced, generalized data validation tasks |
| Execution Flow | Linear, system-specific | More parallel execution where possible |
| Code Reusability | Limited due to system separation | Improved with common scripts and utilities |
| Maintenance | Requires updates in multiple places for changes | Centralized changes, easier maintenance |
| Scalability | Difficult to add new systems | Designed for easier addition of new systems |
| Documentation | Scattered across scripts | Potential for centralized, workflow-level documentation |
