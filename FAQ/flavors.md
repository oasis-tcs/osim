## **Q: What is meant by SBOM flavors?**
**A:** 
One of the dictionary definintions 
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
Yet supplier may require that certain vulnerability attributes must also be supplied.

The [SBOM Information Model](tbd)
is a declarative specification of the possible attributes,
defining the essential content of what information could be exchanged/derived,
but does not specify what must be exchanged.
What must/should be exchanged, and what formats to use, is left to the individual parties in the supply chain
based on their needs.

