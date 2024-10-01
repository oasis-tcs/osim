       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-ap"
    namespaces: [["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"], ["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["ic", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-implementation-common"], ["ac", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-assessment-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Assessment-plan"]
       comment: "OSCAL Assessment Plan Model: JSON Schema"

An assessment plan, such as those provided by a FedRAMP assessor.

**Type: Assessment-plan (Record)**

| ID | Name                     | Type                                 | \#    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|----|--------------------------|--------------------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                 | c:UUIDDatatype                       | 1     | A machine-oriented, globally unique identifier with cross-instance scope that can be used to reference this assessment plan in this or other OSCAL instances. The locally defined UUID of the assessment plan can be used to reference the data item locally or globally (e.g., in an imported OSCAL instance). This UUID should be assigned per-subject, which means it should be consistently used to identify the same subject across revisions of the document. |
| 2  | **metadata**             | m:Metadata                           | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 3  | **import-ssp**           | ac:Import-ssp                        | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 4  | **local-definitions**    | Assessment-plan.local-definitions    | 0..1  | Used to define data objects that are used in the assessment plan, that do not appear in the referenced SSP.                                                                                                                                                                                                                                                                                                                                                         |
| 5  | **terms-and-conditions** | Assessment-plan.terms-and-conditions | 0..1  | Used to define various terms and conditions under which an assessment, described by the plan, can be performed. Each child part defines a different type of term or condition.                                                                                                                                                                                                                                                                                      |
| 6  | **reviewed-controls**    | ac:Reviewed-controls                 | 1     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 7  | **assessment-subjects**  | ac:Assessment-subject                | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 8  | **assessment-assets**    | ac:Assessment-assets                 | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 9  | **tasks**                | ac:Task                              | 0..\* |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 10 | **back-matter**          | m:Back-matter                        | 0..1  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

**********

Used to define data objects that are used in the assessment plan, that do not appear in the referenced SSP.

**Type: Assessment-plan.local-definitions (Record)**

| ID | Name                       | Type                | \#    | Description |
|----|----------------------------|---------------------|-------|-------------|
| 1  | **components**             | ic:System-component | 0..\* |             |
| 2  | **inventory-items**        | ic:Inventory-item   | 0..\* |             |
| 3  | **users**                  | ic:System-user      | 0..\* |             |
| 4  | **objectives-and-methods** | ac:Local-objective  | 0..\* |             |
| 5  | **activities**             | ac:Activity         | 0..\* |             |
| 6  | **remarks**                | m:Remarks           | 0..1  |             |

**********

Used to define various terms and conditions under which an assessment, described by the plan, can be performed. Each child part defines a different type of term or condition.

**Type: Assessment-plan.terms-and-conditions (Record)**

| ID | Name      | Type               | \#    | Description |
|----|-----------|--------------------|-------|-------------|
| 1  | **parts** | ac:Assessment-part | 0..\* |             |

**********
