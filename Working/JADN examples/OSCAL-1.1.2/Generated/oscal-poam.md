       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-poam"
    namespaces: [["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"], ["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["ic", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-implementation-common"], ["ac", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-assessment-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Plan-of-action-and-milestones"]
       comment: "OSCAL Plan of Action and Milestones (POA&M) Model: JSON Schema"

A plan of action and milestones which identifies initial and residual risks, deviations, and disposition, such as those required by FedRAMP.

**Type: Plan-of-action-and-milestones (Record)**

| ID | Name                  | Type              | \#    | Description                                                                                                                                                                                                                                                                                     |
|----|-----------------------|-------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype    | 1     | A machine-oriented, globally unique identifier with instancescope that can be used to reference this POA&M instance in this OSCAL instance. This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **metadata**          | m:Metadata        | 1     |                                                                                                                                                                                                                                                                                                 |
| 3  | **import-ssp**        | ac:Import-ssp     | 0..1  |                                                                                                                                                                                                                                                                                                 |
| 4  | **system-id**         | ic:System-id      | 0..1  |                                                                                                                                                                                                                                                                                                 |
| 5  | **local-definitions** | Local-definitions | 0..1  |                                                                                                                                                                                                                                                                                                 |
| 6  | **observations**      | ac:Observation    | 0..\* |                                                                                                                                                                                                                                                                                                 |
| 7  | **risks**             | ac:Risk           | 0..\* |                                                                                                                                                                                                                                                                                                 |
| 8  | **findings**          | ac:Finding        | 0..\* |                                                                                                                                                                                                                                                                                                 |
| 9  | **poam-items**        | Poam-item         | 1..\* |                                                                                                                                                                                                                                                                                                 |
| 10 | **back-matter**       | m:Back-matter     | 0..1  |                                                                                                                                                                                                                                                                                                 |

**********

Allows components, and inventory-items to be defined within the POA&M for circumstances where no OSCAL-based SSP exists, or is not delivered with the POA&M.

**Type: Local-definitions (Record)**

| ID | Name                  | Type                 | \#    | Description |
|----|-----------------------|----------------------|-------|-------------|
| 1  | **components**        | ic:System-component  | 0..\* |             |
| 2  | **inventory-items**   | ic:Inventory-item    | 0..\* |             |
| 3  | **assessment-assets** | ac:Assessment-assets | 0..1  |             |
| 4  | **remarks**           | m:Remarks            | 0..1  |             |

**********

Describes an individual POA&M item.

**Type: Poam-item (Record)**

| ID | Name                     | Type                           | \#    | Description                                                                                                                                                                                                                                                                                        |
|----|--------------------------|--------------------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                 | c:UUIDDatatype                 | 0..1  | A machine-oriented, globally unique identifier with instance scope that can be used to reference this POA&M item entry in this OSCAL instance. This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **title**                | String                         | 1     | The title or name for this POA&M item .                                                                                                                                                                                                                                                            |
| 3  | **description**          | String                         | 1     | A human-readable description of POA&M item.                                                                                                                                                                                                                                                        |
| 4  | **props**                | m:Property                     | 0..\* |                                                                                                                                                                                                                                                                                                    |
| 5  | **links**                | m:Link                         | 0..\* |                                                                                                                                                                                                                                                                                                    |
| 6  | **origins**              | Poam-item.origins              | 0..\* |                                                                                                                                                                                                                                                                                                    |
| 7  | **related-findings**     | Poam-item.related-findings     | 0..\* |                                                                                                                                                                                                                                                                                                    |
| 8  | **related-observations** | Poam-item.related-observations | 0..\* |                                                                                                                                                                                                                                                                                                    |
| 9  | **related-risks**        | Poam-item.related-risks        | 0..\* |                                                                                                                                                                                                                                                                                                    |
| 10 | **remarks**              | m:Remarks                      | 0..1  |                                                                                                                                                                                                                                                                                                    |

**********

Identifies the source of the finding, such as a tool or person.

**Type: Poam-item.origins (Record)**

| ID | Name       | Type            | \#    | Description |
|----|------------|-----------------|-------|-------------|
| 1  | **actors** | ac:Origin-actor | 1..\* |             |

**********

Relates the poam-item to referenced finding(s).

**Type: Poam-item.related-findings (Record)**

| ID | Name             | Type           | \# | Description                                                                           |
|----|------------------|----------------|----|---------------------------------------------------------------------------------------|
| 1  | **finding-uuid** | c:UUIDDatatype | 1  | A machine-oriented identifier reference to a finding defined in the list of findings. |

**********

Relates the poam-item to a set of referenced observations that were used to determine the finding.

**Type: Poam-item.related-observations (Record)**

| ID | Name                 | Type           | \# | Description                                                                                    |
|----|----------------------|----------------|----|------------------------------------------------------------------------------------------------|
| 1  | **observation-uuid** | c:UUIDDatatype | 1  | A machine-oriented identifier reference to an observation defined in the list of observations. |

**********

Relates the finding to a set of referenced risks that were used to determine the finding.

**Type: Poam-item.related-risks (Record)**

| ID | Name          | Type           | \# | Description                                                                     |
|----|---------------|----------------|----|---------------------------------------------------------------------------------|
| 1  | **risk-uuid** | c:UUIDDatatype | 1  | A machine-oriented identifier reference to a risk defined in the list of risks. |

**********
