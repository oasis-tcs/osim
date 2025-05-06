# Use Case: Component usage across an organization

Organizations maintain software asset inventories to support 
engineering, security, compliance, legal and other functions. 
SBOMs extend these asset inventories down to the level of the components 
that comprise each software application. 
Organizations can use this component-level inventory 
to identify commonly-used software components 
across an organization and 
assess the impact of their prevalence on the organization’s 
security and operational efficiency.

For example, if a commonly-used component is 
now associated with a zero-day or exploited vulnerability, 
its remediation by the security and engineering functions 
requires knowledge of every software application 
within the organization that depends on that vulnerable component. 
In another example, an organization that discovers a 
commonly-used component has unreliable supportability, 
may proactively allocate engineering resources 
for the component’s maintenance.

An SBOM provides the initial component inventory that 
Engineering, Security, Incident Response, 
Compliance and other organizational functions 
can analyze and correlate with information such as vulnerabilities,
licenses, End of Life (EOL) or End of Support (EOS) 
to assess risks from commonly-used components and 
efficiently plan for their mitigation, remediation, and ongoing support.

The key attributes of this use case:

* actors
   - Engineering Management, Security Incident Response, Audit, Compliance, Governance, and Risk Management
* business motivation
   - Asset management, evaluate long-term risk
* functional objectives
   - Assess security and license risks across multiple software systems or an entire organization.
   - Assess compliance and risk mitigation progress for an entire organization.
   - Assess long-term risk incurred by adopting specific components or systems within an organization.
* processes or steps to achieve objectives
   - Identify SBOMs that have been ingested for all software applications in use within the organization
   - Identify the most commonly used software components across an organization.
   - Identify security, licensing or EOL issues in software components that impact multiple software systems.
   - Identify the prevalence of software components with different versions.
   - Identify the prevalence of different components that serve similar purposes.
   - Identify proliferation of vulnerable components across a complex system.
   - Identify critical software components within an organization.
   - Identify components which are EOL
* SBOM fields used
   - Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Dependency Relationship
* added or cross-linked data
   - EOL
   - Licenses
   - Vulnerability Information Sources 
   - Inventory systems that include runtime data
* benefits achieved
   - Provides engineering management with the ability to understand components that affect multiple software systems under their management
   - Provides engineering management with insights to plan where more resources are needed to maintain pervasive software components.
   - Provides audit and compliance personnel with an understanding of the organizational impact of findings about a software component.
   - Provide Incident Response personnel information about the scale and impact of an incident associated with a vulnerable component.

The text of this use case was adapted from [Reference 1](./README.md#references).
