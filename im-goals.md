# Information Modeling Goals
The OASIS Open Supplychain Information Modeling (OSIM) TC aims to standardize and
promote information models about all aspects of supply chains. This involves two kinds
of work:
* Identify value propositions and use cases for applying information modeling to existing
supply chain activities.
* Develop information model artifacts for data used in these activities to promote harmonization and re-use.

The IM work products of the TC should address the following goals:

*An **Information Model (IM)** defines the essential content of data artifacts used in computing,
independently of how they are represented for communication or storage.*

## Essential Content 
The core purpose of an IM is to define logical equivalence of data artifacts. An artifact is
"an immutable blob of data" (**), which includes software as well as typed data such as primitives,
structures, messages, and documents.
An IM allows the essential content of typed data to be validated and compared for equality
regardless of format, and enables hub-and-spoke lossless translation across formats. 
* An abstract schema is the formal definition of essential content 
* An information value is the internal representation of essential content, defined by application
behavior, independent of both data format and programming techniques 
* When reading messages into information values, essential content is validated and insignificant
data is discarded. 

** [Supply chain Levels for Software Artifacts](https://slsa.dev/spec/v1.0/terminology)

## Format Independent 
An information model includes encoding rules that define how information values are parsed from
and serialized to messages in a specific data format. Data formats include:
* Text-based data languages, e.g., XML, JSON 
* Binary data languages, e.g., CBOR, Protobuf 
* Schemaless data structures, e.g., IP packets 

Encoding rules may define more than one data format for a specific data language,
e.g., fields represented as elements or attributes in XML, or object or array members in JSON. 

## Metaschema 
An abstract schema is itself an information value, enabling it to be validated against
a metaschema, losslessly translated across data formats, as well as defined without
serialization using domain-specific language grammars and tools.
Serializing a schema allows it to be bundled with the messages it defines for dynamic
version tracking, and processed using language-specific tools and ecosystems.

## IM Definitions
Parenthesized terms are usable interchangeably in the context of information modeling.

**Abstract schema**: a definition of the essential content to be communicated or stored
to serve a particular purpose

**Data format (encoding rules, serialization rules)**: an identified mechanism for converting logical values
to and from data values

**Data value (artifact, document, lexical value, message)**: a sequence of text characters or octets (bytes)
that represents a logical value in a data format

**Information definition language**: a domain-specific representation of abstract schema logical values 

**Information model**: an abstract schema for a particular application plus a set of
application-independent encoding rules

**Logical type**: an identified definition of a unit of essential content 

**Logical value (information value)**: the internal representation of an instance of
a logical type that expresses its essential content 

**Metaschema**: a schema that validates schemas for the language in which it is written, including itself 

**Presentation format**: a view of logical values that does not necessarily preserve
all essential content, for display or documentation purposes
