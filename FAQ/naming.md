## **Q: What is meant by "an unambiguously identified piece of software" in defining an SBOM?**
**A:** 
The [OSIM definition of SBOM](./sbom.md) defines that an SBOM 
"can be modeled as a [CLAIM](./claim.md) made by some known [IDENTITY](./identity.md)
regarding the [COMPOSITION](./composition.md) of an *unambiguously identified piece of software*".
[The OSIM Supply Chain Information Model](tbd) defines the item the SBOM is about.
This is the "unambiguously identified piece of software".
For OSIM the terms "product", "primary component", and "subject of the SBOM" will be synonomous.
Note the term is relative to the position in the SBOM ie dependendent on where it is in the supply chain. 
In one SBOM a particular piece of software may be the primary component. 
But if that product is then used as part of a larger product, that same software becomes a subcomponent.

The methods of 'unambiguously identifing' the piece of software are still under study.
