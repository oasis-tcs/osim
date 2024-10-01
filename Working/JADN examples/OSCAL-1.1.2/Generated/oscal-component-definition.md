       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-component-definition"
    namespaces: [["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"], ["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["ic", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-implementation-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Component-definition"]
       comment: "OSCAL Component Definition Model: JSON Schema"

A collection of component descriptions, which may optionally be grouped by capability.

**Type: Component-definition (Record)**

| ID | Name                             | Type                        | \#    | Description                                                                         |
|----|----------------------------------|-----------------------------|-------|-------------------------------------------------------------------------------------|
| 1  | **uuid**                         | c:UUIDDatatype              | 1     | Provides a globally unique means to identify a given component definition instance. |
| 2  | **metadata**                     | m:Metadata                  | 1     |                                                                                     |
| 3  | **import-component-definitions** | Import-component-definition | 0..\* |                                                                                     |
| 4  | **components**                   | Defined-component           | 0..\* |                                                                                     |
| 5  | **capabilities**                 | Capability                  | 0..\* |                                                                                     |
| 6  | **back-matter**                  | m:Back-matter               | 0..1  |                                                                                     |

**********

Loads a component definition from another resource.

**Type: Import-component-definition (Record)**

| ID | Name     | Type                   | \# | Description                                                                                               |
|----|----------|------------------------|----|-----------------------------------------------------------------------------------------------------------|
| 1  | **href** | c:URIReferenceDatatype | 1  | A link to a resource that defines a set of components and/or capabilities to import into this collection. |

**********

A defined component that can be part of an implemented system.

**Type: Defined-component (Record)**

| ID | Name                        | Type                   | \#    | Description                                                               |
|----|-----------------------------|------------------------|-------|---------------------------------------------------------------------------|
| 1  | **uuid**                    | c:UUIDDatatype         | 1     | Provides a globally unique means to identify a given component.           |
| 2  | **type**                    | Defined-component.type | 1     | A category describing the purpose of the component.                       |
| 3  | **title**                   | String                 | 1     | A human readable name for the component.                                  |
| 4  | **description**             | String                 | 1     | A description of the component, including information about its function. |
| 5  | **purpose**                 | String                 | 0..1  | A summary of the technological or business purpose of the component.      |
| 6  | **props**                   | m:Property             | 0..\* |                                                                           |
| 7  | **links**                   | m:Link                 | 0..\* |                                                                           |
| 8  | **responsible-roles**       | m:Responsible-role     | 0..\* |                                                                           |
| 9  | **protocols**               | ic:Protocol            | 0..\* |                                                                           |
| 10 | **control-implementations** | Control-implementation | 0..\* |                                                                           |
| 11 | **remarks**                 | m:Remarks              | 0..1  |                                                                           |

**********

A category describing the purpose of the component.

**Type: Defined-component.type (Choice(anyOf))**

| ID | Name | Type                     | \# | Description |
|----|------|--------------------------|----|-------------|
| 1  | **** | c:StringDatatype         | 1  | **c1** -    |
| 2  | **** | Defined-component.type.2 | 1  | **c2** -    |

**********

**Type: Defined-component.type.2 (Enumerated)**

| ID | Item                  | Description |
|----|-----------------------|-------------|
| 1  | **interconnection**   |             |
| 2  | **software**          |             |
| 3  | **hardware**          |             |
| 4  | **service**           |             |
| 5  | **policy**            |             |
| 6  | **physical**          |             |
| 7  | **process-procedure** |             |
| 8  | **plan**              |             |
| 9  | **guidance**          |             |
| 10 | **standard**          |             |
| 11 | **validation**        |             |

**********

Defines how the component or capability supports a set of controls.

**Type: Control-implementation (Record)**

| ID | Name                         | Type                    | \#    | Description                                                                                                          |
|----|------------------------------|-------------------------|-------|----------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                     | c:UUIDDatatype          | 1     | Provides a means to identify a set of control implementations that are supported by a given component or capability. |
| 2  | **source**                   | c:URIReferenceDatatype  | 1     | A reference to an OSCAL catalog or profile providing the referenced control or subcontrol definition.                |
| 3  | **description**              | String                  | 1     | A description of how the specified set of controls are implemented for the containing component or capability.       |
| 4  | **props**                    | m:Property              | 0..\* |                                                                                                                      |
| 5  | **links**                    | m:Link                  | 0..\* |                                                                                                                      |
| 6  | **set-parameters**           | ic:Set-parameter        | 0..\* |                                                                                                                      |
| 7  | **implemented-requirements** | Implemented-requirement | 1..\* |                                                                                                                      |

**********

Describes how the containing component or capability implements an individual control.

**Type: Implemented-requirement (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                           |
|----|-----------------------|--------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype     | 1     | Provides a globally unique means to identify a given control implementation by a component.                                                                                                                                           |
| 2  | **control-id**        | c:TokenDatatype    | 1     | A reference to a control with a corresponding id value. When referencing an externally defined control, the Control Identifier Reference must be used in the context of the external / imported OSCAL instance (e.g., uri-reference). |
| 3  | **description**       | String             | 1     | A suggestion from the supplier (e.g., component vendor or author) for how the specified control may be implemented if the containing component or capability is instantiated in a system security plan.                               |
| 4  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                       |
| 5  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                       |
| 6  | **set-parameters**    | ic:Set-parameter   | 0..\* |                                                                                                                                                                                                                                       |
| 7  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                       |
| 8  | **statements**        | Statement          | 0..\* |                                                                                                                                                                                                                                       |
| 9  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                       |

**********

Identifies which statements within a control are addressed.

**Type: Statement (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                  |
|----|-----------------------|--------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **statement-id**      | c:TokenDatatype    | 1     | A human-oriented identifier reference to a control statement.                                                                                                                                                                                                                                                                                |
| 2  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this control statement elsewhere in this or other OSCAL instances. The UUID of the control statement in the source OSCAL instance is sufficient to reference the data item locally or globally (e.g., in an imported OSCAL instance). |
| 3  | **description**       | String             | 1     | A summary of how the containing control statement is implemented by the component or capability.                                                                                                                                                                                                                                             |
| 4  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                              |
| 5  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                              |
| 6  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                              |
| 7  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                              |

**********

A grouping of other components and/or capabilities.

**Type: Capability (Record)**

| ID | Name                        | Type                   | \#    | Description                                                      |
|----|-----------------------------|------------------------|-------|------------------------------------------------------------------|
| 1  | **uuid**                    | c:UUIDDatatype         | 1     | Provides a globally unique means to identify a given capability. |
| 2  | **name**                    | c:StringDatatype       | 1     | The capability's human-readable name.                            |
| 3  | **description**             | String                 | 1     | A summary of the capability.                                     |
| 4  | **props**                   | m:Property             | 0..\* |                                                                  |
| 5  | **links**                   | m:Link                 | 0..\* |                                                                  |
| 6  | **incorporates-components** | Incorporates-component | 0..\* |                                                                  |
| 7  | **control-implementations** | Control-implementation | 0..\* |                                                                  |
| 8  | **remarks**                 | m:Remarks              | 0..1  |                                                                  |

**********

The collection of components comprising this capability.

**Type: Incorporates-component (Record)**

| ID | Name               | Type           | \# | Description                                                               |
|----|--------------------|----------------|----|---------------------------------------------------------------------------|
| 1  | **component-uuid** | c:UUIDDatatype | 1  | A machine-oriented identifier reference to a component.                   |
| 2  | **description**    | String         | 1  | A description of the component, including information about its function. |

**********
