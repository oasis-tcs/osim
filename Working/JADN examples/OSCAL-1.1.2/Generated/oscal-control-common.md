       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-control-common"
    namespaces: [["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"], ["m", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Include-all", "Parameter"]

| Type Name       | Type Definition | Description                                                          |
|-----------------|-----------------|----------------------------------------------------------------------|
| **Include-all** | Record          | Include all controls from the imported catalog or profile resources. |

**********

Parameters provide a mechanism for the dynamic assignment of value(s) in a control.

**Type: Parameter (Record)**

| ID | Name            | Type                 | \#    | Description                                                                                                         |
|----|-----------------|----------------------|-------|---------------------------------------------------------------------------------------------------------------------|
| 1  | **id**          | c:TokenDatatype      | 1     | A unique identifier for the parameter.                                                                              |
| 2  | **class**       | c:TokenDatatype      | 0..1  | A textual label that provides a characterization of the type, purpose, use or scope of the parameter.               |
| 3  | **depends-on**  | c:TokenDatatype      | 0..1  | (deprecated) Another parameter invoking this one. This construct has been deprecated and should not be used.        |
| 4  | **props**       | m:Property           | 0..\* |                                                                                                                     |
| 5  | **links**       | m:Link               | 0..\* |                                                                                                                     |
| 6  | **label**       | String               | 0..1  | A short, placeholder name for the parameter, which can be used as a substitute for a value if no value is assigned. |
| 7  | **usage**       | String               | 0..1  | Describes the purpose and use of a parameter.                                                                       |
| 8  | **constraints** | Parameter-constraint | 0..\* |                                                                                                                     |
| 9  | **guidelines**  | Parameter-guideline  | 0..\* |                                                                                                                     |
| 10 | **values**      | Parameter-value      | 0..\* |                                                                                                                     |
| 11 | **select**      | Parameter-selection  | 0..1  |                                                                                                                     |
| 12 | **remarks**     | m:Remarks            | 0..1  |                                                                                                                     |

**********

A formal or informal expression of a constraint or test.

**Type: Parameter-constraint (Record)**

| ID | Name            | Type                       | \#    | Description                                        |
|----|-----------------|----------------------------|-------|----------------------------------------------------|
| 1  | **description** | String                     | 0..1  | A textual summary of the constraint to be applied. |
| 2  | **tests**       | Parameter-constraint.tests | 0..\* |                                                    |

**********

A test expression which is expected to be evaluated by a tool.

**Type: Parameter-constraint.tests (Record)**

| ID | Name           | Type             | \#   | Description                                       |
|----|----------------|------------------|------|---------------------------------------------------|
| 1  | **expression** | c:StringDatatype | 1    | A formal (executable) expression of a constraint. |
| 2  | **remarks**    | m:Remarks        | 0..1 |                                                   |

**********

A prose statement that provides a recommendation for the use of a parameter.

**Type: Parameter-guideline (Record)**

| ID | Name      | Type   | \# | Description                                           |
|----|-----------|--------|----|-------------------------------------------------------|
| 1  | **prose** | String | 1  | Prose permits multiple paragraphs, lists, tables etc. |

**********

A parameter value or set of values.

**Type: Parameter-value (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **alias** -  |

**********

Presenting a choice among alternatives.

**Type: Parameter-selection (Record)**

| ID | Name         | Type                         | \#    | Description                                                                                                                 |
|----|--------------|------------------------------|-------|-----------------------------------------------------------------------------------------------------------------------------|
| 1  | **how-many** | Parameter-selection.how-many | 0..1  | Describes the number of selections that must occur. Without this setting, only one value should be assumed to be permitted. |
| 2  | **choice**   | Parameter-selection.choice   | 0..\* |                                                                                                                             |

**********

Describes the number of selections that must occur. Without this setting, only one value should be assumed to be permitted.

**Type: Parameter-selection.how-many (Choice(allOf))**

| ID | Name | Type                           | \# | Description |
|----|------|--------------------------------|----|-------------|
| 1  | **** | c:TokenDatatype                | 1  | **c1** -    |
| 2  | **** | Parameter-selection.how-many.2 | 1  | **c2** -    |

**********

**Type: Parameter-selection.how-many.2 (Enumerated)**

| ID | Item            | Description |
|----|-----------------|-------------|
| 1  | **one**         |             |
| 2  | **one-or-more** |             |

**********

| Type Name                      | Type Definition       | Description |
|--------------------------------|-----------------------|-------------|
| **Parameter-selection.choice** | ArrayOf(String){1..*} |             |

**********
