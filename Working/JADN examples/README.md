# JADN IM Examples

JSON Abstract Data Notation ([JADN](https://github.com/oasis-tcs/openc2-jadn/tree/working))
is an information modeling language initially developed by the OASIS Open Command and Control
(OpenC2) TC to support development and
[documentation](https://docs.oasis-open.org/openc2/oc2ls/v1.0/cs02/oc2ls-v1.0-cs02.html#33-content)
of the OpenC2 language. The same IM is used to both validate messages and generate
property tables used in the standard, ensuring consistency between the two.

JADN is not specific to OpenC2, and this folder contains examples of other document /
protocol specifications in JADN format. The examples are not necessarily complete,
current, or correct, and have not been endorsed by the spec developers. The intent is
a proof of concept to illustrate how JADN can specify common information building
blocks applicable across a range of applications.

Each example contains JADN source in JSON format, and artifacts generated from it:
* xxx.jadn - JADN source, JSON format
* xxx.jidl - JADN Information Definition Language (source in text format)
* xxx.md - property tables in Markdown format
* xxx.dot - GraphViz ERD source
* xxx.png - GraphViz rendered ERD
* xxx.json - JSON Schema
* xxx.xsd - XML Schema Definition (future)
* xxx.proto - Protocol Buffers schema (future)
* xxx.cddl - RFC 8610 Concise Data Definition Language (future)

JADN's normative format is JSON data, but JIDL is generally the preferred source format
for readability. They are equivalent; loading either format yields the identical IM.

Propose additional candidates for information modeling here ...

1. [OpenC2](OpenC2) objects and datatypes
2. [CycloneDX](CycloneDX) SBOM documents
3. [SPDX](SPDX) SBOM documents
4. [OSCAL](OSCAL-1.1.2) NIST Open Security Controls Assessment Language
5. [NIEM](NIEM) National Information Exchange Model OASIS Open Project
6. [CIQ](CIQ) OASIS Customer Information Quality (2002)
7. ...