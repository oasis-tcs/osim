# Use Case: 

The key attributes of this use case: Integrity and threat management for Operational Technology (OT) and isolated networks

Software deployed for critical infrastructure, industrial use, 
and high security environments, or on isolated networks typically doesn’t 
follow a cloud-native or DevSecOps operations model where software updates 
might be pushed to systems to address security issues. 
While the software might be isolated, isolation doesn’t preclude a need to 
understand dependencies and known security issues. 
Such knowledge becomes quite valuable for both update/upgrade 
process management, but also as part of threat management 
and compliance efforts. 

As an example, suppliers of cyber-physical devices often manufacture 
those devices in batches and sell them over an extended period of time. 
As unsold devices are manufacturing inventory, 
they are not kept current with patches while they sit in inventory. 
Once sold and installed in an isolated environment, without an SBOM, 
it is difficult to determine if the newly installed device 
presents increased risk due to unresolved vulnerabilities or 
through weaknesses in end-of-life or obsolete dependencies. 

An SBOM provides transparency of software dependencies by providing 
a comprehensive list of components, libraries, and potentially runtime tools 
used within and by  an application. 
With appropriate transparency, SBOMs enable teams to standardize and 
streamline version and dependency management across network boundaries to 
minimize attack surface and other risks. 
This approach simplifies compliance and security review and ensures 
traceability, enabling repeatable packaging for software transfers 
between environments. 
For instance, artifacts and dependencies can be collected from sources like 
container image registries/repositories, source repositories, and local 
files, then bundled into an artifact repository for seamless deployment.

The process of using an SBOM to standardize dependencies within isolated 
network environments ensures the integrity of target environments by 
verifying that only declared components are gathered and distributed. 
By computing and including secure hashes for each component, the SBOM 
provides an additional layer of metadata that enables Consumers to verify 
the authenticity and integrity of the software bundle, safeguarding it 
against tampering or unauthorized modifications.

The key attributes of this use case:

* actors
   - Software Developers, Deployment Engineers, Security Engineers, DevSecOps, Maintenance, Compliance, and Legal
* business motivation
   - Enable secure software distribution in air-gapped environments.
   - Facilitate controlled patching and deployment without Internet dependency.
   - Reduce costs, streamline operations, and enhance security.
   - Ensure legal and compliance for bundled software like container images or embedded systems.
   - Simplify audits, mitigate risks, and build stakeholder trust.
   - Maintain compliance with security and regulatory requirements.
   - Faster incident response, and stronger resilience. 
   - Improve trust and traceability for mission-critical applications.
* functional objectives
   - Declare components to be included in a data transfer between systems or networks
   - Track configuration of systems post-transfer between systems and networks
   - Identify security controls that are met prior to transfer as part of government’s or organization’s “Authority to Operate” (ATO) decision.
* processes or steps to achieve objectives
   - Collect - Using component unique identifiers like PURLs, download components from package repositories, git repositories, and container registries.
   - Process - Complete any validation checks on the downloaded components like antivirus checks, CVE lookup, or signature validation.
   - Bundle - Bundle the downloaded and processed components to be moved across a network gap.
   - Expand - Once the transferred bundle is available on the isolated network, expand and move the components to isolated package repositories or container registries.
* SBOM fields used
   - Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Dependency Relationship, Author of
SBOM Data, Timestamp
* added or cross-linked data
   - Licenses
   - Component hashes
   - Sanctioned or prohibited supplier lists 
   - Vulnerability Information Sources
* benefits achieved
   - Users who develop or deploy on networks not connected to the public Internet have to certify that all components meet security controls as part of a government’s or organization’s Authority to Operate. SBOMs provide a clear path to understand what was introduced and allow you to verify everything that was included.


The text of this use case was adapted from [Reference 1](./README.md#references).
