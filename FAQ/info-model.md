## **Q: What is meant by 'information model'?**
**A:**
An information model (IM) is a representation of concepts, relationships, constraints, rules,
and operations to specify data semantics for a chosen domain of discourse. It defines the
essential content of discrete data items independently of how that content is represented
for processing, communication or storage.

An information modeling language is a formal syntax that allows users to capture data semantics
and constraints.  The basic unit of a data or information model is called a "resource", "entity",
or "type". For physical resources such as people, organizations or buildings, the data resource
is a highly simplified model of reality, omitting most details to focus on specific aspects for
clarity and usability. For data resources such as documents or messages (including data used to
model physical resources), the data resource *is* reality and the model is the definition of its
content.

In concrete data models, type definitions specify both the content and the form of each resource
instance, and validation is performed against formatted (lexical) values. In abstract information
models, type definitions specify the essential content of each instance, and validation is
performed against information (logical) values regardless of lexical form. Information modeling
ensures that all representations of the same logical value are equivalent, and that data can be
converted from any representation to any other without loss of information. A JADN information model,
unlike ASN.1, is a logical value that can be represented in multiple equivalent data formats.
