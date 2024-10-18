## **Q: What is meant by SBOM flavors?**
**A:** 
One of the dictionary definitions 
of the noun flavor is:
"a kind, variety, or sort".
And one of the definitions of the verb flavor is:
"add or enhance to give a distinctive quality to".
In keeping with the 'food ingredients' analogy for SBOMs
where 'flavor' is contextual,
the term "SBOM flavor" is the specific set of SBOM attributes for a particular use between two parties.

For example one organization may require it's suppliers 
to provide the flavor of SBOM that includes licenses.
Another organization may require it's suppliers
to provide just the component list, 
but that it has to be a 'complete' component list
which is a different flavor than only requiring
the first-level components to be provided.
Or an organization may require that certain vulnerability attributes must also be supplied.
Others sets of flavors may involve vulnerability attributes, end-of-life attributes,
attributes associated with when in the software lifecycle the SBOM was generated,
or lineage/pedigree/provenance attributes, etc.

The [Supplychain Information Model](tbd)
is a declarative specification of the possible attributes,
defining the essential content of what information could be exchanged/derived,
but does not specify what must be exchanged.
What must/should be exchanged, and what formats to use, is left to the individual parties in the supply chain
based on the value propositions in their specific use cases.

The [Supplychain Information Model](tbd)
contains [Supplychain Profiles](./profiles.md) which specify collections of 
optional attributes that together form a profile to 
solve the need of particular use case.

Flavors can be considered in the problem space and exist
independent of any implementation, specification, or solution.
Profiles are a codification/specification in the solution space of the [Supplychain Information Model](tbd).