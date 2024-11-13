## **Q: What is meant by 'information model'?**
**A:** 
An Information Model (IM) defines the essential content of messages used in computing, 
independently of how those messages are represented (i.e., serialized) for communication or storage. 
Information models are a means to understand and document the essential information content 
relevant to a system, application, or protocol exchange 
without regard to how that information is represented in actual implementations. 
Having a clear view of the information required provides clarity 
regarding the goals that the eventual implementation must satisfy.
An IM defines logical equivalence of data artifacts such that all representations of the same logical value are equivalent and data can be converted from any representation to any other without loss of information.

The main purpose of an IM is to model data at both the conceptual and formal levels. 
This allows IMs to model any kind of data, from simple structures such as value ranges or coordinates, 
to protocol messages, to complete documents, without needing to address programming languages and techniques. 
An IM is a declarative specification that defines desired outcomes (data item validity and equivalence) without describing control flow. 

