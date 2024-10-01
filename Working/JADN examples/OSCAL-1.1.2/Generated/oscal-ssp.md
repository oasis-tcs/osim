       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-ssp"
    namespaces: [["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"], ["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["ic", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-implementation-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["System-security-plan"]
       comment: "OSCAL System Security Plan (SSP) Model: JSON Schema"

A system security plan, such as those described in NIST SP 800-18.

**Type: System-security-plan (Record)**

| ID | Name                       | Type                   | \#   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----|----------------------------|------------------------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                   | c:UUIDDatatype         | 1    | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this system security plan (SSP) elsewhere in this or other OSCAL instances. The locally defined UUID of the SSP can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance).This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **metadata**               | m:Metadata             | 1    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 3  | **import-profile**         | Import-profile         | 1    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 4  | **system-characteristics** | System-characteristics | 1    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 5  | **system-implementation**  | System-implementation  | 1    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 6  | **control-implementation** | Control-implementation | 1    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 7  | **back-matter**            | m:Back-matter          | 0..1 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**********

Used to import the OSCAL profile representing the system's control baseline.

**Type: Import-profile (Record)**

| ID | Name        | Type                   | \#   | Description                                                                                   |
|----|-------------|------------------------|------|-----------------------------------------------------------------------------------------------|
| 1  | **href**    | c:URIReferenceDatatype | 1    | A resolvable URL reference to the profile or catalog to use as the system's control baseline. |
| 2  | **remarks** | m:Remarks              | 0..1 |                                                                                               |

**********

Contains the characteristics of the system, such as its name, purpose, and security impact level.

**Type: System-characteristics (Record)**

| ID | Name                           | Type                   | \#    | Description                                                                                                    |
|----|--------------------------------|------------------------|-------|----------------------------------------------------------------------------------------------------------------|
| 1  | **system-ids**                 | ic:System-id           | 1..\* |                                                                                                                |
| 2  | **system-name**                | c:StringDatatype       | 1     | The full name of the system.                                                                                   |
| 3  | **system-name-short**          | c:StringDatatype       | 0..1  | A short name for the system, such as an acronym, that is suitable for display in a data table or summary list. |
| 4  | **description**                | String                 | 1     | A summary of the system.                                                                                       |
| 5  | **props**                      | m:Property             | 0..\* |                                                                                                                |
| 6  | **links**                      | m:Link                 | 0..\* |                                                                                                                |
| 7  | **date-authorized**            | Date-authorized        | 0..1  |                                                                                                                |
| 8  | **security-sensitivity-level** | c:StringDatatype       | 0..1  | The overall information system sensitivity categorization, such as defined by FIPS-199.                        |
| 9  | **system-information**         | System-information     | 1     |                                                                                                                |
| 10 | **security-impact-level**      | Security-impact-level  | 0..1  |                                                                                                                |
| 11 | **status**                     | Status                 | 1     |                                                                                                                |
| 12 | **authorization-boundary**     | Authorization-boundary | 1     |                                                                                                                |
| 13 | **network-architecture**       | Network-architecture   | 0..1  |                                                                                                                |
| 14 | **data-flow**                  | Data-flow              | 0..1  |                                                                                                                |
| 15 | **responsible-parties**        | m:Responsible-party    | 0..\* |                                                                                                                |
| 16 | **remarks**                    | m:Remarks              | 0..1  |                                                                                                                |

**********

The date the system received its authorization.

**Type: Date-authorized (Choice(allOf))**

| ID | Name | Type           | \# | Description |
|----|------|----------------|----|-------------|
| 1  | **** | c:DateDatatype | 1  | **alias** -  |

**********

Contains details about all information types that are stored, processed, or transmitted by the system, such as privacy information, and those defined in NIST SP 800-60.

**Type: System-information (Record)**

| ID | Name                  | Type                                 | \#    | Description |
|----|-----------------------|--------------------------------------|-------|-------------|
| 1  | **props**             | m:Property                           | 0..\* |             |
| 2  | **links**             | m:Link                               | 0..\* |             |
| 3  | **information-types** | System-information.information-types | 1..\* |             |

**********

Contains details about one information type that is stored, processed, or transmitted by the system, such as privacy information, and those defined in NIST SP 800-60.

**Type: System-information.information-types (Record)**

| ID | Name                       | Type                                                 | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|----|----------------------------|------------------------------------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                   | c:UUIDDatatype                                       | 0..1  | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this information type elsewhere in this or other OSCAL instances. The locally defined UUID of the information type can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**                  | String                                               | 1     | A human readable name for the information type. This title should be meaningful within the context of the system.                                                                                                                                                                                                                                                                                                                                                               |
| 3  | **description**            | String                                               | 1     | A summary of how this information type is used within the system.                                                                                                                                                                                                                                                                                                                                                                                                               |
| 4  | **categorizations**        | System-information.information-types.categorizations | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 5  | **props**                  | m:Property                                           | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 6  | **links**                  | m:Link                                               | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 7  | **confidentiality-impact** | Impact                                               | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 8  | **integrity-impact**       | Impact                                               | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 9  | **availability-impact**    | Impact                                               | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**********

A set of information type identifiers qualified by the given identification system used, such as NIST SP 800-60.

**Type: System-information.information-types.categorizations (Record)**

| ID | Name                     | Type                                                        | \#    | Description                                                |
|----|--------------------------|-------------------------------------------------------------|-------|------------------------------------------------------------|
| 1  | **system**               | System-information.information-types.categorizations.system | 1     | Specifies the information type identification system used. |
| 2  | **information-type-ids** | c:StringDatatype                                            | 0..\* |                                                            |

**********

Specifies the information type identification system used.

**Type: System-information.information-types.categorizations.system (Choice(anyOf))**

| ID | Name | Type                                                          | \# | Description |
|----|------|---------------------------------------------------------------|----|-------------|
| 1  | **** | c:URIDatatype                                                 | 1  | **c1** -    |
| 2  | **** | System-information.information-types.categorizations.system.2 | 1  | **c2** -    |

**********

**Type: System-information.information-types.categorizations.system.2 (Enumerated)**

| ID | Item                                          | Description |
|----|-----------------------------------------------|-------------|
| 1  | **http://doi.org/10.6028/NIST.SP.800-60v2r1** |             |

**********

The expected level of impact resulting from the described information.

**Type: Impact (Record)**

| ID | Name                         | Type                     | \#    | Description |
|----|------------------------------|--------------------------|-------|-------------|
| 1  | **props**                    | m:Property               | 0..\* |             |
| 2  | **links**                    | m:Link                   | 0..\* |             |
| 3  | **base**                     | Base                     | 1     |             |
| 4  | **selected**                 | Selected                 | 0..1  |             |
| 5  | **adjustment-justification** | Adjustment-justification | 0..1  |             |

**********

The prescribed base (Confidentiality, Integrity, or Availability) security impact level.

**Type: Base (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **alias** -  |

**********

The selected (Confidentiality, Integrity, or Availability) security impact level.

**Type: Selected (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **alias** -  |

**********

| Type Name                    | Type Definition | Description                                                                                                               |
|------------------------------|-----------------|---------------------------------------------------------------------------------------------------------------------------|
| **Adjustment-justification** | String          | If the selected security level is different from the base security level, this contains the justification for the change. |

**********

The overall level of expected impact resulting from unauthorized disclosure, modification, or loss of access to information.

**Type: Security-impact-level (Record)**

| ID | Name                                   | Type             | \# | Description                                                                                                  |
|----|----------------------------------------|------------------|----|--------------------------------------------------------------------------------------------------------------|
| 1  | **security-objective-confidentiality** | c:StringDatatype | 1  | A target-level of confidentiality for the system, based on the sensitivity of information within the system. |
| 2  | **security-objective-integrity**       | c:StringDatatype | 1  | A target-level of integrity for the system, based on the sensitivity of information within the system.       |
| 3  | **security-objective-availability**    | c:StringDatatype | 1  | A target-level of availability for the system, based on the sensitivity of information within the system.    |

**********

Describes the operational status of the system.

**Type: Status (Record)**

| ID | Name        | Type         | \#   | Description                   |
|----|-------------|--------------|------|-------------------------------|
| 1  | **state**   | Status.state | 1    | The current operating status. |
| 2  | **remarks** | m:Remarks    | 0..1 |                               |

**********

The current operating status.

**Type: Status.state (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **c1** -    |
| 2  | **** | Status.state.2   | 1  | **c2** -    |

**********

**Type: Status.state.2 (Enumerated)**

| ID | Item                         | Description |
|----|------------------------------|-------------|
| 1  | **operational**              |             |
| 2  | **under-development**        |             |
| 3  | **under-major-modification** |             |
| 4  | **disposition**              |             |
| 5  | **other**                    |             |

**********

A description of this system's authorization boundary, optionally supplemented by diagrams that illustrate the authorization boundary.

**Type: Authorization-boundary (Record)**

| ID | Name            | Type       | \#    | Description                                       |
|----|-----------------|------------|-------|---------------------------------------------------|
| 1  | **description** | String     | 1     | A summary of the system's authorization boundary. |
| 2  | **props**       | m:Property | 0..\* |                                                   |
| 3  | **links**       | m:Link     | 0..\* |                                                   |
| 4  | **diagrams**    | Diagram    | 0..\* |                                                   |
| 5  | **remarks**     | m:Remarks  | 0..1  |                                                   |

**********

A graphic that provides a visual representation the system, or some aspect of it.

**Type: Diagram (Record)**

| ID | Name            | Type           | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|----|-----------------|----------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**        | c:UUIDDatatype | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this diagram elsewhere in this or other OSCAL instances. The locally defined UUID of the diagram can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **description** | String         | 0..1  | A summary of the diagram.                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 3  | **props**       | m:Property     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 4  | **links**       | m:Link         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 5  | **caption**     | String         | 0..1  | A brief caption to annotate the diagram.                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 6  | **remarks**     | m:Remarks      | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

**********

A description of the system's network architecture, optionally supplemented by diagrams that illustrate the network architecture.

**Type: Network-architecture (Record)**

| ID | Name            | Type       | \#    | Description                                     |
|----|-----------------|------------|-------|-------------------------------------------------|
| 1  | **description** | String     | 1     | A summary of the system's network architecture. |
| 2  | **props**       | m:Property | 0..\* |                                                 |
| 3  | **links**       | m:Link     | 0..\* |                                                 |
| 4  | **diagrams**    | Diagram    | 0..\* |                                                 |
| 5  | **remarks**     | m:Remarks  | 0..1  |                                                 |

**********

A description of the logical flow of information within the system and across its boundaries, optionally supplemented by diagrams that illustrate these flows.

**Type: Data-flow (Record)**

| ID | Name            | Type       | \#    | Description                          |
|----|-----------------|------------|-------|--------------------------------------|
| 1  | **description** | String     | 1     | A summary of the system's data flow. |
| 2  | **props**       | m:Property | 0..\* |                                      |
| 3  | **links**       | m:Link     | 0..\* |                                      |
| 4  | **diagrams**    | Diagram    | 0..\* |                                      |
| 5  | **remarks**     | m:Remarks  | 0..1  |                                      |

**********

Provides information as to how the system is implemented.

**Type: System-implementation (Record)**

| ID | Name                         | Type                                           | \#    | Description |
|----|------------------------------|------------------------------------------------|-------|-------------|
| 1  | **props**                    | m:Property                                     | 0..\* |             |
| 2  | **links**                    | m:Link                                         | 0..\* |             |
| 3  | **leveraged-authorizations** | System-implementation.leveraged-authorizations | 0..\* |             |
| 4  | **users**                    | ic:System-user                                 | 1..\* |             |
| 5  | **components**               | ic:System-component                            | 1..\* |             |
| 6  | **inventory-items**          | ic:Inventory-item                              | 0..\* |             |
| 7  | **remarks**                  | m:Remarks                                      | 0..1  |             |

**********

A description of another authorized system from which this system inherits capabilities that satisfy security requirements. Another term for this concept is a common control provider.

**Type: System-implementation.leveraged-authorizations (Record)**

| ID | Name                | Type            | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|----|---------------------|-----------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**            | c:UUIDDatatype  | 1     | A machine-oriented, globally unique identifier with cross-instance scope and can be used to reference this leveraged authorization elsewhere in this or other OSCAL instances. The locally defined UUID of the leveraged authorization can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**           | String          | 1     | A human readable name for the leveraged authorization in the context of the system.                                                                                                                                                                                                                                                                                                                                                                                                          |
| 3  | **props**           | m:Property      | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 4  | **links**           | m:Link          | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 5  | **party-uuid**      | c:UUIDDatatype  | 1     | A machine-oriented identifier reference to the party that manages the leveraged system.                                                                                                                                                                                                                                                                                                                                                                                                      |
| 6  | **date-authorized** | Date-authorized | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 7  | **remarks**         | m:Remarks       | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

**********

Describes how the system satisfies a set of controls.

**Type: Control-implementation (Record)**

| ID | Name                         | Type                    | \#    | Description                                                                                                             |
|----|------------------------------|-------------------------|-------|-------------------------------------------------------------------------------------------------------------------------|
| 1  | **description**              | String                  | 1     | A statement describing important things to know about how this set of control satisfaction documentation is approached. |
| 2  | **set-parameters**           | ic:Set-parameter        | 0..\* |                                                                                                                         |
| 3  | **implemented-requirements** | Implemented-requirement | 1..\* |                                                                                                                         |

**********

Describes how the system satisfies the requirements of an individual control.

**Type: Implemented-requirement (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|----|-----------------------|--------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this control requirement elsewhere in this or other OSCAL instances. The locally defined UUID of the control requirement can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **control-id**        | c:TokenDatatype    | 1     | A reference to a control with a corresponding id value. When referencing an externally defined control, the Control Identifier Reference must be used in the context of the external / imported OSCAL instance (e.g., uri-reference).                                                                                                                                                                                                                                                 |
| 3  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 4  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 5  | **set-parameters**    | ic:Set-parameter   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 6  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 7  | **statements**        | Statement          | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 8  | **by-components**     | By-component       | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 9  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

**********

Identifies which statements within a control are addressed.

**Type: Statement (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                  |
|----|-----------------------|--------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **statement-id**      | c:TokenDatatype    | 1     | A human-oriented identifier reference to a control statement.                                                                                                                                                                                                                                                                                |
| 2  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this control statement elsewhere in this or other OSCAL instances. The UUID of the control statement in the source OSCAL instance is sufficient to reference the data item locally or globally (e.g., in an imported OSCAL instance). |
| 3  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                              |
| 4  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                              |
| 5  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                              |
| 6  | **by-components**     | By-component       | 0..\* |                                                                                                                                                                                                                                                                                                                                              |
| 7  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                              |

**********

Defines how the referenced component implements a set of controls.

**Type: By-component (Record)**

| ID | Name                      | Type                     | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|----|---------------------------|--------------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **component-uuid**        | c:UUIDDatatype           | 1     | A machine-oriented identifier reference to the component that is implemeting a given control.                                                                                                                                                                                                                                                                                                                                                                                       |
| 2  | **uuid**                  | c:UUIDDatatype           | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this by-component entry elsewhere in this or other OSCAL instances. The locally defined UUID of the by-component entry can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 3  | **description**           | String                   | 1     | An implementation statement that describes how a control or a control statement is implemented within the referenced system component.                                                                                                                                                                                                                                                                                                                                              |
| 4  | **props**                 | m:Property               | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 5  | **links**                 | m:Link                   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 6  | **set-parameters**        | ic:Set-parameter         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 7  | **implementation-status** | ic:Implementation-status | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 8  | **export**                | By-component.export      | 0..1  | Identifies content intended for external consumption, such as with leveraged organizations.                                                                                                                                                                                                                                                                                                                                                                                         |
| 9  | **inherited**             | By-component.inherited   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 10 | **satisfied**             | By-component.satisfied   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 11 | **responsible-roles**     | m:Responsible-role       | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 12 | **remarks**               | m:Remarks                | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

**********

Identifies content intended for external consumption, such as with leveraged organizations.

**Type: By-component.export (Record)**

| ID | Name                 | Type                                 | \#    | Description                                                                                                                                                               |
|----|----------------------|--------------------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **description**      | String                               | 0..1  | An implementation statement that describes the aspects of the control or control statement implementation that can be available to another system leveraging this system. |
| 2  | **props**            | m:Property                           | 0..\* |                                                                                                                                                                           |
| 3  | **links**            | m:Link                               | 0..\* |                                                                                                                                                                           |
| 4  | **provided**         | By-component.export.provided         | 0..\* |                                                                                                                                                                           |
| 5  | **responsibilities** | By-component.export.responsibilities | 0..\* |                                                                                                                                                                           |
| 6  | **remarks**          | m:Remarks                            | 0..1  |                                                                                                                                                                           |

**********

Describes a capability which may be inherited by a leveraging system.

**Type: By-component.export.provided (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----|-----------------------|--------------------|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this provided entry elsewhere in this or other OSCAL instances. The locally defined UUID of the provided entry can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **description**       | String             | 1     | An implementation statement that describes the aspects of the control or control statement implementation that can be provided to another system leveraging this system.                                                                                                                                                                                                                                                                                                    |
| 3  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 4  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 5  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 6  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**********

Describes a control implementation responsibility imposed on a leveraging system.

**Type: By-component.export.responsibilities (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----|-----------------------|--------------------|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this responsibility elsewhere in this or other OSCAL instances. The locally defined UUID of the responsibility can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **provided-uuid**     | c:UUIDDatatype     | 0..1  | A machine-oriented identifier reference to an inherited control implementation that a leveraging system is inheriting from a leveraged system.                                                                                                                                                                                                                                                                                                                              |
| 3  | **description**       | String             | 1     | An implementation statement that describes the aspects of the control or control statement implementation that a leveraging system must implement to satisfy the control provided by a leveraged system.                                                                                                                                                                                                                                                                    |
| 4  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 5  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 6  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 7  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**********

Describes a control implementation inherited by a leveraging system.

**Type: By-component.inherited (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|----|-----------------------|--------------------|-------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this inherited entry elsewhere in this or other OSCAL instances. The locally defined UUID of the inherited control implementation can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **provided-uuid**     | c:UUIDDatatype     | 0..1  | A machine-oriented identifier reference to an inherited control implementation that a leveraging system is inheriting from a leveraged system.                                                                                                                                                                                                                                                                                                                                                 |
| 3  | **description**       | String             | 1     | An implementation statement that describes the aspects of a control or control statement implementation that a leveraging system is inheriting from a leveraged system.                                                                                                                                                                                                                                                                                                                        |
| 4  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 5  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 6  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

**********

Describes how this system satisfies a responsibility imposed by a leveraged system.

**Type: By-component.satisfied (Record)**

| ID | Name                    | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----|-------------------------|--------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this satisfied control implementation entry elsewhere in this or other OSCAL instances. The locally defined UUID of the control implementation can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **responsibility-uuid** | c:UUIDDatatype     | 0..1  | A machine-oriented identifier reference to a control implementation that satisfies a responsibility imposed by a leveraged system.                                                                                                                                                                                                                                                                                                                                                                          |
| 3  | **description**         | String             | 1     | An implementation statement that describes the aspects of a control or control statement implementation that a leveraging system is implementing based on a requirement from a leveraged system.                                                                                                                                                                                                                                                                                                            |
| 4  | **props**               | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 5  | **links**               | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 6  | **responsible-roles**   | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 7  | **remarks**             | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**********
