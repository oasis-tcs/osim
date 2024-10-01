       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-implementation-common"
    namespaces: [["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"], ["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Implementation-status", "Inventory-item", "Set-parameter", "System-component", "System-id", "System-user"]

Indicates the degree to which the a given control is implemented.

**Type: Implementation-status (Record)**

| ID | Name        | Type                        | \#   | Description                                                               |
|----|-------------|-----------------------------|------|---------------------------------------------------------------------------|
| 1  | **state**   | Implementation-status.state | 1    | Identifies the implementation status of the control or control objective. |
| 2  | **remarks** | m:Remarks                   | 0..1 |                                                                           |

**********

Identifies the implementation status of the control or control objective.

**Type: Implementation-status.state (Choice(anyOf))**

| ID | Name | Type                          | \# | Description |
|----|------|-------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype               | 1  | **c1** -    |
| 2  | **** | Implementation-status.state.2 | 1  | **c2** -    |

**********

**Type: Implementation-status.state.2 (Enumerated)**

| ID | Item               | Description |
|----|--------------------|-------------|
| 1  | **implemented**    |             |
| 2  | **partial**        |             |
| 3  | **planned**        |             |
| 4  | **alternative**    |             |
| 5  | **not-applicable** |             |

**********

A single managed inventory item within the system.

**Type: Inventory-item (Record)**

| ID | Name                       | Type                                  | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----|----------------------------|---------------------------------------|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                   | c:UUIDDatatype                        | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this inventory item elsewhere in this or other OSCAL instances. The locally defined UUID of the inventory item can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **description**            | String                                | 1     | A summary of the inventory item stating its purpose within the system.                                                                                                                                                                                                                                                                                                                                                                                                      |
| 3  | **props**                  | m:Property                            | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 4  | **links**                  | m:Link                                | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 5  | **responsible-parties**    | m:Responsible-party                   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 6  | **implemented-components** | Inventory-item.implemented-components | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 7  | **remarks**                | m:Remarks                             | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**********

The set of components that are implemented in a given system inventory item.

**Type: Inventory-item.implemented-components (Record)**

| ID | Name                    | Type                | \#    | Description                                                                                              |
|----|-------------------------|---------------------|-------|----------------------------------------------------------------------------------------------------------|
| 1  | **component-uuid**      | c:UUIDDatatype      | 1     | A machine-oriented identifier reference to a component that is implemented as part of an inventory item. |
| 2  | **props**               | m:Property          | 0..\* |                                                                                                          |
| 3  | **links**               | m:Link              | 0..\* |                                                                                                          |
| 4  | **responsible-parties** | m:Responsible-party | 0..\* |                                                                                                          |
| 5  | **remarks**             | m:Remarks           | 0..1  |                                                                                                          |

**********

Identifies the parameter that will be set by the enclosed value.

**Type: Set-parameter (Record)**

| ID | Name         | Type             | \#    | Description                                                                                                                          |
|----|--------------|------------------|-------|--------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **param-id** | c:TokenDatatype  | 1     | A human-oriented reference to a parameter within a control, who's catalog has been imported into the current implementation context. |
| 2  | **values**   | c:StringDatatype | 1..\* |                                                                                                                                      |
| 3  | **remarks**  | m:Remarks        | 0..1  |                                                                                                                                      |

**********

A defined component that can be part of an implemented system.

**Type: System-component (Record)**

| ID | Name                  | Type                    | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|----|-----------------------|-------------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype          | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this component elsewhere in this or other OSCAL instances. The locally defined UUID of the component can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **type**              | System-component.type   | 1     | A category describing the purpose of the component.                                                                                                                                                                                                                                                                                                                                                                                                               |
| 3  | **title**             | String                  | 1     | A human readable name for the system component.                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 4  | **description**       | String                  | 1     | A description of the component, including information about its function.                                                                                                                                                                                                                                                                                                                                                                                         |
| 5  | **purpose**           | String                  | 0..1  | A summary of the technological or business purpose of the component.                                                                                                                                                                                                                                                                                                                                                                                              |
| 6  | **props**             | m:Property              | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 7  | **links**             | m:Link                  | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 8  | **status**            | System-component.status | 1     | Describes the operational status of the system component.                                                                                                                                                                                                                                                                                                                                                                                                         |
| 9  | **responsible-roles** | m:Responsible-role      | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 10 | **protocols**         | Protocol                | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 11 | **remarks**           | m:Remarks               | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

**********

A category describing the purpose of the component.

**Type: System-component.type (Choice(anyOf))**

| ID | Name | Type                    | \# | Description |
|----|------|-------------------------|----|-------------|
| 1  | **** | c:StringDatatype        | 1  | **c1** -    |
| 2  | **** | System-component.type.2 | 1  | **c2** -    |

**********

**Type: System-component.type.2 (Enumerated)**

| ID | Item                  | Description |
|----|-----------------------|-------------|
| 1  | **this-system**       |             |
| 2  | **system**            |             |
| 3  | **interconnection**   |             |
| 4  | **software**          |             |
| 5  | **hardware**          |             |
| 6  | **service**           |             |
| 7  | **policy**            |             |
| 8  | **physical**          |             |
| 9  | **process-procedure** |             |
| 10 | **plan**              |             |
| 11 | **guidance**          |             |
| 12 | **standard**          |             |
| 13 | **validation**        |             |
| 14 | **network**           |             |

**********

Describes the operational status of the system component.

**Type: System-component.status (Record)**

| ID | Name        | Type                          | \#   | Description             |
|----|-------------|-------------------------------|------|-------------------------|
| 1  | **state**   | System-component.status.state | 1    | The operational status. |
| 2  | **remarks** | m:Remarks                     | 0..1 |                         |

**********

The operational status.

**Type: System-component.status.state (Choice(allOf))**

| ID | Name | Type                            | \# | Description |
|----|------|---------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype                 | 1  | **c1** -    |
| 2  | **** | System-component.status.state.2 | 1  | **c2** -    |

**********

**Type: System-component.status.state.2 (Enumerated)**

| ID | Item                  | Description |
|----|-----------------------|-------------|
| 1  | **under-development** |             |
| 2  | **operational**       |             |
| 3  | **disposition**       |             |
| 4  | **other**             |             |

**********

Information about the protocol used to provide a service.

**Type: Protocol (Record)**

| ID | Name            | Type             | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----|-----------------|------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**        | c:UUIDDatatype   | 0..1  | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this service protocol information elsewhere in this or other OSCAL instances. The locally defined UUID of the service protocol can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **name**        | c:StringDatatype | 1     | The common name of the protocol, which should be the appropriate "service name" from the IANA Service Name and Transport Protocol Port Number Registry.                                                                                                                                                                                                                                                                                                                                     |
| 3  | **title**       | String           | 0..1  | A human readable name for the protocol (e.g., Transport Layer Security).                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 4  | **port-ranges** | Port-range       | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**********

Where applicable this is the IPv4 port range on which the service operates.

**Type: Port-range (Record)**

| ID | Name          | Type                         | \#   | Description                                        |
|----|---------------|------------------------------|------|----------------------------------------------------|
| 1  | **start**     | c:NonNegativeIntegerDatatype | 0..1 | Indicates the starting port number in a port range |
| 2  | **end**       | c:NonNegativeIntegerDatatype | 0..1 | Indicates the ending port number in a port range   |
| 3  | **transport** | Port-range.transport         | 0..1 | Indicates the transport type.                      |

**********

Indicates the transport type.

**Type: Port-range.transport (Choice(allOf))**

| ID | Name | Type                   | \# | Description |
|----|------|------------------------|----|-------------|
| 1  | **** | c:TokenDatatype        | 1  | **c1** -    |
| 2  | **** | Port-range.transport.2 | 1  | **c2** -    |

**********

**Type: Port-range.transport.2 (Enumerated)**

| ID | Item    | Description |
|----|---------|-------------|
| 1  | **TCP** |             |
| 2  | **UDP** |             |

**********

A human-oriented, globally unique identifier with cross-instance scope that can be used to reference this system identification property elsewhere in this or other OSCAL instances. When referencing an externally defined system identification, the system identification must be used in the context of the external / imported OSCAL instance (e.g., uri-reference). This string should be assigned per-subject, which means it should be consistently used to identify the same system across revisions of the document.

**Type: System-id (Record)**

| ID | Name                | Type                      | \#   | Description                                                                           |
|----|---------------------|---------------------------|------|---------------------------------------------------------------------------------------|
| 1  | **identifier-type** | System-id.identifier-type | 0..1 | Identifies the identification system from which the provided identifier was assigned. |
| 2  | **id**              | c:StringDatatype          | 1    |                                                                                       |

**********

Identifies the identification system from which the provided identifier was assigned.

**Type: System-id.identifier-type (Choice(anyOf))**

| ID | Name | Type                        | \# | Description |
|----|------|-----------------------------|----|-------------|
| 1  | **** | c:URIDatatype               | 1  | **c1** -    |
| 2  | **** | System-id.identifier-type.2 | 1  | **c2** -    |

**********

**Type: System-id.identifier-type.2 (Enumerated)**

| ID | Item                             | Description |
|----|----------------------------------|-------------|
| 1  | **https://fedramp.gov**          |             |
| 2  | **http://fedramp.gov/ns/oscal**  |             |
| 3  | **https://ietf.org/rfc/rfc4122** |             |
| 4  | **http://ietf.org/rfc/rfc4122**  |             |

**********

A type of user that interacts with the system based on an associated role.

**Type: System-user (Record)**

| ID | Name                      | Type                 | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|----|---------------------------|----------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                  | c:UUIDDatatype       | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this user class elsewhere in this or other OSCAL instances. The locally defined UUID of the system user can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**                 | String               | 0..1  | A name given to the user, which may be used by a tool for display and navigation.                                                                                                                                                                                                                                                                                                                                                                                    |
| 3  | **short-name**            | c:StringDatatype     | 0..1  | A short common name, abbreviation, or acronym for the user.                                                                                                                                                                                                                                                                                                                                                                                                          |
| 4  | **description**           | String               | 0..1  | A summary of the user's purpose within the system.                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 5  | **props**                 | m:Property           | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 6  | **links**                 | m:Link               | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 7  | **role-ids**              | m:Role-id            | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 8  | **authorized-privileges** | Authorized-privilege | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 9  | **remarks**               | m:Remarks            | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

**********

Identifies a specific system privilege held by the user, along with an associated description and/or rationale for the privilege.

**Type: Authorized-privilege (Record)**

| ID | Name                    | Type               | \#    | Description                                             |
|----|-------------------------|--------------------|-------|---------------------------------------------------------|
| 1  | **title**               | String             | 1     | A human readable name for the privilege.                |
| 2  | **description**         | String             | 0..1  | A summary of the privilege's purpose within the system. |
| 3  | **functions-performed** | Function-performed | 1..\* |                                                         |

**********

Describes a function performed for a given authorized privilege by this user class.

**Type: Function-performed (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **alias** -  |

**********
