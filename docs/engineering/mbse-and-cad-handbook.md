# MBSE, physical modeling and CAD handbook

Consolidated English edition of three Spanish engineering notes. The [source register](../source-register.md) maps original filenames to these sections and records technical qualifications. This handbook is guidance for proposed engineering work, not evidence of implemented transformations or validated CAD assets.

## Physical modeling bridges

Modelica describes physical behavior with equations and supports continuous and hybrid models. UML-based systems modeling offers complementary architecture and traceability views; a diagram by itself is not a substitute for equation semantics.

### ModelicaML

ModelicaML is a UML-oriented modeling approach that connects system/model structure and behavior to Modelica semantics. Suitable tooling can generate Modelica source from supported graphical constructs. Tool compatibility, supported constructs and preservation of event/state semantics must be checked for the selected implementation; automatic conversion is not assumed for arbitrary UML models.

Class/structure and state-machine views can contribute to the model. Continuous-time integration, initialization, discrete events and transitions require explicit semantics. Review generated code and run compiler and numerical fixtures before relying on the transformation.

### SysML and SysPhS

SysML supports requirements, architecture and behavior. SysPhS extends physical-interaction and signal-flow modeling, including lumped-parameter electrical, mechanical, hydraulic and thermal systems. This is a bridge to physical simulation, not a universal replacement for a Modelica compiler. See the [OMG specification](https://www.omg.org/spec/SysPhS/1.1/) and [OMG overview](https://www.omgwiki.org/OMGSysML/doku.php?id=sysml-sysphs%3Asysml_extension_for_physical_interaction_and_signal_flow_simulation_sysphs).

Export to Modelica or a different simulation environment depends on a compatible transformation tool and its supported profile/version. Declare units, connector semantics, parameters, initial conditions and solver settings. Do not generalize SysML 1.x profile assumptions to every SysML version or implementation.

### Choosing and combining views

| Dimension | Modelica-centered approach | Systems-modeling bridge |
| --- | --- | --- |
| Representation | Equation-oriented source with optional graphical annotations | Architecture/requirements diagrams with explicit physical extensions |
| Main purpose | Multidomain dynamic behavior and simulation | Traceability among needs, structure, behavior and physical models |
| Reuse | Physical model libraries and connectors | Requirements, architecture patterns and model transformations |
| Evidence | Compiled equations and numerical behavior | Trace links plus verified generated/exported models |
| Boundary | Does not supply every systems-engineering process | Does not automatically provide executable solver semantics |

Use systems views when requirements, hardware/software architecture, configuration and physical behavior need to remain linked. Use a small Modelica fixture to establish the simulation contract before generalizing across aerospace, automotive, robotics or other large systems.

## MBSE methods

MBSE methods organize the engineering process; languages describe model constructs; tools implement subsets of those constructs. Choose the process, language/version and toolchain explicitly.

| Method | Origin / reference tradition | Main focus | Modeling relationship |
| --- | --- | --- | --- |
| Harmony-SE | IBM / Telelogic | Use-case-driven systems/software analysis and iterative development | UML/SysML-oriented workflows |
| OOSEM | INCOSE community | Object-oriented systems analysis and architecture alternatives | Commonly applied with SysML; process/tool conformance requires separate review |
| SYSMOD | Tim Weilkiens / MBSE4U | Context, requirements and pragmatic system architecture | Specify the SysML edition and selected method edition; see [MBSE4U](https://mbse4u.com/wp-content/sysmod/sysmodv5-reveal.html) |
| Arcadia / Capella | Thales / Eclipse ecosystem | Operational, system, logical and physical architecture perspectives | Arcadia method with Capella-specific modeling language; not simply a SysML profile |
| MagicGrid | No Magic / Dassault Systèmes | Structured problem/solution viewpoints and traceability | SysML-oriented framework; selected tool/version must be recorded |

The original notes grouped every approach as UML/SysML-based. Arcadia/Capella requires a distinct classification: its architecture language and process differ from a generic SysML profile. See [Eclipse project description](https://projects.eclipse.org/projects/polarsys.capella/governance) and [Capella explanation](https://mbse-capella.org/arcadia_capella_sysml_tool.html). The source's claimed alignment of OOSEM with ISO/IEC 15288 is not treated here as a demonstrated conformance result.

### Harmony-SE workflow

Start with stakeholder requirements and system use cases. Analyze scenarios through interactions and states, then derive a logical architecture and allocate responsibilities to physical hardware, software and mechanical subsystems. Iterative V-style cycles connect development and verification; the project must still define its concrete acceptance cases.

### OOSEM workflow

Analyze stakeholder needs and business constraints; describe system behavior and performance parameters; synthesize alternative logical/physical architectures. Use parameter relationships and trade-off criteria to compare alternatives. Record the selected architecture and verification evidence rather than assuming a modeling method establishes acceptance.

### SYSMOD workflow

Define the system boundary and external actors. Identify use cases and requirements, then decompose the system into blocks, interfaces and allocated responsibilities. Bind requirement IDs to verification cases and identify open decisions. Preserve context when refining logical structure into a physical implementation.

### Arcadia workflow

Separate four engineering perspectives:

1. Operational analysis: activities and stakeholder needs.
2. System analysis: capabilities and responsibilities of the system.
3. Logical architecture: conceptual components and exchanges.
4. Physical architecture: implementation components and deployment choices.

Capella supports the Arcadia approach. Exchanges with SysML or physical simulation tools require an explicit bridge and validation of the selected representation.

### MagicGrid workflow

Use a structured matrix of stakeholder/problem and solution perspectives to keep requirements, behavior, structure and parameters connected. Agree on the chosen framework scope, modeling conventions and review evidence before using it as a project baseline.

### Cyber-physical transformation pipeline

Requirements and architecture views can feed metaprogramming, language tooling or AI-assisted model generation. Rascal MPL, MechatronicUML, Modelica and LLMs play different roles; listing them does not establish a working compiler pipeline.

A transformation contract should state source language/version, target language/version, supported constructs, units, timing semantics, error handling and trace mapping. Retain generated-code provenance and independently verify physical behavior.

## CAD application taxonomy

Use two independent axes: **application domain** and **technical complexity**. The following categories organize concepts; they are not an inventory of existing JFXModelica CAD deliverables.

| Application category | Typical conceptual models | Industrial / research use |
| --- | --- | --- |
| Mobile and ground robotics | Differential-drive chassis, omni/Mecanum platforms, adaptive suspension, tracked mounts | AGV/AMR navigation, indoor inspection and logistics |
| Arms and manipulators | Servo-compatible links, grippers and articulated supports, approximately 3–6 degrees of freedom | Pick-and-place, assembly and kinematics education |
| Airframes and drones | Quad/hexacopter frames, motor nacelles and vibration-isolated sensor gimbals | Aerial inspection, photogrammetry and remote monitoring |
| Sensor/IoT housings and mounts | RGB-D camera/LiDAR mounts; SBC and microcontroller enclosures | Prototyping, electronics protection and perception |
| Mechanisms and transmissions | Planetary gears, flexible couplings, cycloidal reducers and timing pulleys | Torque transfer, integrated actuators and positioning mechanisms |

RealSense/Orbbec cameras, Raspberry Pi/Jetson boards and related devices in the original note are illustrative hardware examples. An enclosure drawing alone does not establish an ingress-protection rating, fit, manufacturability or thermal performance.

## CAD complexity levels

| Level | Characteristics | Representative examples | Engineering checks before acceptance |
| --- | --- | --- | --- |
| 1 — Basic | Static single parts, adapters, flanges and mounts; candidate additive/laser-cut fabrication | Sensor brackets, spacers, base plates and V-slot/T-slot adapters | Units, dimensions, loads, mounting fit and process constraints |
| 2 — Intermediate | Simple articulated mechanisms, functional housings, approximately 2–5 parts and 1–3 DOF | Screw/rack grippers, 2-DOF pan-tilt mounts and ventilated housings | Tolerances, interference, actuation, cable routing and thermal/power separation |
| 3 — Advanced | Parametric multibody assemblies with coupled geometry, kinematics and mechatronics | 4–6 DOF manipulators, mobile chassis with suspension and integrated motor/reducer/driver joints | Joint/inertia/frame definitions, stress analysis, manufacturability and interface validation |

The original advanced-level note's apparent typo “multicuero” is interpreted as multibody in this engineering context. This interpretation does not identify a validated source CAD model.

Compatibility with URDF/SDF, ROS 2, Gazebo or Isaac Sim is a goal requiring conversion and validation. Geometry alone does not supply coordinate frames, inertias, joints, collision models or controller semantics. FEA and design-for-manufacturing studies need material, load, boundary-condition and process assumptions.

## Applying the handbook to JFXModelica

Start with one reviewed physical model and one worker interface. Keep context/requirements separate from mathematical behavior while preserving traceability. Classify any CAD concept by domain and complexity, then record geometry, units, parameters and evidence separately.

Select tool candidates from the [catalog](../dependencies/catalog.md). Neither the notes nor the repository-list attachment commits the project to installing every listed component.
