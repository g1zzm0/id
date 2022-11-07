# Provision of simulation models

With the AAS submodel 'Simulation', simulation models from 'Suppliers' can be made available across manufacturers for use by an 'Integrator'. 
The integrator can thus pursue various simulation goals in the evaluation of solutions, which are described in the AAS submodel. 
A minimal model is described with a minimal set of basic features, which addresses all components and partial solutions. 
Thus, already available models can be found and integrated more easily. In a further step it is considered how a component-specific standardization must look like, in order to make also a manufacturer-spreading simple exchange of simulation models for partial solutions possible. E.g. using the example of drive components / solutions.


## Introduction

The submodel template `Provision of simulation models` allows the interoperable provision of simulation model files for an asset via the asset administration shell. The submodel enables this for a wide range of simulation model types and simulation purposes. It contains information about the type of model, how to use the model, and the areas of application.
The main underlying class of models for this sub-model are DAEs, models described by differential algebraic equations. However, models of other types, such as CAD, FMEA, etc., can also be described. FEM type models are not considered, they are covered by another submodel, actually under development. The models described by this submodel may be provided in ASCII or binary form to be used with a specific simulation software (e.g. Matlab/Simulink, Virtuos, etc.), as source code (e.g. C, Modelica, etc.), or in a model exchange format such as FMI.
It describes rudimentarily the content of the model.
Assets, where you can provide simulation models via AAS, can be passive parts, active devices, subsystems, machines or even production plants. When using this submodel template, it is requiered that the asset for which I want to provide a simulation model has an AAS. That is, if there are no AAS yet, I must first define the asset-ID and create an AAS. A submodel can then be added to this AAS.
In the first step, the submodel supports searching and finding, as well as requesting simulation model files from manufacturers or distributors.
In further steps, the submodel will also support the automatic integration of a model into a specific simulation environment, up to an automatic generation of an overall simulation based on structural descriptions of a system containing different components. As it is possible with e.g. the submodel candidate for a bill of material (BoM).

