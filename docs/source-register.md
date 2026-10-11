# Source register and TXT migration

Documentation migration reviewed 2026-10-11. Source notes are reference material, not instructions to execute tools, install software or change external projects.

## Renaming, translation and consolidation

The three generic Spanish TXT names are replaced by one English Markdown handbook with meaningful sections. Their text is translated and consolidated by topic, with table structure restored. Original versions remain recoverable in Git history at baseline commit `62adfa1b915c7aec3a3591248b8693a5e68c64cc`.

| Original file | Original blob SHA | English consolidated destination |
| --- | --- | --- |
| [docs/Cuando se busca una alternativa.txt](https://github.com/sdk2035/jfxmodelica/blob/62adfa1b915c7aec3a3591248b8693a5e68c64cc/docs/Cuando%20se%20busca%20una%20alternativa.txt) | `da1b7dba60aa189a1b3853b6db7dc7f4c7c34ad2` | [Physical modeling bridges](engineering/mbse-and-cad-handbook.md#physical-modeling-bridges) |
| [docs/Las metodologías de Ingeniería.txt](https://github.com/sdk2035/jfxmodelica/blob/62adfa1b915c7aec3a3591248b8693a5e68c64cc/docs/Las%20metodolog%C3%ADas%20de%20Ingenier%C3%ADa.txt) | `9d415054b6f8692c809f233dddf4b653077f65b3` | [MBSE methods](engineering/mbse-and-cad-handbook.md#mbse-methods) |
| [docs/Para organizar los diseños.txt](https://github.com/sdk2035/jfxmodelica/blob/62adfa1b915c7aec3a3591248b8693a5e68c64cc/docs/Para%20organizar%20los%20dise%C3%B1os.txt) | `bed2927af8a9abf3f31ccdbadb90683b4700780c` | [CAD application taxonomy and complexity](engineering/mbse-and-cad-handbook.md#cad-application-taxonomy) |

## Additional attachment

The user supplied **https github com robotics.txt**, containing 17 repository URLs and no executable instructions. URLs were normalized, checked for duplicates and categorized in the [dependency catalog](dependencies/catalog.md). All 17 are retained as linked entries with their upstream/fork relationships and inspected default branches.

The attachment has been consolidated into that catalog rather than copied as another unstructured TXT. The classification is an editorial interpretation of repository metadata; it does not adopt the repositories as dependencies.

## Technical qualifications and editorial changes

- Arcadia/Capella is separated from a generic UML/SysML-profile classification. Its process and modeling language have distinct semantics.
- SysML, SysPhS and ModelicaML bridges are conditioned on selected tool/profile/version support; arbitrary graphical models are not assumed executable.
- SysML 1.x profile descriptions are not generalized to all editions; selected language and method editions must be recorded.
- The note's OOSEM/ISO alignment claim is not represented as proven conformance.
- The CAD note's apparent “multicuero” typo is interpreted as multibody, explicitly marked in the handbook.
- CAD concepts are examples, not verified assets. IP ratings, URDF/SDF compatibility, stress results and manufacturing readiness require evidence.
- Unresolved `[cite: 2]` markers in the original README are removed; descriptions of native/real-time/cloud functionality are reframed as proposals.
- The existing draw.io file outside docs is retained unchanged; its filename and contents are outside this TXT consolidation.
- Repeated general guidance is consolidated; detailed examples, method distinctions and complexity levels remain available in the handbook.

## Primary references for clarified claims

- [OMG SysPhS specification](https://www.omg.org/spec/SysPhS/1.1/) and [OMG physical-interaction overview](https://www.omgwiki.org/OMGSysML/doku.php?id=sysml-sysphs%3Asysml_extension_for_physical_interaction_and_signal_flow_simulation_sysphs).
- [Eclipse Capella project description](https://projects.eclipse.org/projects/polarsys.capella/governance) and [Capella / SysML relationship](https://mbse-capella.org/arcadia_capella_sysml_tool.html).
- [SYSMOD publisher information](https://mbse4u.com/wp-content/sysmod/sysmodv5-reveal.html).
- Linked source repositories in the dependency catalog; role descriptions checked against repository metadata on 2026-10-11.

[Documentation index](README.md)
