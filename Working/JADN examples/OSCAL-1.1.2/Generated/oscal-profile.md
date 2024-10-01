       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-profile"
    namespaces: [["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"], ["cc", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"], ["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Profile"]
       comment: "OSCAL Profile Model: JSON Schema"

Each OSCAL profile is defined by a profile element.

**Type: Profile (Record)**

| ID | Name            | Type           | \#    | Description                                                            |
|----|-----------------|----------------|-------|------------------------------------------------------------------------|
| 1  | **uuid**        | c:UUIDDatatype | 1     | Provides a globally unique means to identify a given profile instance. |
| 2  | **metadata**    | m:Metadata     | 1     |                                                                        |
| 3  | **imports**     | Import         | 1..\* |                                                                        |
| 4  | **merge**       | Merge          | 0..1  |                                                                        |
| 5  | **modify**      | Modify         | 0..1  |                                                                        |
| 6  | **back-matter** | m:Back-matter  | 0..1  |                                                                        |

**********

Designates a referenced source catalog or profile that provides a source of control information for use in creating a new overlay or baseline.

**Type: Import (Record)**

| ID | Name                 | Type                   | \#    | Description                                                                               |
|----|----------------------|------------------------|-------|-------------------------------------------------------------------------------------------|
| 1  | **href**             | c:URIReferenceDatatype | 1     | A resolvable URL reference to the base catalog or profile that this profile is tailoring. |
| 2  | **include-all**      | cc:Include-all         | 0..1  |                                                                                           |
| 3  | **include-controls** | Select-control-by-id   | 0..\* |                                                                                           |
| 4  | **exclude-controls** | Select-control-by-id   | 0..\* |                                                                                           |

**********

Select a control or controls from an imported control set.

**Type: Select-control-by-id (Record)**

| ID | Name                    | Type                                     | \#    | Description                                                                           |
|----|-------------------------|------------------------------------------|-------|---------------------------------------------------------------------------------------|
| 1  | **with-child-controls** | Select-control-by-id.with-child-controls | 0..1  | When a control is included, whether its child (dependent) controls are also included. |
| 2  | **with-ids**            | With-id                                  | 0..\* |                                                                                       |
| 3  | **matching**            | Matching                                 | 0..\* |                                                                                       |

**********

When a control is included, whether its child (dependent) controls are also included.

**Type: Select-control-by-id.with-child-controls (Choice(allOf))**

| ID | Name | Type                                       | \# | Description |
|----|------|--------------------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype                            | 1  | **c1** -    |
| 2  | **** | Select-control-by-id.with-child-controls.2 | 1  | **c2** -    |

**********

**Type: Select-control-by-id.with-child-controls.2 (Enumerated)**

| ID | Item    | Description |
|----|---------|-------------|
| 1  | **yes** |             |
| 2  | **no**  |             |

**********

Selecting a control by its ID given as a literal.

**Type: With-id (Choice(allOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | c:TokenDatatype | 1  | **alias** -  |

**********

Selecting a set of controls by matching their IDs with a wildcard pattern.

**Type: Matching (Record)**

| ID | Name        | Type             | \#   | Description                                                                |
|----|-------------|------------------|------|----------------------------------------------------------------------------|
| 1  | **pattern** | c:StringDatatype | 0..1 | A glob expression matching the IDs of one or more controls to be selected. |

**********

Provides structuring directives that instruct how controls are organized after profile resolution.

**Type: Merge (Record)**

| ID | Name        | Type              | \#   | Description                                                                                                         |
|----|-------------|-------------------|------|---------------------------------------------------------------------------------------------------------------------|
| 1  | **combine** | Merge.combine     | 0..1 | A Combine element defines how to resolve duplicate instances of the same control (e.g., controls with the same ID). |
| 2  | **flat**    | Merge.flat        | 0..1 | Directs that controls appear without any grouping structure.                                                        |
| 3  | **as-is**   | c:BooleanDatatype | 0..1 | Indicates that the controls selected should retain their original grouping as defined in the import source.         |
| 4  | **custom**  | Merge.custom      | 0..1 | Provides an alternate grouping structure that selected controls will be placed in.                                  |

**********

A Combine element defines how to resolve duplicate instances of the same control (e.g., controls with the same ID).

**Type: Merge.combine (Record)**

| ID | Name       | Type                 | \#   | Description                                      |
|----|------------|----------------------|------|--------------------------------------------------|
| 1  | **method** | Merge.combine.method | 0..1 | Declare how clashing controls should be handled. |

**********

Declare how clashing controls should be handled.

**Type: Merge.combine.method (Choice(allOf))**

| ID | Name | Type                   | \# | Description |
|----|------|------------------------|----|-------------|
| 1  | **** | c:StringDatatype       | 1  | **c1** -    |
| 2  | **** | Merge.combine.method.2 | 1  | **c2** -    |

**********

**Type: Merge.combine.method.2 (Enumerated)**

| ID | Item          | Description |
|----|---------------|-------------|
| 1  | **use-first** |             |
| 2  | **merge**     |             |
| 3  | **keep**      |             |

**********

| Type Name      | Type Definition | Description                                                  |
|----------------|-----------------|--------------------------------------------------------------|
| **Merge.flat** | Record          | Directs that controls appear without any grouping structure. |

**********

Provides an alternate grouping structure that selected controls will be placed in.

**Type: Merge.custom (Record)**

| ID | Name                | Type            | \#    | Description |
|----|---------------------|-----------------|-------|-------------|
| 1  | **groups**          | Group           | 0..\* |             |
| 2  | **insert-controls** | Insert-controls | 0..\* |             |

**********

A group of (selected) controls or of groups of controls.

**Type: Group (Record)**

| ID | Name                | Type            | \#    | Description                                                                |
|----|---------------------|-----------------|-------|----------------------------------------------------------------------------|
| 1  | **id**              | c:TokenDatatype | 0..1  | Identifies the group.                                                      |
| 2  | **class**           | c:TokenDatatype | 0..1  | A textual label that provides a sub-type or characterization of the group. |
| 3  | **title**           | String          | 1     | A name to be given to the group for use in display.                        |
| 4  | **params**          | cc:Parameter    | 0..\* |                                                                            |
| 5  | **props**           | m:Property      | 0..\* |                                                                            |
| 6  | **links**           | m:Link          | 0..\* |                                                                            |
| 7  | **parts**           | cc:Part         | 0..\* |                                                                            |
| 8  | **groups**          | Group           | 0..\* |                                                                            |
| 9  | **insert-controls** | Insert-controls | 0..\* |                                                                            |

**********

Specifies which controls to use in the containing context.

**Type: Insert-controls (Record)**

| ID | Name                 | Type                  | \#    | Description                                                                 |
|----|----------------------|-----------------------|-------|-----------------------------------------------------------------------------|
| 1  | **order**            | Insert-controls.order | 0..1  | A designation of how a selection of controls in a profile is to be ordered. |
| 2  | **include-all**      | cc:Include-all        | 0..1  |                                                                             |
| 3  | **include-controls** | Select-control-by-id  | 0..\* |                                                                             |
| 4  | **exclude-controls** | Select-control-by-id  | 0..\* |                                                                             |

**********

A designation of how a selection of controls in a profile is to be ordered.

**Type: Insert-controls.order (Choice(allOf))**

| ID | Name | Type                    | \# | Description |
|----|------|-------------------------|----|-------------|
| 1  | **** | c:TokenDatatype         | 1  | **c1** -    |
| 2  | **** | Insert-controls.order.2 | 1  | **c2** -    |

**********

**Type: Insert-controls.order.2 (Enumerated)**

| ID | Item           | Description |
|----|----------------|-------------|
| 1  | **keep**       |             |
| 2  | **ascending**  |             |
| 3  | **descending** |             |

**********

Set parameters or amend controls in resolution.

**Type: Modify (Record)**

| ID | Name               | Type                  | \#    | Description |
|----|--------------------|-----------------------|-------|-------------|
| 1  | **set-parameters** | Modify.set-parameters | 0..\* |             |
| 2  | **alters**         | Modify.alters         | 0..\* |             |

**********

A parameter setting, to be propagated to points of insertion.

**Type: Modify.set-parameters (Record)**

| ID | Name            | Type                    | \#    | Description                                                                                                         |
|----|-----------------|-------------------------|-------|---------------------------------------------------------------------------------------------------------------------|
| 1  | **param-id**    | c:TokenDatatype         | 1     | An identifier for the parameter.                                                                                    |
| 2  | **class**       | c:TokenDatatype         | 0..1  | A textual label that provides a characterization of the parameter.                                                  |
| 3  | **depends-on**  | c:TokenDatatype         | 0..1  | **(deprecated)** Another parameter invoking this one. This construct has been deprecated and should not be used.    |
| 4  | **props**       | m:Property              | 0..\* |                                                                                                                     |
| 5  | **links**       | m:Link                  | 0..\* |                                                                                                                     |
| 6  | **label**       | String                  | 0..1  | A short, placeholder name for the parameter, which can be used as a substitute for a value if no value is assigned. |
| 7  | **usage**       | String                  | 0..1  | Describes the purpose and use of a parameter.                                                                       |
| 8  | **constraints** | cc:Parameter-constraint | 0..\* |                                                                                                                     |
| 9  | **guidelines**  | cc:Parameter-guideline  | 0..\* |                                                                                                                     |
| 10 | **values**      | cc:Parameter-value      | 0..\* |                                                                                                                     |
| 11 | **select**      | cc:Parameter-selection  | 0..1  |                                                                                                                     |

**********

Specifies changes to be made to an included control when a profile is resolved.

**Type: Modify.alters (Record)**

| ID | Name           | Type                  | \#    | Description                                                                                                                                                                                                                           |
|----|----------------|-----------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **control-id** | c:TokenDatatype       | 1     | A reference to a control with a corresponding id value. When referencing an externally defined control, the Control Identifier Reference must be used in the context of the external / imported OSCAL instance (e.g., uri-reference). |
| 2  | **removes**    | Modify.alters.removes | 0..\* |                                                                                                                                                                                                                                       |
| 3  | **adds**       | Modify.alters.adds    | 0..\* |                                                                                                                                                                                                                                       |

**********

Specifies objects to be removed from a control based on specific aspects of the object that must all match.

**Type: Modify.alters.removes (Record)**

| ID | Name             | Type                               | \#   | Description                                                                                        |
|----|------------------|------------------------------------|------|----------------------------------------------------------------------------------------------------|
| 1  | **by-name**      | c:TokenDatatype                    | 0..1 | Identify items remove by matching their assigned name.                                             |
| 2  | **by-class**     | c:TokenDatatype                    | 0..1 | Identify items to remove by matching their class.                                                  |
| 3  | **by-id**        | c:TokenDatatype                    | 0..1 | Identify items to remove indicated by their id.                                                    |
| 4  | **by-item-name** | Modify.alters.removes.by-item-name | 0..1 | Identify items to remove by the name of the item's information object name, e.g. title or prop.    |
| 5  | **by-ns**        | c:TokenDatatype                    | 0..1 | Identify items to remove by the item's ns, which is the namespace associated with a part, or prop. |

**********

Identify items to remove by the name of the item's information object name, e.g. title or prop.

**Type: Modify.alters.removes.by-item-name (Choice(allOf))**

| ID | Name | Type                                 | \# | Description |
|----|------|--------------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype                      | 1  | **c1** -    |
| 2  | **** | Modify.alters.removes.by-item-name.2 | 1  | **c2** -    |

**********

**Type: Modify.alters.removes.by-item-name.2 (Enumerated)**

| ID | Item        | Description |
|----|-------------|-------------|
| 1  | **param**   |             |
| 2  | **prop**    |             |
| 3  | **link**    |             |
| 4  | **part**    |             |
| 5  | **mapping** |             |
| 6  | **map**     |             |

**********

Specifies contents to be added into controls, in resolution.

**Type: Modify.alters.adds (Record)**

| ID | Name         | Type                        | \#    | Description                                                                                 |
|----|--------------|-----------------------------|-------|---------------------------------------------------------------------------------------------|
| 1  | **position** | Modify.alters.adds.position | 0..1  | Where to add the new content with respect to the targeted element (beside it or inside it). |
| 2  | **by-id**    | c:TokenDatatype             | 0..1  | Target location of the addition.                                                            |
| 3  | **title**    | String                      | 0..1  | A name given to the control, which may be used by a tool for display and navigation.        |
| 4  | **params**   | cc:Parameter                | 0..\* |                                                                                             |
| 5  | **props**    | m:Property                  | 0..\* |                                                                                             |
| 6  | **links**    | m:Link                      | 0..\* |                                                                                             |
| 7  | **parts**    | cc:Part                     | 0..\* |                                                                                             |

**********

Where to add the new content with respect to the targeted element (beside it or inside it).

**Type: Modify.alters.adds.position (Choice(allOf))**

| ID | Name | Type                          | \# | Description |
|----|------|-------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype               | 1  | **c1** -    |
| 2  | **** | Modify.alters.adds.position.2 | 1  | **c2** -    |

**********

**Type: Modify.alters.adds.position.2 (Enumerated)**

| ID | Item         | Description |
|----|--------------|-------------|
| 1  | **before**   |             |
| 2  | **after**    |             |
| 3  | **starting** |             |
| 4  | **ending**   |             |

**********
