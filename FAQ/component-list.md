## **Q: What is meant by the "component list" flavor of  SBOM?**
**A:** 
A component-list SBOM means the SBOM contains component information.
There are different flavors of component-list SBOMs.

A *'first-level component-list SBOM'* contains 
the primary components without further specifying
their subcomponents. This is also a flavor of *'component-list SBOM with known-unknowns'*.

A *'component-list SBOM with known-unknowns'* is a flavor of SBOM
which specifies where there is missing subcomponent information. 

A *'complete component-list SBOM'* contains
all the subcomponents and their subcomponents until
they can not be further broken down; 
and links to all the source code used in producing the software.
