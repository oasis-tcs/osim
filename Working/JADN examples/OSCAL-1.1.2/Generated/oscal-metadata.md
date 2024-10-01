       package: "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-metadata"
    namespaces: [["c", "http://csrc.nist.gov/ns/oscal/1.1.2/oscal-common"]]
        config: {"$MaxString": 1000, "$Sys": ".", "$TypeName": "^[$A-Z][-.$A-Za-z0-9]{0,96}$", "$FieldName": "^[$a-z][-_$A-Za-z0-9]{0,63}$"}
         roots: ["Back-matter", "Metadata", "Responsible-role", "Role-id"]

A collection of resources that may be referenced from within the OSCAL document instance.

**Type: Back-matter (Record)**

| ID | Name          | Type                  | \#    | Description |
|----|---------------|-----------------------|-------|-------------|
| 1  | **resources** | Back-matter.resources | 0..\* |             |

**********

A resource associated with content in the containing document instance. A resource may be directly included in the document using base64 encoding or may point to one or more equivalent internet resources.

**Type: Back-matter.resources (Record)**

| ID | Name             | Type                           | \#    | Description                                                                                     |
|----|------------------|--------------------------------|-------|-------------------------------------------------------------------------------------------------|
| 1  | **uuid**         | c:UUIDDatatype                 | 1     | A unique identifier for a resource.                                                             |
| 2  | **title**        | String                         | 0..1  | An optional name given to the resource, which may be used by a tool for display and navigation. |
| 3  | **description**  | String                         | 0..1  | An optional short summary of the resource used to indicate the purpose of the resource.         |
| 4  | **props**        | Property                       | 0..\* |                                                                                                 |
| 5  | **document-ids** | Document-id                    | 0..\* |                                                                                                 |
| 6  | **citation**     | Back-matter.resources.citation | 0..1  | An optional citation consisting of end note text using structured markup.                       |
| 7  | **rlinks**       | Back-matter.resources.rlinks   | 0..\* |                                                                                                 |
| 8  | **base64**       | Back-matter.resources.base64   | 0..1  | A resource encoded using the Base64 alphabet defined by RFC 2045.                               |
| 9  | **remarks**      | Remarks                        | 0..1  |                                                                                                 |

**********

An attribute, characteristic, or quality of the containing object expressed as a namespace qualified name/value pair.

**Type: Property (Record)**

| ID | Name        | Type             | \#   | Description                                                                                                                                         |
|----|-------------|------------------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **name**    | c:TokenDatatype  | 1    | A textual label, within a namespace, that uniquely identifies a specific attribute, characteristic, or quality of the property's containing object. |
| 2  | **uuid**    | c:UUIDDatatype   | 0..1 | A unique identifier for a property.                                                                                                                 |
| 3  | **ns**      | c:URIDatatype    | 0..1 | A namespace qualifying the property's name. This allows different organizations to associate distinct semantics with the same name.                 |
| 4  | **value**   | c:StringDatatype | 1    | Indicates the value of the attribute, characteristic, or quality.                                                                                   |
| 5  | **class**   | c:TokenDatatype  | 0..1 | A textual label that provides a sub-type or characterization of the property's name.                                                                |
| 6  | **group**   | c:TokenDatatype  | 0..1 | An identifier for relating distinct sets of properties.                                                                                             |
| 7  | **remarks** | Remarks          | 0..1 |                                                                                                                                                     |

**********

| Type Name   | Type Definition | Description                                        |
|-------------|-----------------|----------------------------------------------------|
| **Remarks** | String          | Additional commentary about the containing object. |

**********

A document identifier qualified by an identifier scheme.

**Type: Document-id (Record)**

| ID | Name           | Type               | \#   | Description                                                                                                                                                  |
|----|----------------|--------------------|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **scheme**     | Document-id.scheme | 0..1 | Qualifies the kind of document identifier using a URI. If the scheme is not provided the value of the element will be interpreted as a string of characters. |
| 2  | **identifier** | c:StringDatatype   | 1    |                                                                                                                                                              |