![SMTSim](https://user-images.githubusercontent.com/1814815/199018518-0d985525-c853-4a2a-9970-42af7f0fc035.jpg)


## Status: `Submitted`
The sub-namespace for SimulationModels and its identifiers have been finalized in the Taskforce Provision of simulation models.


## SimulationModels (Submodel)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModels](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModels)

The Submodel may provide one or more simulation models, a service to generate a specific model, or access to an open or specific query.

### SimulationModel (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel)
Feature collection to provide or request simulation models. Models can be described by objective and content.

### SimulationModel/Summary (MLP)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Summary](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Summary)
Summary of the contents of the simulation model in text form. 

### SimulationModel/SimPurpose (SMC)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimPurpose](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimPurpose) This characteristic describes the simulation purpose or suitability for different simulation goals. 

### SimulationModel/TypeOfModel (Property)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/TypeOfModel](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/TypeOfModel) List of modeling approaches used for the model

### SimulationModel/ScopeOfModel (Property)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ScopeOfModel](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ScopeOfModel) List of basic physical characteristics which are represented by the model.

### SimulationModel/LicenseModel (Property)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/LicenseModel](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/LicenseModel) If a simulation model usage will be charged and how it will be charged. 

### SimulationModel/EngineeringDomain (Property)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/EngineeringDomain](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/EngineeringDomain) List of engineering disciplines supported or mapped with the model.  

### SimulationModel/Environment (SMC)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment) Information about prerequisite environments or dependencies of underlying components on the target system. 

### SimulationModel/RefSimDocumentation (File)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/RefSimDocumentation](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/RefSimDocumentation) Simulation Documentation Documentation of example simulations of the model can be supplied. This includes a solver setup and sample circuit and sample results. e.g. zip file, PDF, html, ... -

### SimulationModel/ModelFile (SMC)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile) Providing versions of the simulation model and with characteristics to distinguish them. 

### SimulationModel/ParamMethod (Property)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ParamMethod](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ParamMethod) Indicates whether the model must be parameterized and if so, which method is required.

### SimulationModel/ParamFile (File)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ParamFile](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ParamFile) File for parameterization of the model. As parameter file or parameter documentation (e.g. pdf). 

### SimulationModel/InitStateMethod (Property)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/InitStateMethod](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/InitStateMethod) Describes the state variables of the simulation model that must be initialized to start the simulation. For initial value problems, these quantities describe the system state at the start of the simulation. In this case, the system is in a state of equilibrium. Alternatively, a simulation model may include a method to determine consistent initial values at this step, e.g., at an operating point. 

### SimulationModel/InitStateFile (File)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/InitStateFile](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/InitStateFile) File for parameterization of the model. As parameter file or parameter documentation (e.g. pdf). 

### SimulationModel/DefaultSimTime (Property)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/DefaultSimTime](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/DefaultSimTime) Predefined simulation period in seconds.

### SimulationModel/SimModManufacturerInformation (SMC)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimModManufacturerInformation](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimModManufacturerInformation) Provide access to  simulation support service provided by the distributor via mail or phone.

### SimulationModel/Ports (SMC)
[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports) Interfaces of the model. This includes inputs, outputs as well as acausal connections (e.g. mechanical connections). In addition, it is specified here whether the model provides binary interfaces (e.g. for visualization).


### SimulationModel/SimPurpose/PosSimPurpose (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimPurpose/PosSimPurpose](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimPurpose/PosSimPurpose)

List of simulation purposes for which the model is intended

### SimulationModel/SimPurpose/negSimPurpose (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimPurpose/negSimPurpose](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimPurpose/negSimPurpose)

List of simulation purposes for which the model is explicitly not suitable. 


### SimulationModel/Environment/operatingSystem (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/operatingSystem](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/operatingSystem)

### SimulationModel/Environment/ToolEnvironment (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/ToolEnvironment](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/ToolEnvironment)

### SimulationModel/Environment/DependencyEnvironment (MLP)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/DependencyEnvironment](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/DependencyEnvironment)

### SimulationModel/Environment/VisualizationInformation (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/VisualizationInformation](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/VisualizationInformation)

### SimulationModel/Environment/SimulationTool (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool)

## SimulationModel/SimulationTool (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimulationTool](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimulationTool)

Contains properties of the model with regarding to concrete simulation tools.

### SimulationModel/Environment/SimulationTool/SimToolName (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SimToolName](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SimToolName) Name of the simulation tool including version.
## HERE continue
### SimulationModel/Environment/SimulationTool/DependencySimTool (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/DependencySimTool](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/DependencySimTool) Dependencies of Simulation Tools.

### SimulationModel/Environment/SimulationTool/Compiler (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/Compiler](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/Compiler) Name of necessary compiler including version

### SimulationModel/Environment/SimulationTool/SolverAndTolerances (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances) Useful settings of the simulation environment. Includes e.g. solver settings. 


### SimulationModel/Environment/SimulationTool/SolverAndTolerances/StepSizeControlNeeded (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/StepSizeControlNeeded](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/StepSizeControlNeeded) Whether the model requires adaptive step size

### SimulationModel/Environment/SimulationTool/SolverAndTolerances/fixedStepSize (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/fixedStepSize](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/fixedStepSize) Fixed integration step size, if there is no adaptive step size

### SimulationModel/Environment/SimulationTool/SolverAndTolerances/StiffSolverNeeded (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/StiffSolverNeeded](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/StiffSolverNeeded) Rigid integrator recommended.

### SimulationModel/Environment/SimulationTool/SolverAndTolerances/SolverIncluded (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/SolverIncluded](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/SolverIncluded) Solver is integrated in the model (e.g. FMU for co-simulation).

### SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm) List of validated tool-solver combinations.


### SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/SolverAlgorithm (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/SolverAlgorithm](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/SolverAlgorithm) validated solver.

### SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/ToolSolverFurtherDescription (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/ToolSolverFurtherDescription](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/ToolSolverFurtherDescription) Further tool- and solver-specific information.

### SimulationModel/Environment/SimulationTool/SolverAndTolerances/Tolerance (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/Tolerance](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Environment/SimulationTool/SolverAndTolerances/TestedToolSolverAlgorithm/Tolerance) (relative) tolerance for theadaptive step size.


### SimulationModel/ModelFile/ModelFileType (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileType](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileType) Designation of the exchange format of the model. E.G.: FMI 1.0, Co-Simulation, Platform / Source - Code. FMI 2.0.2, Model Exchange, Source - Code, S-function, Version 2, 64bit, mex - Format / or C-Code, Modelica 3, encoded, VHDL

### SimulationModel/ModelFile/ModelFileVersion (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion) Provision of a version of the simulation model with information to distinguish the versions. The versions are primarily intended for bug fixes without content changes


### SimulationModel/ModelFile/ModelFileVersion/ModelVersionId (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/VersionId](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/ModelVersionId)

Version number of the model from the vendor.

### SimulationModel/ModelFile/ModelFileVersion/ModelPreviewImage (File)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/ModelPreviewImage](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/ModelPreviewImage)

Image file to represent the model in user interfaces, e.g. in a search.

### SimulationModel/ModelFile/ModelFileVersion/DigitalFile (File)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/DigitalFile](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/DigitalFile)

Deployment of the model file

### SimulationModel/ModelFile/ModelFileVersion/ModelFileReleaseNotesTxt (MLP)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/ModelFileReleaseNotesTxt](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/ModelFileReleaseNotesTxt)

contains information about this release

### SimulationModel/ModelFile/ModelFileVersion/ModelFileReleaseNotesFile (File)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/ModelFileReleaseNotesFile](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/ModelFile/ModelFileVersion/ModelFileReleaseNotesFile) release notes link or file


### SimulationModel/SimModManufacturerInformation/Phone (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimModManufacturerInformation/Phone](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/SimModManufacturerInformation/Phone) Phone number including type


### SimulationModel/Ports/PortsConnector (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortsConnector](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortsConnector)

List of ports of the model. These include a name, a description, a list of variables, and a list of ports. 

### SimulationModel/Ports/BinaryConnector (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/BinaryConnector](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/BinaryConnector)
List of Binary interfaces (binaryType) based on the FMI 3.0 standard (https://fmi-standard.org/Docs/3.0-dev/#definition-of-types). At this point the name (e.g. "Binary interface visualization") and the description (e.g. "Interface for binary transfer of visualization information") are specified. 


### SimulationModel/Ports/PortConnector/PortConnectorName (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/PortConnectorName](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/PortConnectorName)

Name of the Connector Port.

### SimulationModel/PortsConnector/PortConDescription (MLP)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/PortConDescription](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/PortConDescription)

Description of the Connector Port. 

### SimulationModel/Ports/PortConnector/Variable (SMC)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable)

List of variables of the port. 


### SimulationModel/Ports/PortConnector/Variable/VariableName (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableName](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableName) Name of the variable. 

### SimulationModel/Ports/PortConnector/Variable/Range (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/Range](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/Range) Range of values for the variable (e.g. [min, max], [min, max[, ]min, max], ]min, max[, {val1, val2, ...}). 


### SimulationModel/Ports/PortConnector/Variable/VariableType (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableType](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableType) Type of the variable (e.g. Real, Integer, Boolean, String or Enum).

### SimulationModel/Ports/PortConnector/Variable/VariableDescription (MLP)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableDescription](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableDescription) Description of the variable. 

### SimulationModel/Ports/PortConnector/Variable/UnitList (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/UnitList](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/UnitList) The most common units can be selected here. If "others" is selected, a free text can be entered. 

### SimulationModel/Ports/PortConnector/Variable/UnitDescription (MLP)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/UnitDescription](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/UnitDescription) Text field for missing units of the list.


### SimulationModel/Ports/PortConnector/Variable/VariableCausality (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableCausality](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariableCausality) The causality of the variable: input to inputs, output to ouputs, acausal connections (e.g. mechanical connection) do not have causality.

### SimulationModel/Ports/PortConnector/Variable/VariablePrefix (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariablePrefix](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/PortConnector/Variable/VariablePrefix) Prefix for acausal variable. Potential variables are set equal when connecting (no prefix). Stream variables are connected according to Kirchhoff's law, i.e. the sum of the variables equals zero. The bi-directional flow of matter is described with "stream" (e.g. for enthalpy). 


### SimulationModel/Ports/BinaryConnector/BinaryConName (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/BinaryConnector/BinaryConName](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/BinaryConnector/BinaryConName) Binary interface name. 

### SimulationModel/BinaryConnector/BinaryConDescription (Property)

[https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/BinaryConnector/BinaryConDescription](https://admin-shell.io/idta/SimulationModels/1/0/SimulationModel/Ports/BinaryConnector/BinaryConDescription) Binary interface description. 

## Versions: [1.0](.)
This version is the first version to be officially published by IDTA Document `Provision of simulation models 1.0`.

## Contact

This sub-namespace is proposed by [IDTA Working Group `Provision of simulation models`](https://github.com/admin-shell-io/submodel-templates/tree/main/development/simulation/1/0). See also [IDTA Registered AAS Submodel Templates](https://industrialdigitaltwin.org/content-hub/Teilmodelle#:~:text=Provision%20of%20simulation%20models) or contact via email the [IDTA project manager for submodel templates](mailto:sudip.adhikari@idtwin.org) or [chair of the working group](mailto:Markus.Kiele-Dunsche@lenze.com).
