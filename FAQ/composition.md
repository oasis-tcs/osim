## **Q: What is meant by "COMPOSITION" in defining an SBOM?**
**A:** 
The [OSIM definition of SBOM](./sbom.md) defines that an SBOM 
"can be modeled as a [CLAIM](./claim.md) made by some known [IDENTITY](./identity.md)
regarding the *COMPOSITION* of an [unambiguously identified piece of software](./naming.md)".
[The OSIM Supply Chain Information Model](tbd) defines the many elements of the information model
which make up the claim as to the composition of the software.
Note that in the case of the OSIM Supply Chain Information Model, the claim may include
metadata elements,
[component-list-flavor](./component-list.md) elements (i.e. "classic" composition),
[license-flavor](./license-flavor.md) elements,
[vulnerability-flavor](./vuln-flavor.md) elements,
[exploitability-flavor](./exploitability-flavor.md) elements,
[end-of-life/support/...](./eox-flavor.md) elements,
etc.
In other words, composition claims include claims about the composition, not just a list of the components.
