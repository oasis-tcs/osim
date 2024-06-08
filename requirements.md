# Information Modeling Requirements
*An **Information Model (IM)** defines the essential content of messages used in computing,
independently of how those messages are represented (i.e., serialized) for communication or storage.*

The OSIM TC should establish assessment criteria for evaluating candidate
information modeling approaches.

## Essential Content 
The core purpose of an IM is to define information equivalence. This allows the essential content
of data values to be compared for equality regardless of format, and enables hub-and-spoke
translation across formats. 
* An abstract schema is the formal definition of essential content 
* An information value is the internal representation of essential content, defined by behavior,
independent of both data format and programming techniques 
* When reading messages into information values, essential content is validated and insignificant
data is discarded. 

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
a metaschema and losslessly translated across data formats. This enables bundling
an IM with the messages it defines for dynamic version tracking, and processing
an IM using language-specific tools and ecosystems.

## Definitions 
**Abstract schema**: a definition of the essential content to be communicated or stored
to serve a particular purpose 

**Data format (encoding rules)**: an identified mechanism for converting logical values
to and from data values 

**Data value (lexical value, message)**: a sequence of text characters or octets (bytes)
that represents a logical value in a data format 

**Information model**: an abstract schema for a particular application plus a set of
application-independent encoding rules 

**Logical type**: an identified definition of a unit of essential content 

**Logical value (information value)**: the internal representation of an instance of
a logical type that expresses its essential content 

**Metaschema**: a schema that validates schemas for the language in which it is written, including itself 

**Presentation format**: a view of logical values that does not necessarily preserve
all essential content, for display or documentation purposes
