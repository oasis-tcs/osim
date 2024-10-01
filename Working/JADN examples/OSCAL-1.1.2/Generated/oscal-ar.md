       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-ar"
    namespaces: [["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"], ["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["ic", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-implementation-common"], ["ac", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-assessment-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Assessment-results"]
       comment: "OSCAL Assessment Results Model: JSON Schema"

Security assessment results, such as those provided by a FedRAMP assessor in the FedRAMP Security Assessment Report.

**Type: Assessment-results (Record)**

| ID | Name                  | Type                                 | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|----|-----------------------|--------------------------------------|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype                       | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this assessment results instance in this or other OSCAL instances. The locally defined UUID of the assessment result can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **metadata**          | m:Metadata                           | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 3  | **import-ap**         | Import-ap                            | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 4  | **local-definitions** | Assessment-results.local-definitions | 0..1  | Used to define data objects that are used in the assessment plan, that do not appear in the referenced SSP.                                                                                                                                                                                                                                                                                                                                                                       |
| 5  | **results**           | Result                               | 1..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 6  | **back-matter**       | m:Back-matter                        | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

**********

Used by assessment-results to import information about the original plan for assessing the system.

**Type: Import-ap (Record)**

| ID | Name        | Type                   | \#   | Description                                                                            |
|----|-------------|------------------------|------|----------------------------------------------------------------------------------------|
| 1  | **href**    | c:URIReferenceDatatype | 1    | A resolvable URL reference to the assessment plan governing the assessment activities. |
| 2  | **remarks** | m:Remarks              | 0..1 |                                                                                        |

**********

Used to define data objects that are used in the assessment plan, that do not appear in the referenced SSP.

**Type: Assessment-results.local-definitions (Record)**

| ID | Name                       | Type               | \#    | Description |
|----|----------------------------|--------------------|-------|-------------|
| 1  | **objectives-and-methods** | ac:Local-objective | 0..\* |             |
| 2  | **activities**             | ac:Activity        | 0..\* |             |
| 3  | **remarks**                | m:Remarks          | 0..1  |             |

**********

Used by the assessment results and POA&M. In the assessment results, this identifies all of the assessment observations and findings, initial and residual risks, deviations, and disposition. In the POA&M, this identifies initial and residual risks, deviations, and disposition.

**Type: Result (Record)**

| ID | Name                  | Type                           | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|----|-----------------------|--------------------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype                 | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this set of results in this or other OSCAL instances. The locally defined UUID of the assessment result can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**             | String                         | 1     | The title for this set of results.                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 3  | **description**       | String                         | 1     | A human-readable description of this set of test results.                                                                                                                                                                                                                                                                                                                                                                                                            |
| 4  | **start**             | c:DateTimeWithTimezoneDatatype | 1     | Date/time stamp identifying the start of the evidence collection reflected in these results.                                                                                                                                                                                                                                                                                                                                                                         |
| 5  | **end**               | c:DateTimeWithTimezoneDatatype | 0..1  | Date/time stamp identifying the end of the evidence collection reflected in these results. In a continuous motoring scenario, this may contain the same value as start if appropriate.                                                                                                                                                                                                                                                                               |
| 6  | **props**             | m:Property                     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 7  | **links**             | m:Link                         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 8  | **local-definitions** | Result.local-definitions       | 0..1  | Used to define data objects that are used in the assessment plan, that do not appear in the referenced SSP.                                                                                                                                                                                                                                                                                                                                                          |
| 9  | **reviewed-controls** | ac:Reviewed-controls           | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 10 | **attestations**      | Result.attestations            | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 11 | **assessment-log**    | Result.assessment-log          | 0..1  | A log of all assessment-related actions taken.                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 12 | **observations**      | ac:Observation                 | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 13 | **risks**             | ac:Risk                        | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 14 | **findings**          | ac:Finding                     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 15 | **remarks**           | m:Remarks                      | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

**********

Used to define data objects that are used in the assessment plan, that do not appear in the referenced SSP.

**Type: Result.local-definitions (Record)**

| ID | Name                  | Type                 | \#    | Description |
|----|-----------------------|----------------------|-------|-------------|
| 1  | **components**        | ic:System-component  | 0..\* |             |
| 2  | **inventory-items**   | ic:Inventory-item    | 0..\* |             |
| 3  | **users**             | ic:System-user       | 0..\* |             |
| 4  | **assessment-assets** | ac:Assessment-assets | 0..1  |             |
| 5  | **tasks**             | ac:Task              | 0..\* |             |

**********

A set of textual statements, typically written by the assessor.

**Type: Result.attestations (Record)**

| ID | Name                    | Type                | \#    | Description |
|----|-------------------------|---------------------|-------|-------------|
| 1  | **responsible-parties** | m:Responsible-party | 0..\* |             |
| 2  | **parts**               | ac:Assessment-part  | 1..\* |             |

**********

A log of all assessment-related actions taken.

**Type: Result.assessment-log (Record)**

| ID | Name        | Type                          | \#    | Description |
|----|-------------|-------------------------------|-------|-------------|
| 1  | **entries** | Result.assessment-log.entries | 1..\* |             |

**********

Identifies the result of an action and/or task that occurred as part of executing an assessment plan or an assessment event that occurred in producing the assessment results.

**Type: Result.assessment-log.entries (Record)**

| ID | Name              | Type                           | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----|-------------------|--------------------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**          | c:UUIDDatatype                 | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference an assessment event in this or other OSCAL instances. The locally defined UUID of the assessment log entry can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**         | String                         | 0..1  | The title for this event.                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 3  | **description**   | String                         | 0..1  | A human-readable description of this event.                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 4  | **start**         | c:DateTimeWithTimezoneDatatype | 1     | Identifies the start date and time of an event.                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 5  | **end**           | c:DateTimeWithTimezoneDatatype | 0..1  | Identifies the end date and time of an event. If the event is a point in time, the start and end will be the same date and time.                                                                                                                                                                                                                                                                                                                                        |
| 6  | **props**         | m:Property                     | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 7  | **links**         | m:Link                         | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 8  | **logged-by**     | ac:Logged-by                   | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 9  | **related-tasks** | ac:Related-task                | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 10 | **remarks**       | m:Remarks                      | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**********
