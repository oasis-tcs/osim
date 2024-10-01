       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-assessment-common"
    namespaces: [["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"], ["ic", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-implementation-common"], ["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Activity", "Assessment-assets", "Assessment-method", "Assessment-subject-placeholder", "Finding", "Import-ssp", "Local-objective", "Observation", "Risk"]

Identifies an assessment or related process that can be performed. In the assessment plan, this is an intended activity which may be associated with an assessment task. In the assessment results, this an activity that was actually performed as part of an assessment.

**Type: Activity (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----|-----------------------|--------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this assessment activity elsewhere in this or other OSCAL instances. The locally defined UUID of the activity can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**             | String             | 0..1  | The title for this included activity.                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 3  | **description**       | String             | 1     | A human-readable description of this included activity.                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 4  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| 5  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| 6  | **steps**             | Activity.steps     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| 7  | **related-controls**  | Reviewed-controls  | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| 8  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| 9  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

**********

Identifies an individual step in a series of steps related to an activity, such as an assessment test or examination procedure.

**Type: Activity.steps (Record)**

| ID | Name                  | Type               | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|----|-----------------------|--------------------|-------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype     | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this step elsewhere in this or other OSCAL instances. The locally defined UUID of the step (in a series of steps) can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**             | String             | 0..1  | The title for this step.                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 3  | **description**       | String             | 1     | A human-readable description of this step.                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 4  | **props**             | m:Property         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 5  | **links**             | m:Link             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 6  | **reviewed-controls** | Reviewed-controls  | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 7  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 8  | **remarks**           | m:Remarks          | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

**********

Identifies the controls being assessed and their control objectives.

**Type: Reviewed-controls (Record)**

| ID | Name                             | Type                                           | \#    | Description                                         |
|----|----------------------------------|------------------------------------------------|-------|-----------------------------------------------------|
| 1  | **description**                  | String                                         | 0..1  | A human-readable description of control objectives. |
| 2  | **props**                        | m:Property                                     | 0..\* |                                                     |
| 3  | **links**                        | m:Link                                         | 0..\* |                                                     |
| 4  | **control-selections**           | Reviewed-controls.control-selections           | 1..\* |                                                     |
| 5  | **control-objective-selections** | Reviewed-controls.control-objective-selections | 0..\* |                                                     |
| 6  | **remarks**                      | m:Remarks                                      | 0..1  |                                                     |

**********

Identifies the controls being assessed. In the assessment plan, these are the planned controls. In the assessment results, these are the actual controls, and reflects any changes from the plan.

**Type: Reviewed-controls.control-selections (Record)**

| ID | Name                 | Type                 | \#    | Description                                                                 |
|----|----------------------|----------------------|-------|-----------------------------------------------------------------------------|
| 1  | **description**      | String               | 0..1  | A human-readable description of in-scope controls specified for assessment. |
| 2  | **props**            | m:Property           | 0..\* |                                                                             |
| 3  | **links**            | m:Link               | 0..\* |                                                                             |
| 4  | **include-all**      | cc:Include-all       | 0..1  |                                                                             |
| 5  | **include-controls** | Select-control-by-id | 0..\* |                                                                             |
| 6  | **exclude-controls** | Select-control-by-id | 0..\* |                                                                             |
| 7  | **remarks**          | m:Remarks            | 0..1  |                                                                             |

**********

Used to select a control for inclusion/exclusion based on one or more control identifiers. A set of statement identifiers can be used to target the inclusion/exclusion to only specific control statements providing more granularity over the specific statements that are within the asessment scope.

**Type: Select-control-by-id (Record)**

| ID | Name              | Type            | \#    | Description                                                                                                                                                                                                                           |
|----|-------------------|-----------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **control-id**    | c:TokenDatatype | 1     | A reference to a control with a corresponding id value. When referencing an externally defined control, the Control Identifier Reference must be used in the context of the external / imported OSCAL instance (e.g., uri-reference). |
| 2  | **statement-ids** | c:TokenDatatype | 0..\* |                                                                                                                                                                                                                                       |

**********

Identifies the control objectives of the assessment. In the assessment plan, these are the planned objectives. In the assessment results, these are the assessed objectives, and reflects any changes from the plan.

**Type: Reviewed-controls.control-objective-selections (Record)**

| ID | Name                   | Type                   | \#    | Description                                                            |
|----|------------------------|------------------------|-------|------------------------------------------------------------------------|
| 1  | **description**        | String                 | 0..1  | A human-readable description of this collection of control objectives. |
| 2  | **props**              | m:Property             | 0..\* |                                                                        |
| 3  | **links**              | m:Link                 | 0..\* |                                                                        |
| 4  | **include-all**        | cc:Include-all         | 0..1  |                                                                        |
| 5  | **include-objectives** | Select-objective-by-id | 0..\* |                                                                        |
| 6  | **exclude-objectives** | Select-objective-by-id | 0..\* |                                                                        |
| 7  | **remarks**            | m:Remarks              | 0..1  |                                                                        |

**********

Used to select a control objective for inclusion/exclusion based on the control objective's identifier.

**Type: Select-objective-by-id (Record)**

| ID | Name             | Type            | \# | Description                        |
|----|------------------|-----------------|----|------------------------------------|
| 1  | **objective-id** | c:TokenDatatype | 1  | Points to an assessment objective. |

**********

Identifies the assets used to perform this assessment, such as the assessment team, scanning tools, and assumptions.

**Type: Assessment-assets (Record)**

| ID | Name                     | Type                                   | \#    | Description |
|----|--------------------------|----------------------------------------|-------|-------------|
| 1  | **components**           | ic:System-component                    | 0..\* |             |
| 2  | **assessment-platforms** | Assessment-assets.assessment-platforms | 1..\* |             |

**********

Used to represent the toolset used to perform aspects of the assessment.

**Type: Assessment-assets.assessment-platforms (Record)**

| ID | Name                | Type                                                   | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|----|---------------------|--------------------------------------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**            | c:UUIDDatatype                                         | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this assessment platform elsewhere in this or other OSCAL instances. The locally defined UUID of the assessment platform can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**           | String                                                 | 0..1  | The title or name for the assessment platform.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| 3  | **props**           | m:Property                                             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 4  | **links**           | m:Link                                                 | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 5  | **uses-components** | Assessment-assets.assessment-platforms.uses-components | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 6  | **remarks**         | m:Remarks                                              | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

**********

The set of components that are used by the assessment platform.

**Type: Assessment-assets.assessment-platforms.uses-components (Record)**

| ID | Name                    | Type                | \#    | Description                                                                                              |
|----|-------------------------|---------------------|-------|----------------------------------------------------------------------------------------------------------|
| 1  | **component-uuid**      | c:UUIDDatatype      | 1     | A machine-oriented identifier reference to a component that is implemented as part of an inventory item. |
| 2  | **props**               | m:Property          | 0..\* |                                                                                                          |
| 3  | **links**               | m:Link              | 0..\* |                                                                                                          |
| 4  | **responsible-parties** | m:Responsible-party | 0..\* |                                                                                                          |
| 5  | **remarks**             | m:Remarks           | 0..1  |                                                                                                          |

**********

A local definition of a control objective. Uses catalog syntax for control objective and assessment activities.

**Type: Assessment-method (Record)**

| ID | Name            | Type            | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|----|-----------------|-----------------|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**        | c:UUIDDatatype  | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this assessment method elsewhere in this or other OSCAL instances. The locally defined UUID of the assessment method can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **description** | String          | 0..1  | A human-readable description of this assessment method.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| 3  | **props**       | m:Property      | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 4  | **links**       | m:Link          | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 5  | **part**        | Assessment-part | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 6  | **remarks**     | m:Remarks       | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

**********

A partition of an assessment plan or results or a child of another part.

**Type: Assessment-part (Record)**

| ID | Name      | Type                 | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|----|-----------|----------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**  | c:UUIDDatatype       | 0..1  | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this part elsewhere in this or other OSCAL instances. The locally defined UUID of the part can be used to reference the data item locally or globally (e.g., in an ported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **name**  | Assessment-part.name | 1     | A textual label that uniquely identifies the part's semantic type.                                                                                                                                                                                                                                                                                                                                                                                    |
| 3  | **ns**    | c:URIDatatype        | 0..1  | A namespace qualifying the part's name. This allows different organizations to associate distinct semantics with the same name.                                                                                                                                                                                                                                                                                                                       |
| 4  | **class** | c:TokenDatatype      | 0..1  | A textual label that provides a sub-type or characterization of the part's name. This can be used to further distinguish or discriminate between the semantics of multiple parts of the same control with the same name and ns.                                                                                                                                                                                                                       |
| 5  | **title** | String               | 0..1  | A name given to the part, which may be used by a tool for display and navigation.                                                                                                                                                                                                                                                                                                                                                                     |
| 6  | **props** | m:Property           | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 7  | **prose** | String               | 0..1  | Permits multiple paragraphs, lists, tables etc.                                                                                                                                                                                                                                                                                                                                                                                                       |
| 8  | **parts** | Assessment-part      | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 9  | **links** | m:Link               | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

**********

A textual label that uniquely identifies the part's semantic type.

**Type: Assessment-part.name (Choice(anyOf))**

| ID | Name | Type                   | \# | Description |
|----|------|------------------------|----|-------------|
| 1  | **** | c:TokenDatatype        | 1  | **c1** -    |
| 2  | **** | Assessment-part.name.2 | 1  | **c2** -    |

**********

**Type: Assessment-part.name.2 (Enumerated)**

| ID | Item          | Description |
|----|---------------|-------------|
| 1  | **asset**     |             |
| 2  | **method**    |             |
| 3  | **objective** |             |

**********

Used when the assessment subjects will be determined as part of one or more other assessment activities. These assessment subjects will be recorded in the assessment results in the assessment log.

**Type: Assessment-subject-placeholder (Record)**

| ID | Name            | Type                                   | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|----|-----------------|----------------------------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**        | c:UUIDDatatype                         | 1     | A machine-oriented, globally unique identifier for a set of assessment subjects that will be identified by a task or an activity that is part of a task. The locally defined UUID of the assessment subject placeholder can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **description** | String                                 | 0..1  | A human-readable description of intent of this assessment subject placeholder.                                                                                                                                                                                                                                                                                                                                                                                                |
| 3  | **sources**     | Assessment-subject-placeholder.sources | 1..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 4  | **props**       | m:Property                             | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 5  | **links**       | m:Link                                 | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 6  | **remarks**     | m:Remarks                              | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

**********

Assessment subjects will be identified while conducting the referenced activity-instance.

**Type: Assessment-subject-placeholder.sources (Record)**

| ID | Name          | Type           | \# | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|----|---------------|----------------|----|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **task-uuid** | c:UUIDDatatype | 1  | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference (in this or other OSCAL instances) an assessment activity to be performed as part of the event. The locally defined UUID of the task can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |

**********

Describes an individual finding.

**Type: Finding (Record)**

| ID | Name                              | Type                         | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|----|-----------------------------------|------------------------------|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                          | c:UUIDDatatype               | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this finding in this or other OSCAL instances. The locally defined UUID of the finding can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**                         | String                       | 1     | The title for this finding.                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 3  | **description**                   | String                       | 1     | A human-readable description of this finding.                                                                                                                                                                                                                                                                                                                                                                                                       |
| 4  | **props**                         | m:Property                   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 5  | **links**                         | m:Link                       | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 6  | **origins**                       | Origin                       | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 7  | **target**                        | Finding-target               | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 8  | **implementation-statement-uuid** | c:UUIDDatatype               | 0..1  | A machine-oriented identifier reference to the implementation statement in the SSP to which this finding is related.                                                                                                                                                                                                                                                                                                                                |
| 9  | **related-observations**          | Finding.related-observations | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 10 | **related-risks**                 | Finding.related-risks        | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 11 | **remarks**                       | m:Remarks                    | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

**********

Identifies the source of the finding, such as a tool, interviewed person, or activity.

**Type: Origin (Record)**

| ID | Name              | Type         | \#    | Description |
|----|-------------------|--------------|-------|-------------|
| 1  | **actors**        | Origin-actor | 1..\* |             |
| 2  | **related-tasks** | Related-task | 0..\* |             |

**********

The actor that produces an observation, a finding, or a risk. One or more actor type can be used to specify a person that is using a tool.

**Type: Origin-actor (Record)**

| ID | Name           | Type              | \#    | Description                                                                                 |
|----|----------------|-------------------|-------|---------------------------------------------------------------------------------------------|
| 1  | **type**       | Origin-actor.type | 1     | The kind of actor.                                                                          |
| 2  | **actor-uuid** | c:UUIDDatatype    | 1     | A machine-oriented identifier reference to the tool or person based on the associated type. |
| 3  | **role-id**    | c:TokenDatatype   | 0..1  | For a party, this can optionally be used to specify the role the actor was performing.      |
| 4  | **props**      | m:Property        | 0..\* |                                                                                             |
| 5  | **links**      | m:Link            | 0..\* |                                                                                             |

**********

The kind of actor.

**Type: Origin-actor.type (Choice(allOf))**

| ID | Name | Type                | \# | Description |
|----|------|---------------------|----|-------------|
| 1  | **** | c:TokenDatatype     | 1  | **c1** -    |
| 2  | **** | Origin-actor.type.2 | 1  | **c2** -    |

**********

**Type: Origin-actor.type.2 (Enumerated)**

| ID | Item                    | Description |
|----|-------------------------|-------------|
| 1  | **tool**                |             |
| 2  | **assessment-platform** |             |
| 3  | **party**               |             |

**********

Identifies an individual task for which the containing object is a consequence of.

**Type: Related-task (Record)**

| ID | Name                    | Type                            | \#    | Description                                                          |
|----|-------------------------|---------------------------------|-------|----------------------------------------------------------------------|
| 1  | **task-uuid**           | c:UUIDDatatype                  | 1     | A machine-oriented identifier reference to a unique task.            |
| 2  | **props**               | m:Property                      | 0..\* |                                                                      |
| 3  | **links**               | m:Link                          | 0..\* |                                                                      |
| 4  | **responsible-parties** | m:Responsible-party             | 0..\* |                                                                      |
| 5  | **subjects**            | Assessment-subject              | 0..\* |                                                                      |
| 6  | **identified-subject**  | Related-task.identified-subject | 0..1  | Used to detail assessment subjects that were identfied by this task. |
| 7  | **remarks**             | m:Remarks                       | 0..1  |                                                                      |

**********

Identifies system elements being assessed, such as components, inventory items, and locations. In the assessment plan, this identifies a planned assessment subject. In the assessment results this is an actual assessment subject, and reflects any changes from the plan. exactly what will be the focus of this assessment. Any subjects not identified in this way are out-of-scope.

**Type: Assessment-subject (Record)**

| ID | Name                 | Type                    | \#    | Description                                                                                                                                 |
|----|----------------------|-------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **type**             | Assessment-subject.type | 1     | Indicates the type of assessment subject, such as a component, inventory, item, location, or party represented by this selection statement. |
| 2  | **description**      | String                  | 0..1  | A human-readable description of the collection of subjects being included in this assessment.                                               |
| 3  | **props**            | m:Property              | 0..\* |                                                                                                                                             |
| 4  | **links**            | m:Link                  | 0..\* |                                                                                                                                             |
| 5  | **include-all**      | cc:Include-all          | 0..1  |                                                                                                                                             |
| 6  | **include-subjects** | Select-subject-by-id    | 0..\* |                                                                                                                                             |
| 7  | **exclude-subjects** | Select-subject-by-id    | 0..\* |                                                                                                                                             |
| 8  | **remarks**          | m:Remarks               | 0..1  |                                                                                                                                             |

**********

Indicates the type of assessment subject, such as a component, inventory, item, location, or party represented by this selection statement.

**Type: Assessment-subject.type (Choice(anyOf))**

| ID | Name | Type                      | \# | Description |
|----|------|---------------------------|----|-------------|
| 1  | **** | c:TokenDatatype           | 1  | **c1** -    |
| 2  | **** | Assessment-subject.type.2 | 1  | **c2** -    |

**********

**Type: Assessment-subject.type.2 (Enumerated)**

| ID | Item               | Description |
|----|--------------------|-------------|
| 1  | **component**      |             |
| 2  | **inventory-item** |             |
| 3  | **location**       |             |
| 4  | **party**          |             |
| 5  | **user**           |             |

**********

Identifies a set of assessment subjects to include/exclude by UUID.

**Type: Select-subject-by-id (Record)**

| ID | Name             | Type                      | \#    | Description                                                                                                                 |
|----|------------------|---------------------------|-------|-----------------------------------------------------------------------------------------------------------------------------|
| 1  | **subject-uuid** | c:UUIDDatatype            | 1     | A machine-oriented identifier reference to a component, inventory-item, location, party, user, or resource using it's UUID. |
| 2  | **type**         | Select-subject-by-id.type | 1     | Used to indicate the type of object pointed to by the uuid-ref within a subject.                                            |
| 3  | **props**        | m:Property                | 0..\* |                                                                                                                             |
| 4  | **links**        | m:Link                    | 0..\* |                                                                                                                             |
| 5  | **remarks**      | m:Remarks                 | 0..1  |                                                                                                                             |

**********

Used to indicate the type of object pointed to by the uuid-ref within a subject.

**Type: Select-subject-by-id.type (Choice(anyOf))**

| ID | Name | Type                        | \# | Description |
|----|------|-----------------------------|----|-------------|
| 1  | **** | c:TokenDatatype             | 1  | **c1** -    |
| 2  | **** | Select-subject-by-id.type.2 | 1  | **c2** -    |

**********

**Type: Select-subject-by-id.type.2 (Enumerated)**

| ID | Item               | Description |
|----|--------------------|-------------|
| 1  | **component**      |             |
| 2  | **inventory-item** |             |
| 3  | **location**       |             |
| 4  | **party**          |             |
| 5  | **user**           |             |
| 6  | **resource**       |             |

**********

Used to detail assessment subjects that were identfied by this task.

**Type: Related-task.identified-subject (Record)**

| ID | Name                         | Type               | \#    | Description                                                                                              |
|----|------------------------------|--------------------|-------|----------------------------------------------------------------------------------------------------------|
| 1  | **subject-placeholder-uuid** | c:UUIDDatatype     | 1     | A machine-oriented identifier reference to a unique assessment subject placeholder defined by this task. |
| 2  | **subjects**                 | Assessment-subject | 1..\* |                                                                                                          |

**********

Captures an assessor's conclusions regarding the degree to which an objective is satisfied.

**Type: Finding-target (Record)**

| ID | Name                      | Type                     | \#    | Description                                                                                                         |
|----|---------------------------|--------------------------|-------|---------------------------------------------------------------------------------------------------------------------|
| 1  | **type**                  | Finding-target.type      | 1     | Identifies the type of the target.                                                                                  |
| 2  | **target-id**             | c:TokenDatatype          | 1     | A machine-oriented identifier reference for a specific target qualified by the type.                                |
| 3  | **title**                 | String                   | 0..1  | The title for this objective status.                                                                                |
| 4  | **description**           | String                   | 0..1  | A human-readable description of the assessor's conclusions regarding the degree to which an objective is satisfied. |
| 5  | **props**                 | m:Property               | 0..\* |                                                                                                                     |
| 6  | **links**                 | m:Link                   | 0..\* |                                                                                                                     |
| 7  | **status**                | Finding-target.status    | 1     | A determination of if the objective is satisfied or not within a given system.                                      |
| 8  | **implementation-status** | ic:Implementation-status | 0..1  |                                                                                                                     |
| 9  | **remarks**               | m:Remarks                | 0..1  |                                                                                                                     |

**********

Identifies the type of the target.

**Type: Finding-target.type (Choice(allOf))**

| ID | Name | Type                  | \# | Description |
|----|------|-----------------------|----|-------------|
| 1  | **** | c:StringDatatype      | 1  | **c1** -    |
| 2  | **** | Finding-target.type.2 | 1  | **c2** -    |

**********

**Type: Finding-target.type.2 (Enumerated)**

| ID | Item             | Description |
|----|------------------|-------------|
| 1  | **statement-id** |             |
| 2  | **objective-id** |             |

**********

A determination of if the objective is satisfied or not within a given system.

**Type: Finding-target.status (Record)**

| ID | Name        | Type                         | \#   | Description                                                    |
|----|-------------|------------------------------|------|----------------------------------------------------------------|
| 1  | **state**   | Finding-target.status.state  | 1    | An indication as to whether the objective is satisfied or not. |
| 2  | **reason**  | Finding-target.status.reason | 0..1 | The reason the objective was given it's status.                |
| 3  | **remarks** | m:Remarks                    | 0..1 |                                                                |

**********

An indication as to whether the objective is satisfied or not.

**Type: Finding-target.status.state (Choice(allOf))**

| ID | Name | Type                          | \# | Description |
|----|------|-------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype               | 1  | **c1** -    |
| 2  | **** | Finding-target.status.state.2 | 1  | **c2** -    |

**********

**Type: Finding-target.status.state.2 (Enumerated)**

| ID | Item              | Description |
|----|-------------------|-------------|
| 1  | **satisfied**     |             |
| 2  | **not-satisfied** |             |

**********

The reason the objective was given it's status.

**Type: Finding-target.status.reason (Choice(anyOf))**

| ID | Name | Type                           | \# | Description |
|----|------|--------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype                | 1  | **c1** -    |
| 2  | **** | Finding-target.status.reason.2 | 1  | **c2** -    |

**********

**Type: Finding-target.status.reason.2 (Enumerated)**

| ID | Item      | Description |
|----|-----------|-------------|
| 1  | **pass**  |             |
| 2  | **fail**  |             |
| 3  | **other** |             |

**********

Relates the finding to a set of referenced observations that were used to determine the finding.

**Type: Finding.related-observations (Record)**

| ID | Name                 | Type           | \# | Description                                                                                    |
|----|----------------------|----------------|----|------------------------------------------------------------------------------------------------|
| 1  | **observation-uuid** | c:UUIDDatatype | 1  | A machine-oriented identifier reference to an observation defined in the list of observations. |

**********

Relates the finding to a set of referenced risks that were used to determine the finding.

**Type: Finding.related-risks (Record)**

| ID | Name          | Type           | \# | Description                                                                     |
|----|---------------|----------------|----|---------------------------------------------------------------------------------|
| 1  | **risk-uuid** | c:UUIDDatatype | 1  | A machine-oriented identifier reference to a risk defined in the list of risks. |

**********

Used by the assessment plan and POA&M to import information about the system.

**Type: Import-ssp (Record)**

| ID | Name        | Type                   | \#   | Description                                                                           |
|----|-------------|------------------------|------|---------------------------------------------------------------------------------------|
| 1  | **href**    | c:URIReferenceDatatype | 1    | A resolvable URL reference to the system security plan for the system being assessed. |
| 2  | **remarks** | m:Remarks              | 0..1 |                                                                                       |

**********

A local definition of a control objective for this assessment. Uses catalog syntax for control objective and assessment actions.

**Type: Local-objective (Record)**

| ID | Name            | Type            | \#    | Description                                                                                                                                                                                                                           |
|----|-----------------|-----------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **control-id**  | c:TokenDatatype | 1     | A reference to a control with a corresponding id value. When referencing an externally defined control, the Control Identifier Reference must be used in the context of the external / imported OSCAL instance (e.g., uri-reference). |
| 2  | **description** | String          | 0..1  | A human-readable description of this control objective.                                                                                                                                                                               |
| 3  | **props**       | m:Property      | 0..\* |                                                                                                                                                                                                                                       |
| 4  | **links**       | m:Link          | 0..\* |                                                                                                                                                                                                                                       |
| 5  | **parts**       | cc:Part         | 1..\* |                                                                                                                                                                                                                                       |
| 6  | **remarks**     | m:Remarks       | 0..1  |                                                                                                                                                                                                                                       |

**********

Describes an individual observation.

**Type: Observation (Record)**

| ID | Name                  | Type                           | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|----|-----------------------|--------------------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype                 | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this observation elsewhere in this or other OSCAL instances. The locally defined UUID of the observation can be used to reference the data item locally or globally (e.g., in an imorted OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**             | String                         | 0..1  | The title for this observation.                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 3  | **description**       | String                         | 1     | A human-readable description of this assessment observation.                                                                                                                                                                                                                                                                                                                                                                                                         |
| 4  | **props**             | m:Property                     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 5  | **links**             | m:Link                         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 6  | **methods**           | Observation.methods            | 1..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 7  | **types**             | Observation.types              | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 8  | **origins**           | Origin                         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 9  | **subjects**          | Subject-reference              | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 10 | **relevant-evidence** | Observation.relevant-evidence  | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 11 | **collected**         | c:DateTimeWithTimezoneDatatype | 1     | Date/time stamp identifying when the finding information was collected.                                                                                                                                                                                                                                                                                                                                                                                              |
| 12 | **expires**           | c:DateTimeWithTimezoneDatatype | 0..1  | Date/time identifying when the finding information is out-of-date and no longer valid. Typically used with continuous assessment scenarios.                                                                                                                                                                                                                                                                                                                          |
| 13 | **remarks**           | m:Remarks                      | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

**********

Identifies how the observation was made.

**Type: Observation.methods (Choice(anyOf))**

| ID | Name | Type                  | \# | Description |
|----|------|-----------------------|----|-------------|
| 1  | **** | c:StringDatatype      | 1  | **c1** -    |
| 2  | **** | Observation.methods.2 | 1  | **c2** -    |

**********

**Type: Observation.methods.2 (Enumerated)**

| ID | Item          | Description |
|----|---------------|-------------|
| 1  | **EXAMINE**   |             |
| 2  | **INTERVIEW** |             |
| 3  | **TEST**      |             |
| 4  | **UNKNOWN**   |             |

**********

Identifies the nature of the observation. More than one may be used to further qualify and enable filtering.

**Type: Observation.types (Choice(anyOf))**

| ID | Name | Type                | \# | Description |
|----|------|---------------------|----|-------------|
| 1  | **** | c:TokenDatatype     | 1  | **c1** -    |
| 2  | **** | Observation.types.2 | 1  | **c2** -    |

**********

**Type: Observation.types.2 (Enumerated)**

| ID | Item                    | Description |
|----|-------------------------|-------------|
| 1  | **ssp-statement-issue** |             |
| 2  | **control-objective**   |             |
| 3  | **mitigation**          |             |
| 4  | **finding**             |             |
| 5  | **historic**            |             |

**********

A human-oriented identifier reference to a resource. Use type to indicate whether the identified resource is a component, inventory item, location, user, or something else.

**Type: Subject-reference (Record)**

| ID | Name             | Type                   | \#    | Description                                                                                                                 |
|----|------------------|------------------------|-------|-----------------------------------------------------------------------------------------------------------------------------|
| 1  | **subject-uuid** | c:UUIDDatatype         | 1     | A machine-oriented identifier reference to a component, inventory-item, location, party, user, or resource using it's UUID. |
| 2  | **type**         | Subject-reference.type | 1     | Used to indicate the type of object pointed to by the uuid-ref within a subject.                                            |
| 3  | **title**        | String                 | 0..1  | The title or name for the referenced subject.                                                                               |
| 4  | **props**        | m:Property             | 0..\* |                                                                                                                             |
| 5  | **links**        | m:Link                 | 0..\* |                                                                                                                             |
| 6  | **remarks**      | m:Remarks              | 0..1  |                                                                                                                             |

**********

Used to indicate the type of object pointed to by the uuid-ref within a subject.

**Type: Subject-reference.type (Choice(anyOf))**

| ID | Name | Type                     | \# | Description |
|----|------|--------------------------|----|-------------|
| 1  | **** | c:TokenDatatype          | 1  | **c1** -    |
| 2  | **** | Subject-reference.type.2 | 1  | **c2** -    |

**********

**Type: Subject-reference.type.2 (Enumerated)**

| ID | Item               | Description |
|----|--------------------|-------------|
| 1  | **component**      |             |
| 2  | **inventory-item** |             |
| 3  | **location**       |             |
| 4  | **party**          |             |
| 5  | **user**           |             |
| 6  | **resource**       |             |

**********

Links this observation to relevant evidence.

**Type: Observation.relevant-evidence (Record)**

| ID | Name            | Type                   | \#    | Description                                      |
|----|-----------------|------------------------|-------|--------------------------------------------------|
| 1  | **href**        | c:URIReferenceDatatype | 0..1  | A resolvable URL reference to relevant evidence. |
| 2  | **description** | String                 | 1     | A human-readable description of this evidence.   |
| 3  | **props**       | m:Property             | 0..\* |                                                  |
| 4  | **links**       | m:Link                 | 0..\* |                                                  |
| 5  | **remarks**     | m:Remarks              | 0..1  |                                                  |

**********

An identified risk.

**Type: Risk (Record)**

| ID | Name                     | Type                           | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----|--------------------------|--------------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                 | c:UUIDDatatype                 | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this risk elsewhere in this or other OSCAL instances. The locally defined UUID of the risk can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**                | String                         | 1     | The title for this risk.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 3  | **description**          | String                         | 1     | A human-readable summary of the identified risk, to include a statement of how the risk impacts the system.                                                                                                                                                                                                                                                                                                                                             |
| 4  | **statement**            | String                         | 1     | An summary of impact for how the risk affects the system.                                                                                                                                                                                                                                                                                                                                                                                               |
| 5  | **props**                | m:Property                     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 6  | **links**                | m:Link                         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 7  | **status**               | Risk-status                    | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 8  | **origins**              | Origin                         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 9  | **threat-ids**           | Threat-id                      | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 10 | **characterizations**    | Characterization               | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 11 | **mitigating-factors**   | Risk.mitigating-factors        | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 12 | **deadline**             | c:DateTimeWithTimezoneDatatype | 0..1  | The date/time by which the risk must be resolved.                                                                                                                                                                                                                                                                                                                                                                                                       |
| 13 | **remediations**         | Response                       | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 14 | **risk-log**             | Risk.risk-log                  | 0..1  | A log of all risk-related tasks taken.                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 15 | **related-observations** | Risk.related-observations      | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**********

Describes the status of the associated risk.

**Type: Risk-status (Choice(anyOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | c:TokenDatatype | 1  | **c1** -    |
| 2  | **** | Risk-status.2   | 1  | **c2** -    |

**********

**Type: Risk-status.2 (Enumerated)**

| ID | Item                    | Description |
|----|-------------------------|-------------|
| 1  | **open**                |             |
| 2  | **investigating**       |             |
| 3  | **remediating**         |             |
| 4  | **deviation-requested** |             |
| 5  | **deviation-approved**  |             |
| 6  | **closed**              |             |

**********

A pointer, by ID, to an externally-defined threat.

**Type: Threat-id (Record)**

| ID | Name       | Type                   | \#   | Description                                                              |
|----|------------|------------------------|------|--------------------------------------------------------------------------|
| 1  | **system** | Threat-id.system       | 1    | Specifies the source of the threat information.                          |
| 2  | **href**   | c:URIReferenceDatatype | 0..1 | An optional location for the threat data, from which this ID originates. |
| 3  | **id**     | c:URIDatatype          | 1    |                                                                          |

**********

Specifies the source of the threat information.

**Type: Threat-id.system (Choice(anyOf))**

| ID | Name | Type               | \# | Description |
|----|------|--------------------|----|-------------|
| 1  | **** | c:URIDatatype      | 1  | **c1** -    |
| 2  | **** | Threat-id.system.2 | 1  | **c2** -    |

**********

**Type: Threat-id.system.2 (Enumerated)**

| ID | Item                            | Description |
|----|---------------------------------|-------------|
| 1  | **http://fedramp.gov**          |             |
| 2  | **http://fedramp.gov/ns/oscal** |             |

**********

A collection of descriptive data about the containing object from a specific origin.

**Type: Characterization (Record)**

| ID | Name       | Type                    | \#    | Description |
|----|------------|-------------------------|-------|-------------|
| 1  | **props**  | m:Property              | 0..\* |             |
| 2  | **links**  | m:Link                  | 0..\* |             |
| 3  | **origin** | Origin                  | 1     |             |
| 4  | **facets** | Characterization.facets | 1..\* |             |

**********

An individual characteristic that is part of a larger set produced by the same actor.

**Type: Characterization.facets (Record)**

| ID | Name        | Type                           | \#    | Description                                                                                                                                                                                                        |
|----|-------------|--------------------------------|-------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **name**    | c:TokenDatatype                | 1     | The name of the risk metric within the specified system.                                                                                                                                                           |
| 2  | **system**  | Characterization.facets.system | 1     | Specifies the naming system under which this risk metric is organized, which allows for the same names to be used in different systems controlled by different parties. This avoids the potential of a name clash. |
| 3  | **value**   | c:StringDatatype               | 1     | Indicates the value of the facet.                                                                                                                                                                                  |
| 4  | **props**   | m:Property                     | 0..\* |                                                                                                                                                                                                                    |
| 5  | **links**   | m:Link                         | 0..\* |                                                                                                                                                                                                                    |
| 6  | **remarks** | m:Remarks                      | 0..1  |                                                                                                                                                                                                                    |

**********

Specifies the naming system under which this risk metric is organized, which allows for the same names to be used in different systems controlled by different parties. This avoids the potential of a name clash.

**Type: Characterization.facets.system (Choice(anyOf))**

| ID | Name | Type                             | \# | Description |
|----|------|----------------------------------|----|-------------|
| 1  | **** | c:URIDatatype                    | 1  | **c1** -    |
| 2  | **** | Characterization.facets.system.2 | 1  | **c2** -    |

**********

**Type: Characterization.facets.system.2 (Enumerated)**

| ID | Item                                      | Description |
|----|-------------------------------------------|-------------|
| 1  | **http://fedramp.gov**                    |             |
| 2  | **http://fedramp.gov/ns/oscal**           |             |
| 3  | **http://csrc.nist.gov/ns/oscal**         |             |
| 4  | **http://csrc.nist.gov/ns/oscal/unknown** |             |
| 5  | **http://cve.mitre.org**                  |             |
| 6  | **http://www.first.org/cvss/v2.0**        |             |
| 7  | **http://www.first.org/cvss/v3.0**        |             |
| 8  | **http://www.first.org/cvss/v3.1**        |             |

**********

Describes an existing mitigating factor that may affect the overall determination of the risk, with an optional link to an implementation statement in the SSP.

**Type: Risk.mitigating-factors (Record)**

| ID | Name                    | Type              | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|----|-------------------------|-------------------|-------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                | c:UUIDDatatype    | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this mitigating factor elsewhere in this or other OSCAL instances. The locally defined UUID of the mitigating factor can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document.                |
| 2  | **implementation-uuid** | c:UUIDDatatype    | 0..1  | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this implementation statement elsewhere in this or other OSCAL instancess. The locally defined UUID of the implementation statement can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 3  | **description**         | String            | 1     | A human-readable description of this mitigating factor.                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 4  | **props**               | m:Property        | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 5  | **links**               | m:Link            | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 6  | **subjects**            | Subject-reference | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

**********

Describes either recommended or an actual plan for addressing the risk.

**Type: Response (Record)**

| ID | Name                | Type                     | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----|---------------------|--------------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**            | c:UUIDDatatype           | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this remediation elsewhere in this or other OSCAL instances. The locally defined UUID of the risk response can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **lifecycle**       | Response.lifecycle       | 1     | Identifies whether this is a recommendation, such as from an assessor or tool, or an actual plan accepted by the system owner.                                                                                                                                                                                                                                                                                                                                          |
| 3  | **title**           | String                   | 1     | The title for this response activity.                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 4  | **description**     | String                   | 1     | A human-readable description of this response plan.                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 5  | **props**           | m:Property               | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 6  | **links**           | m:Link                   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 7  | **origins**         | Origin                   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 8  | **required-assets** | Response.required-assets | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 9  | **tasks**           | Task                     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 10 | **remarks**         | m:Remarks                | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**********

Identifies whether this is a recommendation, such as from an assessor or tool, or an actual plan accepted by the system owner.

**Type: Response.lifecycle (Choice(anyOf))**

| ID | Name | Type                 | \# | Description |
|----|------|----------------------|----|-------------|
| 1  | **** | c:TokenDatatype      | 1  | **c1** -    |
| 2  | **** | Response.lifecycle.2 | 1  | **c2** -    |

**********

**Type: Response.lifecycle.2 (Enumerated)**

| ID | Item               | Description |
|----|--------------------|-------------|
| 1  | **recommendation** |             |
| 2  | **planned**        |             |
| 3  | **completed**      |             |

**********

Identifies an asset required to achieve remediation.

**Type: Response.required-assets (Record)**

| ID | Name            | Type              | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|----|-----------------|-------------------|-------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**        | c:UUIDDatatype    | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this required asset elsewhere in this or other OSCAL instances. The locally defined UUID of the asset can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **subjects**    | Subject-reference | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 3  | **title**       | String            | 0..1  | The title for this required asset.                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 4  | **description** | String            | 1     | A human-readable description of this required asset.                                                                                                                                                                                                                                                                                                                                                                                                               |
| 5  | **props**       | m:Property        | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 6  | **links**       | m:Link            | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 7  | **remarks**     | m:Remarks         | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

**********

Represents a scheduled event or milestone, which may be associated with a series of assessment actions.

**Type: Task (Record)**

| ID | Name                      | Type                       | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----|---------------------------|----------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                  | c:UUIDDatatype             | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this task elsewhere in this or other OSCAL instances. The locally defined UUID of the task can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **type**                  | Task.type                  | 1     | The type of task.                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 3  | **title**                 | String                     | 1     | The title for this task.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 4  | **description**           | String                     | 0..1  | A human-readable description of this task.                                                                                                                                                                                                                                                                                                                                                                                                              |
| 5  | **props**                 | m:Property                 | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 6  | **links**                 | m:Link                     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 7  | **timing**                | Task.timing                | 0..1  | The timing under which the task is intended to occur.                                                                                                                                                                                                                                                                                                                                                                                                   |
| 8  | **dependencies**          | Task.dependencies          | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 9  | **tasks**                 | Task                       | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 10 | **associated-activities** | Task.associated-activities | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 11 | **subjects**              | Assessment-subject         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 12 | **responsible-roles**     | m:Responsible-role         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 13 | **remarks**               | m:Remarks                  | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**********

The type of task.

**Type: Task.type (Choice(anyOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | c:TokenDatatype | 1  | **c1** -    |
| 2  | **** | Task.type.2     | 1  | **c2** -    |

**********

**Type: Task.type.2 (Enumerated)**

| ID | Item          | Description |
|----|---------------|-------------|
| 1  | **milestone** |             |
| 2  | **action**    |             |

**********

The timing under which the task is intended to occur.

**Type: Task.timing (Record)**

| ID | Name                  | Type                          | \#   | Description                                                    |
|----|-----------------------|-------------------------------|------|----------------------------------------------------------------|
| 1  | **on-date**           | Task.timing.on-date           | 0..1 | The task is intended to occur on the specified date.           |
| 2  | **within-date-range** | Task.timing.within-date-range | 0..1 | The task is intended to occur within the specified date range. |
| 3  | **at-frequency**      | Task.timing.at-frequency      | 0..1 | The task is intended to occur at the specified frequency.      |

**********

The task is intended to occur on the specified date.

**Type: Task.timing.on-date (Record)**

| ID | Name     | Type                           | \# | Description                                |
|----|----------|--------------------------------|----|--------------------------------------------|
| 1  | **date** | c:DateTimeWithTimezoneDatatype | 1  | The task must occur on the specified date. |

**********

The task is intended to occur within the specified date range.

**Type: Task.timing.within-date-range (Record)**

| ID | Name      | Type                           | \# | Description                                          |
|----|-----------|--------------------------------|----|------------------------------------------------------|
| 1  | **start** | c:DateTimeWithTimezoneDatatype | 1  | The task must occur on or after the specified date.  |
| 2  | **end**   | c:DateTimeWithTimezoneDatatype | 1  | The task must occur on or before the specified date. |

**********

The task is intended to occur at the specified frequency.

**Type: Task.timing.at-frequency (Record)**

| ID | Name       | Type                          | \# | Description                                                 |
|----|------------|-------------------------------|----|-------------------------------------------------------------|
| 1  | **period** | c:PositiveIntegerDatatype     | 1  | The task must occur after the specified period has elapsed. |
| 2  | **unit**   | Task.timing.at-frequency.unit | 1  | The unit of time for the period.                            |

**********

The unit of time for the period.

**Type: Task.timing.at-frequency.unit (Choice(allOf))**

| ID | Name | Type                            | \# | Description |
|----|------|---------------------------------|----|-------------|
| 1  | **** | c:StringDatatype                | 1  | **c1** -    |
| 2  | **** | Task.timing.at-frequency.unit.2 | 1  | **c2** -    |

**********

**Type: Task.timing.at-frequency.unit.2 (Enumerated)**

| ID | Item        | Description |
|----|-------------|-------------|
| 1  | **seconds** |             |
| 2  | **minutes** |             |
| 3  | **hours**   |             |
| 4  | **days**    |             |
| 5  | **months**  |             |
| 6  | **years**   |             |

**********

Used to indicate that a task is dependent on another task.

**Type: Task.dependencies (Record)**

| ID | Name          | Type           | \#   | Description                                               |
|----|---------------|----------------|------|-----------------------------------------------------------|
| 1  | **task-uuid** | c:UUIDDatatype | 1    | A machine-oriented identifier reference to a unique task. |
| 2  | **remarks**   | m:Remarks      | 0..1 |                                                           |

**********

Identifies an individual activity to be performed as part of a task.

**Type: Task.associated-activities (Record)**

| ID | Name                  | Type               | \#    | Description                                                                               |
|----|-----------------------|--------------------|-------|-------------------------------------------------------------------------------------------|
| 1  | **activity-uuid**     | c:UUIDDatatype     | 1     | A machine-oriented identifier reference to an activity defined in the list of activities. |
| 2  | **props**             | m:Property         | 0..\* |                                                                                           |
| 3  | **links**             | m:Link             | 0..\* |                                                                                           |
| 4  | **responsible-roles** | m:Responsible-role | 0..\* |                                                                                           |
| 5  | **subjects**          | Assessment-subject | 1..\* |                                                                                           |
| 6  | **remarks**           | m:Remarks          | 0..1  |                                                                                           |

**********

A log of all risk-related tasks taken.

**Type: Risk.risk-log (Record)**

| ID | Name        | Type                  | \#    | Description |
|----|-------------|-----------------------|-------|-------------|
| 1  | **entries** | Risk.risk-log.entries | 1..\* |             |

**********

Identifies an individual risk response that occurred as part of managing an identified risk.

**Type: Risk.risk-log.entries (Record)**

| ID | Name                  | Type                                    | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----|-----------------------|-----------------------------------------|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype                          | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this risk log entry elsewhere in this or other OSCAL instances. The locally defined UUID of the risk log entry can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**             | String                                  | 0..1  | The title for this risk log entry.                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 3  | **description**       | String                                  | 0..1  | A human-readable description of what was done regarding the risk.                                                                                                                                                                                                                                                                                                                                                                                                           |
| 4  | **start**             | c:DateTimeWithTimezoneDatatype          | 1     | Identifies the start date and time of the event.                                                                                                                                                                                                                                                                                                                                                                                                                            |
| 5  | **end**               | c:DateTimeWithTimezoneDatatype          | 0..1  | Identifies the end date and time of the event. If the event is a point in time, the start and end will be the same date and time.                                                                                                                                                                                                                                                                                                                                           |
| 6  | **props**             | m:Property                              | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 7  | **links**             | m:Link                                  | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 8  | **logged-by**         | Logged-by                               | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 9  | **status-change**     | Risk-status                             | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 10 | **related-responses** | Risk.risk-log.entries.related-responses | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 11 | **remarks**           | m:Remarks                               | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**********

Used to indicate who created a log entry in what role.

**Type: Logged-by (Record)**

| ID | Name           | Type            | \#   | Description                                                                       |
|----|----------------|-----------------|------|-----------------------------------------------------------------------------------|
| 1  | **party-uuid** | c:UUIDDatatype  | 1    | A machine-oriented identifier reference to the party who is making the log entry. |
| 2  | **role-id**    | c:TokenDatatype | 0..1 | A point to the role-id of the role in which the party is making the log entry.    |

**********

Identifies an individual risk response that this log entry is for.

**Type: Risk.risk-log.entries.related-responses (Record)**

| ID | Name              | Type           | \#    | Description                                                        |
|----|-------------------|----------------|-------|--------------------------------------------------------------------|
| 1  | **response-uuid** | c:UUIDDatatype | 1     | A machine-oriented identifier reference to a unique risk response. |
| 2  | **props**         | m:Property     | 0..\* |                                                                    |
| 3  | **links**         | m:Link         | 0..\* |                                                                    |
| 4  | **related-tasks** | Related-task   | 0..\* |                                                                    |
| 5  | **remarks**       | m:Remarks      | 0..1  |                                                                    |

**********

Relates the finding to a set of referenced observations that were used to determine the finding.

**Type: Risk.related-observations (Record)**

| ID | Name                 | Type           | \# | Description                                                                                    |
|----|----------------------|----------------|----|------------------------------------------------------------------------------------------------|
| 1  | **observation-uuid** | c:UUIDDatatype | 1  | A machine-oriented identifier reference to an observation defined in the list of observations. |

**********
