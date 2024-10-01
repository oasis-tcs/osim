         title: "SPDX v2.3 Information Model"
       package: "http://spdx.org/spdx-v2.3"
       license: "CC0-1.0"
    namespaces: {"ll": "http://spdx.org/license-list"}
       exports: ["Document", "TagMap$"]
        config: {"$FieldName": "^[a-zA-Z][_A-Za-z0-9]{0,63}$", "$MaxElements": 1000}

**Type: Document (Record)**

| ID | Name                        | Type                  | \#    | Description                                                   |
|----|-----------------------------|-----------------------|-------|---------------------------------------------------------------|
| 1  | **spdxVersion**             | SpdxVersion           | 1     | 6.1 SPDX-M.N where M and N are major and minor version number |
| 2  | **dataLicense**             | SPDX-METADATA-LICENSE | 1     |                                                               |
| 3  | **SPDXID**                  | SPDXREF-DOCUMENT      | 1     |                                                               |
| 4  | **name**                    | String                | 1     | 6.4 Name of this document as designated by creator            |
| 5  | **documentNamespace**       | URI                   | 1     | 6.5 Absolute URI (no #fragment)                               |
| 6  | **externalDocumentRefs**    | ExternalDocumentRef   | 0..\* | 6.6                                                           |
| 7  | **licenseListVersion**      | String                | 0..1  | 6.7                                                           |
| 8  | **creator**                 | Creator               | 1..\* | 6.8 Person / Organization / Tool                              |
| 9  | **created**                 | Timestamp             | 1     | 6.9 RFC-3339 string YYYY-MM-DDThh:mm:ssZ                      |
| 10 | **creatorComment**          | String                | 0..1  | 6.10 Comments about creation of the SPDX document             |
| 11 | **documentComment**         | String                | 0..1  | 6.11 Comments to consumers of the SPDX document               |
| 12 | **packages**                | PackageInfo           | 0..\* | Section 7 Package Information                                 |
| 13 | **files**                   | FileInfo              | 0..\* | Section 8 File Information                                    |
| 14 | **snippets**                | SnippetInfo           | 0..\* | Section 9 Snippet Information                                 |
| 15 | **extractedLicensingInfos** | ExtraLicensingInfo    | 0..\* | Section 10 Other Licensing Information                        |
| 16 | **relationships**           | Relationship          | 0..\* | Section 11 Relationships                                      |
| 17 | **annotations**             | Annotation            | 0..\* | Section 12 Annotations                                        |
| 18 | **reviews**                 | Review                | 0..\* | Section 13 Review Information (deprecated)                    |

**********

**Type: ExternalDocumentRef (Record)**

| ID | Name                   | Type        | \# | Description |
|----|------------------------|-------------|----|-------------|
| 1  | **externalDocumentId** | DocumentRef | 1  |             |
| 2  | **spdxDocument**       | URI         | 1  |             |
| 3  | **checksum**           | Checksum    | 1  |             |

**********

**Type: CreationInfo (Record)**

| ID | Name                   | Type              | \#    | Description |
|----|------------------------|-------------------|-------|-------------|
| 1  | **licenseListVersion** | MajorMinorVersion | 0..1  |             |
| 2  | **creators**           | Entity            | 1..\* |             |
| 3  | **created**            | Timestamp         | 1     |             |
| 4  | **comment**            | String            | 1     |             |

**********

**Type: PackageInfo (Record)**

| ID | Name                        | Type                    | \#    | Description                                            |
|----|-----------------------------|-------------------------|-------|--------------------------------------------------------|
| 1  | **name**                    | String                  | 1     |                                                        |
| 2  | **SPDXID**                  | Key(SpdxRef)            | 1     |                                                        |
| 3  | **versionInfo**             | VersionInfo             | 0..1  |                                                        |
| 4  | **packageFileName**         | PackageFileName         | 0..1  |                                                        |
| 5  | **supplier**                | PackageSupplier         | 0..1  |                                                        |
| 6  | **originator**              | Entity                  | 0..1  | Person or Org, not Tool                                |
| 7  | **downloadLocation**        | DownloadLocation        | 1     | mandatory                                              |
| 8  | **filesAnalyzed**           | Boolean                 | 0..1  | Default True.   7.8.1                                  |
| 9  | **packageVerificationCode** | PackageVerificationCode | 0..1  | optional if filesAnalyzed is True, prohibited if False |
| 10 | **checksums**               | Checksum                | 0..\* |                                                        |
| 11 | **homepage**                | URI                     | 0..1  | URI, NONE, NOASSERTION                                 |
| 12 | **sourceInfo**              | String                  | 0..1  |                                                        |
| 13 | **licenseConcluded**        | LicenseExpression       | 0..1  | 3.13.3 says mandatory                                  |
| 14 | **licenseInfoFromFiles**    | LicenseIdentifier       | 0..\* | optional if filesAnalyzed is True, prohibited if False |
| 15 | **licenseDeclared**         | LicenseExpression       | 1     |                                                        |
| 16 | **licenseComments**         | String                  | 0..1  |                                                        |
| 17 | **copyrightText**           | String                  | 0..1  | 3.17.3 says mandatory                                  |
| 18 | **summary**                 | String                  | 0..1  |                                                        |
| 19 | **description**             | String                  | 0..1  |                                                        |
| 20 | **comment**                 | String                  | 0..1  |                                                        |
| 21 | **externalRefs**            | ExternalRef             | 0..\* | ExternalRef includes category/type/locator/comment.    |
| 22 | **attributionTexts**        | String                  | 0..\* |                                                        |

**********

**Type: FileInfo (Record)**

| ID | Name                   | Type              | \#    | Description                                                                     |
|----|------------------------|-------------------|-------|---------------------------------------------------------------------------------|
| 1  | **fileName**           | String            | 1     |                                                                                 |
| 2  | **SPDXID**             | Key(SpdxRef)      | 1     |                                                                                 |
| 3  | **versionInfo**        | VersionInfo       | 0..1  | not in spec                                                                     |
| 4  | **fileTypes**          | FileType          | 0..\* |                                                                                 |
| 5  | **checksums**          | Checksum          | 0..\* | 4.4.3 says mandatory                                                            |
| 6  | **licenseConcluded**   | LicenseExpression | 0..1  | 4.5.3 says mandatory                                                            |
| 7  | **licenseInfoInFiles** | LicenseExpression | 0..\* | 4.6.3 says mandatory                                                            |
| 8  | **licenseDeclared**    | String            | 0..1  | not in spec                                                                     |
| 9  | **licenseComments**    | String            | 0..1  |                                                                                 |
| 10 | **copyrightText**      | String            | 0..1  | 4.8.3 says mandatory                                                            |
| 11 | **comment**            | String            | 0..1  |                                                                                 |
| 12 | **noticeText**         | String            | 0..1  |                                                                                 |
| 13 | **fileContributors**   | FileContributor   | 0..\* | 4.14.3 says [0..*] (array of strings)                                           |
| 14 | **externalRefs**       | ExternalRef       | 0..\* | not in spec                                                                     |
| 15 | **attributionText**    | String            | 0..\* | just attributions?                                                              |
| 16 | **annotations**        | Annotation        | 0..\* | 8.4.6: For RDF annotations are a property of Document, Package, File or Snippet |
| 17 | **artifactOf**         | Artifact          | 0..\* | deprecated - delete before new version                                          |
| 18 | **dependencies**       | String            | 0..\* | deprecated - delete before new version                                          |

**********

**Type: SnippetInfo (Record)**

| ID | Name                      | Type              | \#    | Description                                                                     |
|----|---------------------------|-------------------|-------|---------------------------------------------------------------------------------|
| 1  | **SPDXID**                | Key(SpdxRef)      | 1     |                                                                                 |
| 2  | **snippetFromFile**       | SpdxRef           | 1     |                                                                                 |
| 3  | **ranges**                | Range             | 1..\* |                                                                                 |
| 4  | **licenseConcluded**      | LicenseExpression | 1     |                                                                                 |
| 5  | **licenseInfoInSnippets** | LicenseExpression | 0..\* |                                                                                 |
| 6  | **licenseComments**       | String            | 0..1  |                                                                                 |
| 7  | **copyrightText**         | String            | 1     |                                                                                 |
| 8  | **comment**               | String            | 0..1  |                                                                                 |
| 9  | **name**                  | String            | 0..1  |                                                                                 |
| 10 | **attributionText**       | String            | 0..\* |                                                                                 |
| 11 | **annotations**           | Annotation        | 0..\* | 8.4.6: For RDF annotations are a property of Document, Package, File or Snippet |

**********

**Type: Relationship (Record)**

| ID | Name                   | Type             | \#   | Description                                          |
|----|------------------------|------------------|------|------------------------------------------------------|
| 1  | **spdxElementId**      | Key              | 1    |                                                      |
| 2  | **relationshipType**   | RelationshipType | 1    |                                                      |
| 3  | **relatedSpdxElement** | SpdxQualifiedRef | 1    | Overloaded multiple targets, consider RelatedElement |
| 4  | **comment**            | String           | 0..1 |                                                      |

**********

**Type: Annotation (Record)**

| ID | Name               | Type           | \# | Description |
|----|--------------------|----------------|----|-------------|
| 1  | **annotator**      | Entity         | 1  |             |
| 2  | **annotationDate** | Timestamp      | 1  |             |
| 3  | **annotationType** | AnnotationType | 1  |             |
| 4  | **comment**        | String         | 1  |             |

**********

Deprecated since v2.0

**Type: Review (Record)**

| ID | Name           | Type      | \#   | Description                   |
|----|----------------|-----------|------|-------------------------------|
| 1  | **reviewer**   | Creator   | 0..1 | Person / Organization / Tool  |
| 2  | **reviewDate** | Timestamp | 0..1 | mandatory if reviewer present |
| 3  | **comment**    | String    | 1    | review comment                |

**********

| Type Name       | Type Definition                           | Description                                                   |
|-----------------|-------------------------------------------|---------------------------------------------------------------|
| **SpdxVersion** | String{pattern="^SPDX-\d{1,2}\.\d{1,4}$"} | Limit digits to below the absurd, or enumerate valid versions |

**********

| Type Name       | Type Definition | Description       |
|-----------------|-----------------|-------------------|
| **SpdxLicense** | String          | Import ll:License |

**********

| Type Name            | Type Definition                      | Description |
|----------------------|--------------------------------------|-------------|
| **SPDXREF-DOCUMENT** | String{pattern="^SPDXRef-DOCUMENT$"} |             |

**********

| Type Name   | Type Definition                                   | Description                               |
|-------------|---------------------------------------------------|-------------------------------------------|
| **SpdxRef** | String{pattern="^SPDXRef-[-+\.a-zA-Z0-9]{1,64}$"} | 3.2.4: SPDXRef-[idstring] - no underscore |

**********

| Type Name       | Type Definition                                       | Description |
|-----------------|-------------------------------------------------------|-------------|
| **DocumentRef** | String{pattern="^DocumentRef-[-+\.a-zA-Z0-9]{1,64}$"} |             |

**********

| Type Name            | Type Definition | Description               |
|----------------------|-----------------|---------------------------|
| **SpdxQualifiedRef** | String          | [DocumentRef-xxx:]SpdxRef |

**********

| Type Name      | Type Definition                                      | Description |
|----------------|------------------------------------------------------|-------------|
| **LicenseRef** | String{pattern="^LicenseRef-[-+\.a-zA-Z0-9]{1,64}$"} |             |

**********

| Type Name             | Type Definition                      | Description |
|-----------------------|--------------------------------------|-------------|
| **MajorMinorVersion** | String{pattern="^\d{1,2}\.\d{1,4}$"} |             |

**********

| Type Name       | Type Definition | Description            |
|-----------------|-----------------|------------------------|
| **VersionInfo** | String          | use versioning scheme? |

**********

| Type Name           | Type Definition | Description |
|---------------------|-----------------|-------------|
| **PackageFileName** | String          |             |

**********

| Type Name     | Type Definition | Description                                                                   |
|---------------|-----------------|-------------------------------------------------------------------------------|
| **Timestamp** | String          | Define an ISO 8601 (or RFC 3339?) text representation format for Integer time |

**********

| Type Name | Type Definition | Description |
|-----------|-----------------|-------------|
| **URI**   | String /uri     |             |

**********

| Type Name            | Type Definition | Description                      |
|----------------------|-----------------|----------------------------------|
| **DownloadLocation** | String          | URI or SPDX-specific VCS schemes |

**********

| Type Name  | Type Definition | Description                                                                          |
|------------|-----------------|--------------------------------------------------------------------------------------|
| **Entity** | String          | Should be a Map instead of strings.  Spec doesn't require comma-separated tag-values |

**********

| Type Name           | Type Definition | Description |
|---------------------|-----------------|-------------|
| **FileContributor** | String          |             |

**********

at least one must be present

**Type: Entity-Alternate (Map{1..\*})**

| ID | Name             | Type   | \#   | Description                                |
|----|------------------|--------|------|--------------------------------------------|
| 1  | **person**       | String | 0..1 | validate person name with optional (email) |
| 2  | **organization** | String | 0..1 |                                            |
| 3  | **tool**         | String | 0..1 |                                            |

**********

| Type Name           | Type Definition | Description |
|---------------------|-----------------|-------------|
| **PackageSupplier** | String          |             |

**********

**Type: PackageVerificationCode (Record)**

| ID | Name                                     | Type            | \# | Description |
|----|------------------------------------------|-----------------|----|-------------|
| 1  | **packageVerificationCodeValue**         | Binary /x       | 1  |             |
| 2  | **packageVerificationCodeExcludedFiles** | PackageFileName | 1  |             |

**********

**Type: Checksum (Record)**

| ID | Name              | Type          | \# | Description |
|----|-------------------|---------------|----|-------------|
| 1  | **algorithm**     | HashAlgorithm | 1  |             |
| 2  | **checksumValue** | Binary /x     | 1  | just value? |

**********

md algorithms not recommended, better algorithms (blake, ripemd, ...) not listed

**Type: Checksum-Alternate (Map{1..\*})**

| ID | Name       | Type              | \#   | Description                                                    |
|----|------------|-------------------|------|----------------------------------------------------------------|
| 1  | **sha1**   | Binary{20..20} /x | 0..1 |                                                                |
| 2  | **sha224** | Binary{28..28} /x | 0..1 |                                                                |
| 3  | **sha256** | Binary{32..32} /x | 0..1 |                                                                |
| 4  | **sha384** | Binary{48..48} /x | 0..1 |                                                                |
| 5  | **sha512** | Binary{64..64} /x | 0..1 |                                                                |
| 6  | **md2**    | Binary{16..16} /x | 0..1 |                                                                |
| 7  | **md4**    | Binary{16..16} /x | 0..1 |                                                                |
| 8  | **md5**    | Binary{16..16} /x | 0..1 |                                                                |
| 9  | **md6**    | Binary /x         | 0..1 | Variable-length SHA-3 candidate, need e.g., md6-256 or md6-384 |

**********

**Type: ExternalRef (Record)**

| ID | Name                  | Type              | \#   | Description |
|----|-----------------------|-------------------|------|-------------|
| 1  | **referenceCategory** | ReferenceCategory | 1    |             |
| 2  | **referenceType**     | ReferenceType     | 1    |             |
| 3  | **referenceLocator**  | ReferenceLocator  | 1    |             |
| 4  | **comment**           | String            | 0..1 |             |

**********

| Type Name         | Type Definition                    | Description |
|-------------------|------------------------------------|-------------|
| **ReferenceType** | Enumerated(Enum[ReferenceLocator]) |             |

**********

annex F - external repository identifiers

**Type: ReferenceLocator (Choice)**

| ID | Name          | Type                  | \# | Description |
|----|---------------|-----------------------|----|-------------|
| 1  | **cpe22Type** | CPE22Type             | 1  |             |
| 2  | **cpe23Type** | CPE23Typ              | 1  |             |
| 3  | **advisory**  | URI                   | 1  |             |
| 4  | **fix**       | URI                   | 1  |             |
| 5  | **url**       | URI                   | 1  |             |
| 6  | **swid**      | SWID                  | 1  |             |
| 7  | **maven**     | Package-Maven-Central | 1  |             |
| 8  | **npm**       | Package-NPM           | 1  |             |
| 9  | **nuget**     | Package-Nuget         | 1  |             |
| 10 | **bower**     | Package-Bower         | 1  |             |
| 11 | **purl**      | Package-PURL          | 1  |             |
| 12 | **swh**       | PID-Swh               | 1  |             |
| 13 | **gitoid**    | PID-GitOID            | 1  |             |
| 99 | **other**     | String                | 1  |             |

**********

| Type Name     | Type Definition | Description                        |
|---------------|-----------------|------------------------------------|
| **CPE22Type** | String          | Add regexes to all reference types |

**********

| Type Name     | Type Definition | Description |
|---------------|-----------------|-------------|
| **CPE23Type** | String          |             |

**********

| Type Name | Type Definition | Description |
|-----------|-----------------|-------------|
| **SWID**  | String          |             |

**********

| Type Name                 | Type Definition | Description |
|---------------------------|-----------------|-------------|
| **Package-Maven-Central** | String          |             |

**********

| Type Name       | Type Definition | Description |
|-----------------|-----------------|-------------|
| **Package-NPM** | String          |             |

**********

| Type Name         | Type Definition | Description |
|-------------------|-----------------|-------------|
| **Package-Nuget** | String          |             |

**********

| Type Name        | Type Definition | Description |
|------------------|-----------------|-------------|
| **PackageBower** | String          |             |

**********

| Type Name       | Type Definition | Description |
|-----------------|-----------------|-------------|
| **PackagePurl** | String          |             |

**********

| Type Name   | Type Definition | Description |
|-------------|-----------------|-------------|
| **PID-Swh** | String          |             |

**********

| Type Name      | Type Definition | Description |
|----------------|-----------------|-------------|
| **PID-GitOID** | String          |             |

**********

| Type Name             | Type Definition | Description              |
|-----------------------|-----------------|--------------------------|
| **LicenseIdentifier** | String          | import from License List |

**********

| Type Name             | Type Definition | Description |
|-----------------------|-----------------|-------------|
| **LicenseExpression** | String          |             |

**********

Simplify - start and end shouldn't have different types and references

**Type: Range (Record)**

| ID | Name             | Type         | \# | Description |
|----|------------------|--------------|----|-------------|
| 1  | **startPointer** | RangePointer | 1  |             |
| 2  | **endPointer**   | RangePointer | 1  |             |

**********

**Type: RangePointer (Record{2..2})**

| ID | Name           | Type    | \#   | Description |
|----|----------------|---------|------|-------------|
| 1  | **offset**     | Integer | 0..1 |             |
| 2  | **lineNumber** | Integer | 0..1 |             |
| 3  | **reference**  | SpdxRef | 1    |             |

**********

Deprecated

**Type: Artifact (Record)**

| ID | Name           | Type   | \#   | Description |
|----|----------------|--------|------|-------------|
| 1  | **name**       | String | 1    |             |
| 2  | **homepage**   | URI    | 0..1 |             |
| 3  | **projectURI** | URI    | 0..1 |             |

**********

Fields after comment not defined in v2.2

**Type: ExtraLicensingInfo (Record)**

| ID | Name                              | Type       | \#    | Description |
|----|-----------------------------------|------------|-------|-------------|
| 1  | **licenseId**                     | LicenseRef | 0..1  |             |
| 2  | **extractedText**                 | String     | 1     |             |
| 3  | **name**                          | String     | 0..1  |             |
| 4  | **seeAlsos**                      | URI        | 0..\* |             |
| 5  | **comment**                       | String     | 0..1  |             |
| 6  | **isDeprecatedLicenseId**         | Boolean    | 0..1  |             |
| 7  | **isFsfLibre**                    | Boolean    | 0..1  |             |
| 8  | **isOsiApproved**                 | Boolean    | 0..1  |             |
| 9  | **licenseText**                   | String     | 0..1  |             |
| 10 | **licenseTextHtml**               | String     | 0..1  |             |
| 11 | **standardLicenseHeader**         | String     | 0..1  |             |
| 12 | **standardLicenseHeaderHtml**     | String     | 0..1  |             |
| 13 | **standardLicenseHeaderTemplate** | String     | 0..1  |             |
| 14 | **standardLicenseTemplate**       | String     | 0..1  |             |

**********

**Type: CrossRef (Record)**

| ID | Name              | Type      | \# | Description |
|----|-------------------|-----------|----|-------------|
| 1  | **url**           | URI       | 1  |             |
| 2  | **isLive**        | Boolean   | 1  |             |
| 3  | **isValid**       | Boolean   | 1  |             |
| 4  | **isWayBackLink** | Boolean   | 1  |             |
| 5  | **match**         | String    | 1  |             |
| 6  | **order**         | Integer   | 1  |             |
| 7  | **timestamp**     | Timestamp | 1  |             |

**********

**Type: AnnotationType (Enumerated)**

| ID | Item       | Description |
|----|------------|-------------|
| 1  | **REVIEW** |             |
| 9  | **OTHER**  |             |

**********

**Type: FileType (Enumerated)**

| ID | Item              | Description |
|----|-------------------|-------------|
| 1  | **SOURCE**        |             |
| 2  | **BINARY**        |             |
| 3  | **ARCHIVE**       |             |
| 4  | **APPLICATION**   |             |
| 5  | **AUDIO**         |             |
| 6  | **IMAGE**         |             |
| 7  | **TEXT**          |             |
| 8  | **VIDEO**         |             |
| 9  | **DOCUMENTATION** |             |
| 10 | **SPDX**          |             |
| 11 | **SHARED**        | Cybeats     |
| 99 | **OTHER**         |             |

**********

**Type: HashAlgorithm (Enumerated)**

| ID | Item       | Description |
|----|------------|-------------|
| 1  | **SHA1**   |             |
| 2  | **SHA224** |             |
| 3  | **SHA256** |             |
| 4  | **SHA384** |             |
| 5  | **SHA512** |             |
| 6  | **MD2**    |             |
| 7  | **MD4**    |             |
| 8  | **MD5**    |             |
| 9  | **MD6**    |             |

**********

no underscores

**Type: ReferenceCategory (Enumerated)**

| ID | Item                | Description |
|----|---------------------|-------------|
| 1  | **SECURITY**        |             |
| 2  | **PACKAGE-MANAGER** |             |
| 3  | **PERSISTENT-ID**   |             |
| 99 | **OTHER**           |             |

**********

**Type: RelationshipType (Enumerated)**

| ID | Item                       | Description      |
|----|----------------------------|------------------|
| 0  | **NONE**                   |                  |
| 1  | **DESCRIBES**              |                  |
| 2  | **DESCRIBED_BY**           |                  |
| 3  | **CONTAINS**               |                  |
| 4  | **CONTAINED_BY**           |                  |
| 5  | **DEPENDS_ON**             |                  |
| 6  | **DEPENENCY_OF**           |                  |
| 7  | **DEPENDENCY_MANIFEST_OF** |                  |
| 8  | **BUILD_+DEPENDENCY_OF**   |                  |
| 9  | **DEV_DEPENDENCY_OF**      |                  |
| 10 | **OPTIONAL_DEPENDENCY_OF** |                  |
| 11 | **PROVIDED_DEPENDENCY_OF** |                  |
| 12 | **TEST_DEPENDENCY_OF**     |                  |
| 13 | **RUNTIME_DEPENDENCY_OF**  |                  |
| 14 | **EXAMPLE_OF**             |                  |
| 15 | **GENERATES**              |                  |
| 16 | **GENERATED_FROM**         |                  |
| 17 | **ANCESTOR_OF**            |                  |
| 18 | **DESCENDANT_OF**          |                  |
| 19 | **VARIANT_OF**             |                  |
| 20 | **DISTRIBUTION_ARTIFACT**  |                  |
| 21 | **PATCH_FOR**              |                  |
| 22 | **PATCH_APPLIED**          |                  |
| 23 | **COPY_OF**                |                  |
| 24 | **FILE_ADDED**             |                  |
| 25 | **FILE_DELETED**           |                  |
| 26 | **FILE_MODIFIED**          |                  |
| 27 | **EXPANDED_FROM_ARCHIVE**  |                  |
| 28 | **DYNAMIC_LINK**           |                  |
| 29 | **STATIC_LINK**            |                  |
| 30 | **DATA_FILE_OF**           |                  |
| 31 | **TEST_CASE_OF**           |                  |
| 32 | **BUILD_TOOL_OF**          |                  |
| 33 | **DEF_TOOL_OF**            |                  |
| 34 | **TEST_OF**                |                  |
| 35 | **TEST_TOOL_OF**           |                  |
| 36 | **DOCUMENTATION_OF**       |                  |
| 37 | **OPTIONAL_COMPONENT_OF**  |                  |
| 38 | **METAFILE_OF**            |                  |
| 39 | **PACKAGE_OF**             |                  |
| 40 | **AMENDS**                 |                  |
| 41 | **PREREQUISITE_FOR**       |                  |
| 42 | **HAS_PREREQUISITE**       |                  |
| 98 | **NOASSERTION**            | should deprecate |
| 99 | **OTHER**                  |                  |

**********

Alias list: map of paths to tags

**Type: TagMap$ (Enumerated)**

| ID | Item                                                   | Description                    |
|----|--------------------------------------------------------|--------------------------------|
| 1  | **spdxVersion:SPDXVersion**                            |                                |
| 2  | **dataLicense:DataLicense**                            |                                |
| 3  | **SPDXID:SPDXID**                                      |                                |
| 4  | **name:DocumentName**                                  |                                |
| 5  | **documentNamespace:DocumentNamespace**                |                                |
| 6  | **externalDocumentRefs/*:ExternalDocumentRef**         | handle plural to multiple tags |
| 7  | **creationInfo/licenseListVersion:LicenseListVersion** |                                |
| 8  | **creationInfo/creators/*:Creator**                    |                                |
| 9  | **creationInfo/created:Created**                       |                                |
| 10 | **creationInfo/comment:CreatorComment**                |                                |
| 11 | **comment:DocumentComment**                            |                                |
| 12 | **packages/*:**                                        |                                |
| 13 | **files/*:**                                           |                                |
| 14 | **snippets/*:**                                        |                                |
| 15 | **hasExtractedLicensingInfos/*:**                      |                                |
| 16 | **relationships/*:**                                   |                                |
| 17 | **annotations/*:**                                     |                                |
| 18 | **documentDescribes:DocumentDescribes**                | not in v2.2 spec               |

**********
