## **Q: What is meant by 'information model'?**
**A:** 

An information model (IM) is a representation of concepts, relationships, constraints, rules,
and operations to specify data semantics for a chosen domain of discourse.
An information modeling language is a formal syntax that allows users to capture data semantics
and constraints.

An IM defines the essential content of discrete data items 
independently of how that content is represented for processing, communication or storage.
An IM is a declarative specification that defines the results needed without specifying how they
are achieved:
1. determine if a data value supplies all essential content (validation)
2. convert a value from one data format to any other without affecting essential content (translation)


This abstraction 

Information models are a means to understand and document the essential information content 
relevant to a system, application, or protocol exchange 
without regard to how that information is represented in actual implementations.


Having a clear view of the information required provides clarity 
regarding the goals that the eventual implementation must satisfy.
An IM defines logical equivalence of data artifacts such that all representations of the same logical value
are equivalent and data can be converted from any representation to any other without loss of information.

The main purpose of an IM is to model data at both the conceptual and formal levels. 
This allows IMs to model any kind of data, from simple structures such as value ranges or coordinates, 
to protocol messages, to complete documents, without needing to address programming languages and techniques. 
An IM is a declarative specification that defines desired outcomes (data item validity and equivalence)
without describing control flow. 