**********

Qualifies the kind of document identifier using a URI. If the scheme is not provided the value of the element will be interpreted as a string of characters.

**Type: Document-id.scheme (Choice(anyOf))**

| ID | Name | Type                 | \# | Description |
|----|------|----------------------|----|-------------|
| 1  | **** | c:URIDatatype        | 1  | **c1** -    |
| 2  | **** | Document-id.scheme.2 | 1  | **c2** -    |

**********

**Type: Document-id.scheme.2 (Enumerated)**

| ID | Item                    | Description |
|----|-------------------------|-------------|
| 1  | **http://www.doi.org/** |             |

**********

An optional citation consisting of end note text using structured markup.

**Type: Back-matter.resources.citation (Record)**

| ID | Name      | Type     | \#    | Description              |
|----|-----------|----------|-------|--------------------------|
| 1  | **text**  | String   | 1     | A line of citation text. |
| 2  | **props** | Property | 0..\* |                          |
| 3  | **links** | Link     | 0..\* |                          |

**********

A reference to a local or remote resource, that has a specific relation to the containing object.

**Type: Link (Record)**

| ID | Name                  | Type                   | \#   | Description                                                                                                                                                                             |
|----|-----------------------|------------------------|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **href**              | c:URIReferenceDatatype | 1    | A resolvable URL reference to a resource.                                                                                                                                               |
| 2  | **rel**               | Link.rel               | 0..1 | Describes the type of relationship provided by the link's hypertext reference. This can be an indicator of the link's purpose.                                                          |
| 3  | **media-type**        | c:StringDatatype       | 0..1 | A label that indicates the nature of a resource, as a data serialization or format.                                                                                                     |
| 4  | **resource-fragment** | c:StringDatatype       | 0..1 | In case where the href points to a back-matter/resource, this value will indicate the URI fragment to append to any rlink associated with the resource. This value MUST be URI encoded. |
| 5  | **text**              | String                 | 0..1 | A textual label to associate with the link, which may be used for presentation in a tool.                                                                                               |

**********

Describes the type of relationship provided by the link's hypertext reference. This can be an indicator of the link's purpose.

