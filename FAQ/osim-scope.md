## **Q: What is the scope of OSIM's modeling activities?**
**A:**
The OASIS [OSIM page](https://www.oasis-open.org/tc-osim/) says:

> The OSIM TC aims to standardize and promote information models for supply chains,
> addressing the growing threat of cybersecurity breaches.
> The goal of the OSIM TC is to bring clarity to supply chain partners and eliminate
> the inefficiencies which come from the increase of disparate implementations.

An [Information Model](info-model) (IM) defines the essential content of documents and messages
used in computing, independently of how that content is represented for processing, communication or storage.
The abstract modeling process has several benefits:
* Conceptual design can start with just named entities and relationships with no additional detail
* An IM is a directed acyclic graph (DAG) (dependency graph) with uniform node structure, enabling
straightforward use of mature entity relationship (ER) diagram applications:
  * [GraphViz](https://graphviz.org/Gallery/directed/) data structures
  * [PlantUML](https://plantuml.com/ie-diagram)
  * [search ...](https://www.google.com/search?q=d3+entity+relationship+diagram)
* Entities defined in one data format can be imported and reused in other formats



Information models are a means to understand and document the essential information content 
relevant to a system, application, or protocol exchange 
without regard to how that information is represented in actual implementations. 
Having a clear view of the information required provides clarity 
regarding the goals that the eventual implementation must satisfy.
An IM defines logical equivalence of data artifacts such that all representations of the same logical value are
equivalent and data can be converted from any representation to any other without loss of information.

The IM's format independence is to model data at both the conceptual and formal levels. 
This allows IMs to model any kind of data, from simple structures such as value ranges or coordinates, 
to protocol messages, to complete documents, without needing to address programming languages and techniques. 

