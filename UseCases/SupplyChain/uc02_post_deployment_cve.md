# Use Case: Post-deployment CVE vulnerabilities 

After software is deployed, ongoing vulnerability monitoring becomes essential for  both producers and consumers 
to reduce security risks throughout the software’s lifecycle. 
New vulnerabilities are continuously discovered, 
making the periodic scanning of SBOM-identified software components against CVEs stored in the NVD a crucial 
proactive action that consumers can take prior to exploitation. 

Beyond periodic scanning, the consumers’ security, IT, and compliance teams can actively integrate 
SBOM monitoring into their post-deployment security operations. 
This includes automating alerts for newly discovered vulnerabilities, assessing the potential impact on deployed systems, 
and prioritizing remediation efforts based on real-world risk factors such as exploitability, software dependencies, and critical system exposure. 

The producer’s engineering or product security teams may be assigned to engage in an ongoing process to detect and 
mitigate these risks throughout the software product’s lifecycle. 
By leveraging a properly maintained SBOM, 
producers can trace vulnerabilities to specific components, 
enabling targeted remediation efforts and efficient resource allocation. 
When the SBOM is paired with a Coordinated Vulnerability Disclosure system, 
the producer can notify consumers and provide updates which can be applied to reduce or eliminate the chance of exploit in the software or firmware. 

Both software producers and consumers reduce risks from new vulnerabilities 
in deployed software products and build trust in deployed software through periodic correlation of SBOMs 
against the CVE database and consistent communications. 

By maintaining a continuous feedback loop with producers, 
consumers can quickly receive security advisories, patches, or mitigations, 
ensuring that deployed software remains secure, compliant, and resilient against emerging threats.

The key attributes of this use case:

* actors
   - risk/compliance officer, regulatory, engineering, security teams, product security teams (PSIRT), consumer security teams (CSIRT)
* business motivation
   - maintain secure products in the market, 
   - maintain regulatory compliance, 
   - avoid costly/embarrassing incidents
* functional objectives
   - discover how new CVEs impact software components in deployed software
   - assess security and compliance risks of emerging vulnerabilities on deployed software
* processes or steps to achieve objectives
   - maintain an accurate SBOM
      + producer - ensure your organization generates and maintains an accurate SBOM for all products
      + consumer - if you rely on software providers, require them to deliver accurate SBOMs with each release, update, or patch
   - review vulnerability assessment reports
      + analyze vulnerability reports provided by suppliers of third-party software integrated into the product
      + supplement this with results from third-party scanning tools
   - perform regular vulnerability monitoring
      + regularly monitor vulnerability information sources to identify new vulnerabilities relevant to components in the SBOM 
      + monitor cybersecurity signals from information sharing and analysis organizations (ISAOs), threat intelligence feeds, and security advisories to stay informed about vulnerabilities and threat trends
   - map newly identified CVEs to SBOM components
   - assess discovered vulnerabilities against the acceptance criteria for the product
   - if required, make decisions related to containment, updates/patches, compensating controls, and reporting or recall decisions
* SBOM fields used
   - supplier, component name, version of the component, other unique identifiers, dependency relationship
* added or cross-linked data
   - vulnerability information sources
   - supplier security assertions (e.g., VEX) 
   - inventory systems that include runtime data
* benefits achieved
   - software producer and consumer maintain the security and compliance of deployed software products that may be impacted by new CVEs posted in the NVD.
   - producer and consumer supporting functions can take appropriate actions to contain, mitigate and report new vulnerabilities before exploitation.

The text of this use case was adapted from [Reference 1](./README.md#references).
