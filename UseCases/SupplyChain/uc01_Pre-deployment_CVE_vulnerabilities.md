# Pre-deployment CVE vulnerabilities
Software Producers must ensure or attest that their products are free of known 
and addressable security risks (e.g., 
attest compliance with Secure Software Development Framework (SSDF) 
prior to their release per 
[General Services Administration (GSA) Office of Government-wide Policy. (2024, May 14).  Acquisition Letter MV-2023-02 Supplement 2.](https://www.gsa.gov/system/files/MV-2023-02%20w%20sups%201-2.pdf) ). 
In the pre-market setting, an SBOM serves as a foundational tool for managing cybersecurity risks in software and firmware. 
By using SBOMs in conjunction with vulnerability information, 
software Producers can systematically identify vulnerabilities which are then analyzed against the planned product. 
This analysis drives potential actions such as new design requirements, supplier controls and testing to minimize or eliminate the potential for exploits once the product is released into the market. 
This activity also supports regulatory submissions, eases market entry and provides a level of confidence and trust for buyers. 
The documentation of this analysis can serve as evidence to support security attestations. 
By proactively sharing relevant security information, software producers can enhance transparency, demonstrate accountability, and support informed decision-making across the supply chain.
The key attributes of this use case:
* Actors
   - Producer’s Procurement Office for Components, Regulatory, Engineering, Product Security Teams
* Business Motivation
   - Minimize risks and liabilities to the software Producer from unaddressed vulnerabilities in a software product 
* Functional Objectives
   - Discover vulnerabilities and address risks to the software product prior to the software's release 
* Processes or Steps to Achieve Objectives
   - Cross reference SBOM components with vulnerability information from various sources, including NVD, GitHub Security Advisory, and other trusted repositories
   - Identify any associated CVEs for each component and document for further analysis
   - Review supplier-provided vulnerability assessment reports of third-party software integrated into the product
   - Assess risk and prioritize vulnerabilities based on acceptance criteria and risk scoring factors based on vulnerability information and other factors like component dependencies
   - Remediate vulnerabilities by implementing compensating security controls, patching or removing unused or non-essential components
   - If remediation requires substantial changes, reassess the product design or implementation to ensure vulnerabilities are effectively addressed without introducing new risks
   - Perform vulnerability assessment post-remediation to ensure all identified vulnerabilities are mitigated and no new vulnerabilities have been introduced
   - Record all steps taken to address vulnerabilities, including the rationale for risk acceptance if specific vulnerabilities remain unaddressed
   - If required, provide updates to stakeholders, customers, or regulatory authorities regarding vulnerability management actions and risk mitigation measures taken
* SBOM Fields Used
   - Supplier, Component Name, Version of the Component, Other Unique Identifiers, Dependency Relationship
* Added or Cross-linked Data
   - Vulnerability Information Sources
   - Supplier Security Assertions (e.g., VEX), and threat model insights 
* Benefits Achieved
   - Ensures the product software is as secure as possible, based on the discovered vulnerabilities, prior to deployment and field use.
   - Minimizes liability for the Producer.
   - Supports security attestations and security advisories that may be required by software procurers.


