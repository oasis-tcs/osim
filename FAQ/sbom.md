## **What is an SBOM?**
**A:** A Software Bill of Materials (SBOM) 
is a formal record containing the details 
and supply chain relationships of various components used in building software.
These components, including libraries and modules, can be open source or proprietary,
free or paid, and the data can be widely available or access-restricted. 

A Software Bill of Materials (SBOM) can be modeled as a CLAIM made by some known IDENTITY
regarding the COMPOSITION of an unambiguously identified piece of software.

With this definition, the following are all SBOMs:

- I know nothing about the software npm:foo@1.3.2
- [someone else] claims that npm:foo@1.3.2 doesn't contain the component bar.
- [someone else] claims that npm:foo@1.3.2 contains the components
  - npm:baz@5.3
  - npm:qux@4.6.2
- [someone else] claims that npm:foo@1.3.2 contains the components
  - npm:baz@5.3  
    from producer X  
    which has license Y  
    and has EOL date Z  
    and depends on
    - npm:qux@4.6.2  
      from producer A  
      which has license B  
      and has EOL date C
    - npm:quux@0.9.1  
      from producer D  
      which has license E  
      and has EOL date F
- [someone else] claims that npm:foo@1.3.2 does not contain any C++

Note that with this formulation there's no objective standard for "correctness" of an SBOM. The five SBOM examples above are all valid claims by different identities. All may be true and correct at once, even with varying levels of information content.

Examples #2 and #3 conform to the "component list" [FLAVOR of SBOM](flavors.md).
