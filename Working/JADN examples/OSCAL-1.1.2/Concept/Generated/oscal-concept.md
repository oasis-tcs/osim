         title: "OSCAL"
       package: "https://example.gov/ns/oscal/0.0.1/"
   description: "OSCAL - Open Security Controls Assessment Language"
    namespaces: [["", "https://example.gov/ns/oscal/0.0.1/metadata/"], ["", "https://example.gov/ns/oscal/0.0.1/catalog/"], ["", "https://example.gov/ns/oscal/0.0.1/profile/"], ["", "https://example.gov/ns/oscal/0.0.1/component/"], ["", "https://example.gov/ns/oscal/0.0.1/ssp/"], ["", "https://example.gov/ns/oscal/0.0.1/assessment_plan/"], ["", "https://example.gov/ns/oscal/0.0.1/assessment_results/"], ["", "https://example.gov/ns/oscal/0.0.1/poam/"]]
       exports: ["OSCAL"]

OSCAL document - content must appear in this sequence

**Type: OSCAL (Record sequence)**

| ID | Name            | Type                    | \#   | Description                                    |
|----|-----------------|-------------------------|------|------------------------------------------------|
| 1  | **model**       | Enumerated(Enum[Model]) | 1    | OSCAL model identifier                         |
| 2  | **uuid**        | UUID                    | 1    | Document instance unique identifier            |
| 3  | **metadata**    | Metadata                | 1    | Identifying info, roles, parties and locations |
| 4  | **body**        | Model(TagId[model])     | 1    | Model-specific body                            |
| 5  | **back_matter** | Back-matter             | 0..1 | Linked and attached resources                  |

**********

Model-specific content

**Type: Model (Choice)**

| ID | Name          | Type                          | \# | Description                                                                               |
|----|---------------|-------------------------------|----|-------------------------------------------------------------------------------------------|
| 1  | **catalog**   | Catalog                       | 1  | Control layer: catalog of controls                                                        |
| 2  | **profile**   | Profile                       | 1  | Control layer: selecting, organizing and tailoring a set of controls                      |
| 3  | **component** | Component                     | 1  | Implementation layer: component definition and configuration                              |
| 4  | **ssp**       | System-security-plan          | 1  | Implementation layer: security implementation of an information system                    |
| 5  | **ap**        | Assessment-plan               | 1  | Assessment layer: scope and activities                                                    |
| 6  | **ar**        | Assessment-results            | 1  | Assessment layer: information produced from assessment activities                         |
| 7  | **poam**      | Plan-of-action-and-milestones | 1  | Assessment layer: Plan of action and milestones: findings to be addressed by system owner |

**********