**Type: Link.rel (Choice(anyOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | c:TokenDatatype | 1  | **c1** -    |
| 2  | **** | Link.rel.2      | 1  | **c2** -    |

**********

**Type: Link.rel.2 (Enumerated)**

| ID | Item          | Description |
|----|---------------|-------------|
| 1  | **reference** |             |

**********

A URL-based pointer to an external resource with an optional hash for verification and change detection.

**Type: Back-matter.resources.rlinks (Record)**

| ID | Name           | Type                   | \#    | Description                                                                         |
|----|----------------|------------------------|-------|-------------------------------------------------------------------------------------|
| 1  | **href**       | c:URIReferenceDatatype | 1     | A resolvable URL pointing to the referenced resource.                               |
| 2  | **media-type** | c:StringDatatype       | 0..1  | A label that indicates the nature of a resource, as a data serialization or format. |
| 3  | **hashes**     | Hash                   | 0..\* |                                                                                     |

**********

A representation of a cryptographic digest generated over a resource using a specified hash algorithm.

**Type: Hash (Record)**

| ID | Name          | Type             | \# | Description                                   |
|----|---------------|------------------|----|-----------------------------------------------|
| 1  | **algorithm** | Hash.algorithm   | 1  | The digest method by which a hash is derived. |
| 2  | **value**     | c:StringDatatype | 1  |                                               |

**********

The digest method by which a hash is derived.

**Type: Hash.algorithm (Choice(anyOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **c1** -    |
| 2  | **** | Hash.algorithm.2 | 1  | **c2** -    |

**********

**Type: Hash.algorithm.2 (Enumerated)**

| ID | Item         | Description |
|----|--------------|-------------|
| 1  | **SHA-224**  |             |
| 2  | **SHA-256**  |             |
| 3  | **SHA-384**  |             |
| 4  | **SHA-512**  |             |
| 5  | **SHA3-224** |             |
| 6  | **SHA3-256** |             |
| 7  | **SHA3-384** |             |
| 8  | **SHA3-512** |             |

**********

A resource encoded using the Base64 alphabet defined by RFC 2045.

**Type: Back-matter.resources.base64 (Record)**

| ID | Name           | Type             | \#   | Description                                                                                                                                                 |
|----|----------------|------------------|------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **filename**   | c:TokenDatatype  | 0..1 | Name of the file before it was encoded as Base64 to be embedded in a resource. This is the name that will be assigned to the file when the file is decoded. |
| 2  | **media-type** | c:StringDatatype | 0..1 | A label that indicates the nature of a resource, as a data serialization or format.                                                                         |
| 3  | **value**      | c:Base64Datatype | 1    |                                                                                                                                                             |

**********

Provides information about the containing document, and defines concepts that are shared across the document.

**Type: Metadata (Record)**

| ID | Name                    | Type               | \#    | Description                                                                           |
|----|-------------------------|--------------------|-------|---------------------------------------------------------------------------------------|
| 1  | **title**               | String             | 1     | A name given to the document, which may be used by a tool for display and navigation. |
| 2  | **published**           | Published          | 0..1  |                                                                                       |
| 3  | **last-modified**       | Last-modified      | 1     |                                                                                       |
| 4  | **version**             | Version            | 1     |                                                                                       |
| 5  | **oscal-version**       | Oscal-version      | 1     |                                                                                       |
| 6  | **revisions**           | Metadata.revisions | 0..\* |                                                                                       |
| 7  | **document-ids**        | Document-id        | 0..\* |                                                                                       |
| 8  | **props**               | Property           | 0..\* |                                                                                       |
| 9  | **links**               | Link               | 0..\* |                                                                                       |
| 10 | **roles**               | Metadata.roles     | 0..\* |                                                                                       |
| 11 | **locations**           | Metadata.locations | 0..\* |                                                                                       |
| 12 | **parties**             | Metadata.parties   | 0..\* |                                                                                       |
| 13 | **responsible-parties** | Responsible-party  | 0..\* |                                                                                       |
| 14 | **actions**             | Action             | 0..\* |                                                                                       |
| 15 | **remarks**             | Remarks            | 0..1  |                                                                                       |

**********

The date and time the document was last made available.

**Type: Published (Choice(allOf))**

| ID | Name | Type                           | \# | Description |
|----|------|--------------------------------|----|-------------|
| 1  | **** | c:DateTimeWithTimezoneDatatype | 1  | **alias** -  |

**********

The date and time the document was last stored for later retrieval.

**Type: Last-modified (Choice(allOf))**

| ID | Name | Type                           | \# | Description |
|----|------|--------------------------------|----|-------------|
| 1  | **** | c:DateTimeWithTimezoneDatatype | 1  | **alias** -  |

**********

Used to distinguish a specific revision of an OSCAL document from other previous and future versions.

**Type: Version (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **alias** -  |

**********

The OSCAL model version the document was authored against and will conform to as valid.

**Type: Oscal-version (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **alias** -  |

**********

An entry in a sequential list of revisions to the containing document, expected to be in reverse chronological order (i.e. latest first).

**Type: Metadata.revisions (Record)**

| ID | Name              | Type          | \#    | Description                                                                                    |
|----|-------------------|---------------|-------|------------------------------------------------------------------------------------------------|
| 1  | **title**         | String        | 0..1  | A name given to the document revision, which may be used by a tool for display and navigation. |
| 2  | **published**     | Published     | 0..1  |                                                                                                |
| 3  | **last-modified** | Last-modified | 0..1  |                                                                                                |
| 4  | **version**       | Version       | 1     |                                                                                                |
| 5  | **oscal-version** | Oscal-version | 0..1  |                                                                                                |
| 6  | **props**         | Property      | 0..\* |                                                                                                |
| 7  | **links**         | Link          | 0..\* |                                                                                                |
| 8  | **remarks**       | Remarks       | 0..1  |                                                                                                |

**********

Defines a function, which might be assigned to a party in a specific situation.

**Type: Metadata.roles (Record)**

| ID | Name            | Type             | \#    | Description                                                                       |
|----|-----------------|------------------|-------|-----------------------------------------------------------------------------------|
| 1  | **id**          | c:TokenDatatype  | 1     | A unique identifier for the role.                                                 |
| 2  | **title**       | String           | 1     | A name given to the role, which may be used by a tool for display and navigation. |
| 3  | **short-name**  | c:StringDatatype | 0..1  | A short common name, abbreviation, or acronym for the role.                       |
| 4  | **description** | String           | 0..1  | A summary of the role's purpose and associated responsibilities.                  |
| 5  | **props**       | Property         | 0..\* |                                                                                   |
| 6  | **links**       | Link             | 0..\* |                                                                                   |
| 7  | **remarks**     | Remarks          | 0..1  |                                                                                   |

**********

A physical point of presence, which may be associated with people, organizations, or other concepts within the current or linked OSCAL document.

**Type: Metadata.locations (Record)**

| ID | Name                  | Type             | \#    | Description                                                                           |
|----|-----------------------|------------------|-------|---------------------------------------------------------------------------------------|
| 1  | **uuid**              | c:UUIDDatatype   | 1     | A unique ID for the location, for reference.                                          |
| 2  | **title**             | String           | 0..1  | A name given to the location, which may be used by a tool for display and navigation. |
| 3  | **address**           | Address          | 0..1  |                                                                                       |
| 4  | **email-addresses**   | Email-address    | 0..\* |                                                                                       |
| 5  | **telephone-numbers** | Telephone-number | 0..\* |                                                                                       |
| 6  | **urls**              | c:URIDatatype    | 0..\* |                                                                                       |
| 7  | **props**             | Property         | 0..\* |                                                                                       |
| 8  | **links**             | Link             | 0..\* |                                                                                       |
| 9  | **remarks**           | Remarks          | 0..1  |                                                                                       |

**********

A postal address for the location.

**Type: Address (Record)**

| ID | Name            | Type             | \#    | Description                                                             |
|----|-----------------|------------------|-------|-------------------------------------------------------------------------|
| 1  | **type**        | Address.type     | 0..1  | Indicates the type of address.                                          |
| 2  | **addr-lines**  | Addr-line        | 0..\* |                                                                         |
| 3  | **city**        | c:StringDatatype | 0..1  | City, town or geographical region for the mailing address.              |
| 4  | **state**       | c:StringDatatype | 0..1  | State, province or analogous geographical region for a mailing address. |
| 5  | **postal-code** | c:StringDatatype | 0..1  | Postal or ZIP code for mailing address.                                 |
| 6  | **country**     | c:StringDatatype | 0..1  | The ISO 3166-1 alpha-2 country code for the mailing address.            |

**********

Indicates the type of address.

**Type: Address.type (Choice(anyOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | c:TokenDatatype | 1  | **c1** -    |
| 2  | **** | Address.type.2  | 1  | **c2** -    |

**********

**Type: Address.type.2 (Enumerated)**

| ID | Item     | Description |
|----|----------|-------------|
| 1  | **home** |             |
| 2  | **work** |             |

**********

A single line of an address.

**Type: Addr-line (Choice(allOf))**

| ID | Name | Type             | \# | Description |
|----|------|------------------|----|-------------|
| 1  | **** | c:StringDatatype | 1  | **alias** -  |

**********

An email address as defined by RFC 5322 Section 3.4.1.

**Type: Email-address (Choice(allOf))**

| ID | Name | Type                   | \# | Description |
|----|------|------------------------|----|-------------|
| 1  | **** | c:EmailAddressDatatype | 1  | **alias** -  |

**********

A telephone service number as defined by ITU-T E.164.

**Type: Telephone-number (Record)**

| ID | Name       | Type                  | \#   | Description                         |
|----|------------|-----------------------|------|-------------------------------------|
| 1  | **type**   | Telephone-number.type | 0..1 | Indicates the type of phone number. |
| 2  | **number** | c:StringDatatype      | 1    |                                     |

**********

Indicates the type of phone number.

**Type: Telephone-number.type (Choice(anyOf))**

| ID | Name | Type                    | \# | Description |
|----|------|-------------------------|----|-------------|
| 1  | **** | c:StringDatatype        | 1  | **c1** -    |
| 2  | **** | Telephone-number.type.2 | 1  | **c2** -    |

**********

**Type: Telephone-number.type.2 (Enumerated)**

| ID | Item       | Description |
|----|------------|-------------|
| 1  | **home**   |             |
| 2  | **office** |             |
| 3  | **mobile** |             |

**********

An organization or person, which may be associated with roles or other concepts within the current or linked OSCAL document.

**Type: Metadata.parties (Record)**

| ID | Name                        | Type                          | \#    | Description                                                                             |
|----|-----------------------------|-------------------------------|-------|-----------------------------------------------------------------------------------------|
| 1  | **uuid**                    | c:UUIDDatatype                | 1     | A unique identifier for the party.                                                      |
| 2  | **type**                    | Metadata.parties.type         | 1     | A category describing the kind of party the object describes.                           |
| 3  | **name**                    | c:StringDatatype              | 0..1  | The full name of the party. This is typically the legal name associated with the party. |
| 4  | **short-name**              | c:StringDatatype              | 0..1  | A short common name, abbreviation, or acronym for the party.                            |
| 5  | **external-ids**            | Metadata.parties.external-ids | 0..\* |                                                                                         |
| 6  | **props**                   | Property                      | 0..\* |                                                                                         |
| 7  | **links**                   | Link                          | 0..\* |                                                                                         |
| 8  | **email-addresses**         | Email-address                 | 0..\* |                                                                                         |
| 9  | **telephone-numbers**       | Telephone-number              | 0..\* |                                                                                         |
| 10 | **addresses**               | Address                       | 0..\* |                                                                                         |
| 11 | **location-uuids**          | Location-uuid                 | 0..\* |                                                                                         |
| 12 | **member-of-organizations** | c:UUIDDatatype                | 0..\* |                                                                                         |
| 13 | **remarks**                 | Remarks                       | 0..1  |                                                                                         |

**********

A category describing the kind of party the object describes.

**Type: Metadata.parties.type (Choice(allOf))**

| ID | Name | Type                    | \# | Description |
|----|------|-------------------------|----|-------------|
| 1  | **** | c:StringDatatype        | 1  | **c1** -    |
| 2  | **** | Metadata.parties.type.2 | 1  | **c2** -    |

**********

**Type: Metadata.parties.type.2 (Enumerated)**

| ID | Item             | Description |
|----|------------------|-------------|
| 1  | **person**       |             |
| 2  | **organization** |             |

**********

An identifier for a person or organization using a designated scheme. e.g. an Open Researcher and Contributor ID (ORCID).

**Type: Metadata.parties.external-ids (Record)**

| ID | Name       | Type                                 | \# | Description                                |
|----|------------|--------------------------------------|----|--------------------------------------------|
| 1  | **scheme** | Metadata.parties.external-ids.scheme | 1  | Indicates the type of external identifier. |
| 2  | **id**     | c:StringDatatype                     | 1  |                                            |

**********

Indicates the type of external identifier.

**Type: Metadata.parties.external-ids.scheme (Choice(anyOf))**

| ID | Name | Type                                   | \# | Description |
|----|------|----------------------------------------|----|-------------|
| 1  | **** | c:URIDatatype                          | 1  | **c1** -    |
| 2  | **** | Metadata.parties.external-ids.scheme.2 | 1  | **c2** -    |

**********

**Type: Metadata.parties.external-ids.scheme.2 (Enumerated)**

| ID | Item                  | Description |
|----|-----------------------|-------------|
| 1  | **http://orcid.org/** |             |

**********

Reference to a location by UUID.

**Type: Location-uuid (Choice(allOf))**

| ID | Name | Type           | \# | Description |
|----|------|----------------|----|-------------|
| 1  | **** | c:UUIDDatatype | 1  | **alias** -  |

**********

A reference to a set of persons and/or organizations that have responsibility for performing the referenced role in the context of the containing object.

**Type: Responsible-party (Record)**

| ID | Name            | Type            | \#    | Description                                 |
|----|-----------------|-----------------|-------|---------------------------------------------|
| 1  | **role-id**     | c:TokenDatatype | 1     | A reference to a role performed by a party. |
| 2  | **party-uuids** | Party-uuid      | 1..\* |                                             |
| 3  | **props**       | Property        | 0..\* |                                             |
| 4  | **links**       | Link            | 0..\* |                                             |
| 5  | **remarks**     | Remarks         | 0..1  |                                             |

**********

Reference to a party by UUID.

**Type: Party-uuid (Choice(allOf))**

| ID | Name | Type           | \# | Description |
|----|------|----------------|----|-------------|
| 1  | **** | c:UUIDDatatype | 1  | **alias** -  |

**********

An action applied by a role within a given party to the content.

**Type: Action (Record)**

| ID | Name                    | Type                           | \#    | Description                                                                                                                                                                                     |
|----|-------------------------|--------------------------------|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | **uuid**                | c:UUIDDatatype                 | 1     | A unique identifier that can be used to reference this defined action elsewhere in an OSCAL document. A UUID should be consistently used for a given location across revisions of the document. |
| 2  | **date**                | c:DateTimeWithTimezoneDatatype | 0..1  | The date and time when the action occurred.                                                                                                                                                     |
| 3  | **type**                | c:TokenDatatype                | 1     | The type of action documented by the assembly, such as an approval.                                                                                                                             |
| 4  | **system**              | c:URIDatatype                  | 1     | Specifies the action type system used.                                                                                                                                                          |
| 5  | **props**               | Property                       | 0..\* |                                                                                                                                                                                                 |
| 6  | **links**               | Link                           | 0..\* |                                                                                                                                                                                                 |
| 7  | **responsible-parties** | Responsible-party              | 0..\* |                                                                                                                                                                                                 |
| 8  | **remarks**             | Remarks                        | 0..1  |                                                                                                                                                                                                 |

**********

A reference to a role with responsibility for performing a function relative to the containing object, optionally associated with a set of persons and/or organizations that perform that role.

**Type: Responsible-role (Record)**

| ID | Name            | Type            | \#    | Description                                                |
|----|-----------------|-----------------|-------|------------------------------------------------------------|
| 1  | **role-id**     | c:TokenDatatype | 1     | A human-oriented identifier reference to a role performed. |
| 2  | **props**       | Property        | 0..\* |                                                            |
| 3  | **links**       | Link            | 0..\* |                                                            |
| 4  | **party-uuids** | Party-uuid      | 0..\* |                                                            |
| 5  | **remarks**     | Remarks         | 0..1  |                                                            |

**********

Reference to a role by UUID.

**Type: Role-id (Choice(allOf))**

| ID | Name | Type            | \# | Description |
|----|------|-----------------|----|-------------|
| 1  | **** | c:TokenDatatype | 1  | **alias** -  |

**********
