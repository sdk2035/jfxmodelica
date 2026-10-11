# Categorized dependency and reference catalog

Reviewed 2026-10-11. This is an **adoption catalog**, not an installation manifest. JFXModelica has no executable dependency manifest in the inspected baseline. No entry below is declared installed, required at runtime or compatible with every other entry.

## Classification

- **Initial worker candidate:** evaluate first for a bounded simulation contract.
- **Optional integration / research candidate:** adopt only for a demonstrated use case.
- **Reference / specification:** informs design; not automatically executable software.
- **Development tooling:** used by contributors, separately from deployed workers.

The additional attachment supplied 17 unique repository URLs. All 17 are included exactly once below. Repository metadata was checked through GitHub; descriptions and fork provenance establish intended scope, not numerical correctness, license compliance or validated JFXModelica integration.

## Standards and language references

| Repository | Role | Adoption classification | Provenance / inspected default branch |
| --- | --- | --- | --- |
| [robotics-intelligent-systems/ModelicaSpecification](https://github.com/robotics-intelligent-systems/ModelicaSpecification) | Modelica language specification | Specification reference; not a runtime package | Fork of [modelica/ModelicaSpecification](https://github.com/modelica/ModelicaSpecification); `master` |

## Simulation engines and compiler/front-end alternatives

| Repository | Role | Adoption classification | Provenance / inspected default branch |
| --- | --- | --- | --- |
| [robotics-intelligent-systems/OpenModelica](https://github.com/robotics-intelligent-systems/OpenModelica) | Modelica compilation and simulation | Initial worker candidate | Fork of [OpenModelica/OpenModelica](https://github.com/OpenModelica/OpenModelica); `master` |
| [robotics-intelligent-systems/JModelica](https://github.com/robotics-intelligent-systems/JModelica) | Modeling, simulation and optimization platform | Alternative engine; evaluate maintenance and compatibility | Fork of [JModelica/JModelica](https://github.com/JModelica/JModelica); `master` |
| [sdk2035/rumoca](https://github.com/sdk2035/rumoca) | Rust-native Modelica compiler | Alternative compiler; assess supported language subset | Fork of [CogniPilot/rumoca](https://github.com/CogniPilot/rumoca); `main` |
| [choeger/modelica.ml](https://github.com/choeger/modelica.ml) | OCaml Modelica front end | Compiler research/reference | Independent repository; `master` |
| [sdk2035/modelscript](https://github.com/sdk2035/modelscript) | Modelica/SysML2-oriented compiler tooling | Integration/research candidate; validate claimed transformations | Fork of [modelscript/modelscript](https://github.com/modelscript/modelscript); `main` |

## AI-assisted modeling and learning

| Repository | Role | Adoption classification | Provenance / inspected default branch |
| --- | --- | --- | --- |
| [sdk2035/ModiGen](https://github.com/sdk2035/ModiGen) | LLM-based multi-domain component generation | Research candidate | Fork of [miko99jh/ModiGen](https://github.com/miko99jh/ModiGen); `main` |
| [robotics-intelligent-systems/SMArtIInt](https://github.com/robotics-intelligent-systems/SMArtIInt) | Modelica artificial-intelligence interface | Optional AI integration candidate | Fork of [xrg-simulation/SMArtIInt](https://github.com/xrg-simulation/SMArtIInt); `main` |
| [sdk2035/modelicagym](https://github.com/sdk2035/modelicagym) | Modelica-to-Gym integration | Optional learning-environment candidate; assess API generation compatibility | Fork of [ucuapps/modelicagym](https://github.com/ucuapps/modelicagym); `master` |

## Visualization and model editors

| Repository | Role | Adoption classification | Provenance / inspected default branch |
| --- | --- | --- | --- |
| [sdk2035/jfxengine](https://github.com/sdk2035/jfxengine) | SysML models in a 3D environment | Portfolio integration candidate | Independent repository; `main` |
| [sdk2035/visualization2](https://github.com/sdk2035/visualization2) | Modelica real-time visualization in C++ | Optional visualization candidate | Fork of [DLR-FT/visualization2](https://github.com/DLR-FT/visualization2); `main` |
| [sdk2035/webmodelica](https://github.com/sdk2035/webmodelica) | Web-based Modelica toolbox | Web-tooling reference | Fork of [modelica-tools/webmodelica](https://github.com/modelica-tools/webmodelica); `master` |
| [sdk2035/MoDE](https://github.com/sdk2035/MoDE) | Modelica diagram editor | Editor reference | Fork of [modelica-tools/MoDE](https://github.com/modelica-tools/MoDE); `master` |
| [robotics-intelligent-systems/OMEdit](https://github.com/robotics-intelligent-systems/OMEdit) | OpenModelica connection editor | Development tooling; assess relation to chosen OpenModelica distribution | Fork of [OpenModelica/OMEdit](https://github.com/OpenModelica/OMEdit); `master` |

## MBSE and external-environment interoperability

| Repository | Role | Adoption classification | Provenance / inspected default branch |
| --- | --- | --- | --- |
| [sdk2035/Scilab-OpenModelica-Integration](https://github.com/sdk2035/Scilab-OpenModelica-Integration) | Scilab/XCos and OpenModelica code-generation integration | Optional integration candidate | Fork of [BeppeInfo/Scilab-OpenModelica-Integration](https://github.com/BeppeInfo/Scilab-OpenModelica-Integration); `master` |
| [sdk2035/edu.gatech.mbse.mdsysmlmodelica](https://github.com/sdk2035/edu.gatech.mbse.mdsysmlmodelica) | Java SysML–Modelica transformation using MagicDraw | Transformation reference; branch magicdraw-v18.2 requires explicit tool/version review | Fork of [SysMLModelicaIntegration/edu.gatech.mbse.mdsysmlmodelica](https://github.com/SysMLModelicaIntegration/edu.gatech.mbse.mdsysmlmodelica); `magicdraw-v18.2` |

## Developer tooling

| Repository | Role | Adoption classification | Provenance / inspected default branch |
| --- | --- | --- | --- |
| [robotics-intelligent-systems/modelica-language-vscode](https://github.com/robotics-intelligent-systems/modelica-language-vscode) | Modelica language support for VS Code | Optional editor extension | Fork of [SimplyDanny/modelica-language-vscode](https://github.com/SimplyDanny/modelica-language-vscode); `master` |

## Additional technology candidates from the original README

These are separate from the 17-URL attachment and do not add adopted dependencies.

| Category | Candidate / source | Proposed role | Adoption condition |
| --- | --- | --- | --- |
| Model libraries | [Modelica Standard Library](https://github.com/modelica/ModelicaStandardLibrary) | Reusable physical components | Pin a compatible library version for the selected compiler and fixture |
| Exchange standard | [FMI](https://fmi-standard.org/) | FMU interchange and co-simulation contracts | Select FMI version, FMU type, platform and tested tool support |
| CFD | [OpenFOAM](https://www.openfoam.org/) | Optional fluid-dynamics worker | Define fields, units, mesh and coupling/time contracts |
| FEA | [CalculiX](https://www.calculix.de/) | Optional structural-analysis worker | Validate materials, loads, boundaries and reference results |
| Flight dynamics | [JSBSim](https://github.com/JSBSim-Team/jsbsim) | Optional aircraft/control scenario worker | Define coordinates, units, model provenance and replay fixture |
| Web interface | [React](https://react.dev/) | Candidate web user interface | Introduce a frontend only with an implementation and pinned package manifest |
| Web visualization | [Three.js](https://threejs.org/) | Candidate browser 3D renderer | Define geometry/result mapping and measured performance |
| AI endpoints | Llama-family, DeepSeek-Coder or CodeLlama examples from the source README | Replaceable model-generation/analysis endpoint | Select exact model, weights/version, license, serving contract and evaluation fixture; no specific model is mandated |
| Language/metaprogramming references | Rascal MPL and MechatronicUML from the MBSE note | Possible transformation tooling | Separate source language, target semantics and supported transformations |

## Minimum adoption record

For each component actually selected, record:

| Field | Required evidence |
| --- | --- |
| Identity | Upstream URL, local fork if used and exact commit/release |
| Version | Compiler/runtime and library versions; no unpinned “latest” baseline |
| License | Project/dependency/model-weight licenses and redistribution review |
| Boundary | Runtime, tool, integration adapter or reference; required vs optional |
| Contract | Source/target formats, units, variables, timing, errors and version negotiation |
| Verification | Reproducible fixture, expected/observed results and compatibility limits |
| Ownership | Maintainer and update/deprecation decision |

No cross-version compatibility or upstream maintenance audit was performed in this documentation pass. Fork metadata must not be used as evidence that a local fork is current with upstream. Do not install multiple compiler backends by default or count editor tools as runtime dependencies.

[Documentation index](../README.md) · [Source register](../source-register.md)
