       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Base64Datatype", "BooleanDatatype", "DateDatatype", "DateTimeWithTimezoneDatatype", "EmailAddressDatatype", "Json-schema-directive", "NonNegativeIntegerDatatype", "PositiveIntegerDatatype", "TokenDatatype", "URIDatatype", "UUIDDatatype"]

| Type Name          | Type Definition                          | Description                                                                     |
|--------------------|------------------------------------------|---------------------------------------------------------------------------------|
| **Base64Datatype** | String{pattern="^[0-9A-Za-z+/]+={0,2}$"} | Binary data encoded using the Base 64 encoding algorithm as defined by RFC4648. |

**********

| Type Name           | Type Definition | Description                                   |
|---------------------|-----------------|-----------------------------------------------|
| **BooleanDatatype** | Boolean         | A binary value that is either: true or false. |

**********

| Type Name        | Type Definition                                                                                                                                                                                                                                                                                                                                                    | Description                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------|
| **DateDatatype** | String{pattern="^(((2000|2400|2800|(19|2[0-9](0[48]|[2468][048]|[13579][26])))-02-29)|(((19|2[0-9])[0-9]{2})-02-(0[1-9]|1[0-9]|2[0-8]))|(((19|2[0-9])[0-9]{2})-(0[13578]|10|12)-(0[1-9]|[12][0-9]|3[01]))|(((19|2[0-9])[0-9]{2})-(0[469]|11)-(0[1-9]|[12][0-9]|30)))(Z|(-((0[0-9]|1[0-2]):00|0[39]:30)|\+((0[0-9]|1[0-4]):00|(0[34569]|10):30|(0[58]|12):45)))?$"} | A string representing a 24-hour period with an optional timezone. |

**********

| Type Name                        | Type Definition                                                                                                                                                                                                                                                                                                                                                                                                                      | Description                                                     |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| **DateTimeWithTimezoneDatatype** | String{pattern="^(((2000|2400|2800|(19|2[0-9](0[48]|[2468][048]|[13579][26])))-02-29)|(((19|2[0-9])[0-9]{2})-02-(0[1-9]|1[0-9]|2[0-8]))|(((19|2[0-9])[0-9]{2})-(0[13578]|10|12)-(0[1-9]|[12][0-9]|3[01]))|(((19|2[0-9])[0-9]{2})-(0[469]|11)-(0[1-9]|[12][0-9]|30)))T(2[0-3]|[01][0-9]):([0-5][0-9]):([0-5][0-9])(\.[0-9]+)?(Z|(-((0[0-9]|1[0-2]):00|0[39]:30)|\+((0[0-9]|1[0-4]):00|(0[34569]|10):30|(0[58]|12):45)))$"} /date-time | A string representing a point in time with a required timezone. |

**********

An email address string formatted according to RFC 6531.

**Type: EmailAddressDatatype (Choice(allOf))**

| ID | Name | Type           | \# | Description |
|----|------|----------------|----|-------------|
| 1  | **** | StringDatatype | 1  | **c1** -    |
| 2  | **** | String         | 1  | **c2** -    |

**********

| Type Name          | Type Definition               | Description                                                                                                  |
|--------------------|-------------------------------|--------------------------------------------------------------------------------------------------------------|
| **StringDatatype** | String{pattern="^\S(.*\S)?$"} | A non-empty string with leading and trailing whitespace disallowed. Whitespace is: U+9, U+10, U+32 or [ 
	]+ |

**********

A JSON Schema directive to bind a specific schema to its document instance.

**Type: Json-schema-directive (Choice(allOf))**

| ID | Name | Type                 | \# | Description |
|----|------|----------------------|----|-------------|
| 1  | **** | URIReferenceDatatype | 1  | **alias** -  |

**********

| Type Name                | Type Definition       | Description                                                                                           |
|--------------------------|-----------------------|-------------------------------------------------------------------------------------------------------|
| **URIReferenceDatatype** | String /uri-reference | A URI Reference, either a URI or a relative-reference, formatted according to section 4.1 of RFC3986. |

**********

An integer value that is equal to or greater than 0.

**Type: NonNegativeIntegerDatatype (Choice(allOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | IntegerDatatype | 1  | **c1** -    |
| 2  | **** | Number          | 1  | **c2** -    |

**********

| Type Name           | Type Definition | Description           |
|---------------------|-----------------|-----------------------|
| **IntegerDatatype** | Integer         | A whole number value. |

**********

An integer value that is greater than 0.

**Type: PositiveIntegerDatatype (Choice(allOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | IntegerDatatype | 1  | **c1** -    |
| 2  | **** | Number          | 1  | **c2** -    |

**********

| Type Name         | Type Definition                                    | Description                                                                                                                  |
|-------------------|----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| **TokenDatatype** | String{pattern="^(\p{L}|_)(\p{L}|\p{N}|[.\-_])*$"} | A non-colonized name as defined by XML Schema Part 2: Datatypes Second Edition. https://www.w3.org/TR/xmlschema11-2/#NCName. |

**********

| Type Name       | Type Definition                                      | Description                                                           |
|-----------------|------------------------------------------------------|-----------------------------------------------------------------------|
| **URIDatatype** | String{pattern="^[a-zA-Z][a-zA-Z0-9+\-.]+:.+$"} /uri | A universal resource identifier (URI) formatted according to RFC3986. |

**********

| Type Name        | Type Definition                                                                                             | Description                                                        |
|------------------|-------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------|
| **UUIDDatatype** | String{pattern="^[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-[45][0-9A-Fa-f]{3}-[89ABab][0-9A-Fa-f]{3}-[0-9A-Fa-f]{12}$"} | A type 4 ('random' or 'pseudorandom') or type 5 UUID per RFC 4122. |

**********
