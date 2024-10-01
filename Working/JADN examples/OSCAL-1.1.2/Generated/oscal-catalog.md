       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-catalog"
    namespaces: [["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"], ["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Catalog"]
       comment: "OSCAL Control Catalog Model: JSON Schema"

A structured, organized collection of control information.

**Type: Catalog (Record)**

| ID | Name            | Type           | \#    | Description                                                            |
|----|-----------------|----------------|-------|------------------------------------------------------------------------|
| 1  | **uuid**        | c:UUIDDatatype | 1     | Provides a globally unique means to identify a given catalog instance. |
| 2  | **metadata**    | m:Metadata     | 1     |                                                                        |
| 3  | **params**      | cc:Parameter   | 0..\* |                                                                        |
| 4  | **controls**    | Control        | 0..\* |                                                                        |
| 5  | **groups**      | Group          | 0..\* |                                                                        |
| 6  | **back-matter** | m:Back-matter  | 0..1  |                                                                        |

**********

A structured object representing a requirement or guideline, which when implemented will reduce an aspect of risk related to an information system and its information.

**Type: Control (Record)**

| ID | Name         | Type            | \#    | Description                                                                                                             |
|----|--------------|-----------------|-------|-------------------------------------------------------------------------------------------------------------------------|
| 1  | **id**       | c:TokenDatatype | 1     | Identifies a control such that it can be referenced in the defining catalog and other OSCAL instances (e.g., profiles). |
| 2  | **class**    | c:TokenDatatype | 0..1  | A textual label that provides a sub-type or characterization of the control.                                            |
| 3  | **title**    | String          | 1     | A name given to the control, which may be used by a tool for display and navigation.                                    |
| 4  | **params**   | cc:Parameter    | 0..\* |                                                                                                                         |
| 5  | **props**    | m:Property      | 0..\* |                                                                                                                         |
| 6  | **links**    | m:Link          | 0..\* |                                                                                                                         |
| 7  | **parts**    | cc:Part         | 0..\* |                                                                                                                         |
| 8  | **controls** | Control         | 0..\* |                                                                                                                         |

**********

A group of controls, or of groups of controls.

**Type: Group (Record)**

| ID | Name         | Type            | \#    | Description                                                                                                                            |
|----|--------------|-----------------|-------|----------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **id**       | c:TokenDatatype | 0..1  | Identifies the group for the purpose of cross-linking within the defining instance or from other instances that reference the catalog. |
| 2  | **class**    | c:TokenDatatype | 0..1  | A textual label that provides a sub-type or characterization of the group.                                                             |
| 3  | **title**    | String          | 1     | A name given to the group, which may be used by a tool for display and navigation.                                                     |
| 4  | **params**   | cc:Parameter    | 0..\* |                                                                                                                                        |
| 5  | **props**    | m:Property      | 0..\* |                                                                                                                                        |
| 6  | **links**    | m:Link          | 0..\* |                                                                                                                                        |
| 7  | **parts**    | cc:Part         | 0..\* |                                                                                                                                        |
| 8  | **groups**   | Group           | 0..\* |                                                                                                                                        |
| 9  | **controls** | Control         | 0..\* |                                                                                                                                        |

**********
