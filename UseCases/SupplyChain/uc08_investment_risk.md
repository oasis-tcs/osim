# Use Case: M&A and investment risk assessment

Organizations that acquire or invest in businesses 
must perform due diligence to identify risks in 
software developed by the acquisition target 
that might make the acquisition or investment problematic. 
For example, acquirers don’t want to take on Intellectual Property (IP) 
or licensing compliance risks and may view unpatched source code 
as too risky. 
SBOMs provide a method to understand which components 
are used within the target software, their suppliers, 
and each component’s license. Based on the suppliers and disclosed licenses, 
the acquisition team can determine if there are any IP conflicts 
or unresolved obligations and from there determine the cost to resolve 
or cure those issues.

Acquirers and investors also need to assess and manage risks from 
unpatched vulnerabilities in the target software and determine 
if the development team’s dependency list is current. 
SBOMs containing components with many outstanding updates 
are potential signs of an immature update process. 
If the only components being kept up to date are those with 
vulnerabilities published in the NVD, then that implies the 
team prioritizes patching of public vulnerabilities 
above maintaining a current codebase.

Acquisition targets also benefit from sharing an SBOM 
in the early stages of an M&A effort, rather than source code, 
thereby reducing the intellectual property risk of releasing 
source code too soon. 
An acquirer can verify the integrity of the target-supplied SBOM 
by using tools such as binary Software Composition Analysis (SCA) 
to extract an SBOM from applications and then 
compare that extracted SBOM against what was provided by the target. 

Acquirers and investors can use information gathered through 
analysis of SBOMs to identify risks in the target software associated 
with its maintenance,security, licensing, IP, or regulatory compliance 
and use that risk assessment in an evaluation of the target business. 

The key attributes of this use case:

* actors
** Technical due diligence teams, Risk/Compliance Officer, Legal
* business motivation
** Ensure that the company targeted for acquisition or investment is free of liabilities from software security, licensing, IP or regulatory compliance issues.
** Ensure target’s dependence on commercial, Original Equipment Manufacturer (OEM) or other third-party software will be maintained without interruption after acquisition.
** Determine acceptability of the target software’s maintenance and updating practices.
* functional objectives
** Identify dependencies on open source, commercial and other third-party software which are critical to continued development and deployment of the target company’s software products
** Determine potential software product liabilities related to target software’s security, licensing, or commercial/OEM relationships
** Determine conformance to regulations, legislation or industry standards requesting “software inventory” information
** Assess adequacy of software maintenance practices
* processes or steps to achieve objectives
** Critical Dependencies:
*** Analyze target company’s SBOMs for inclusion of all components including open source, proprietary, commercial, and contracted software
*** Analyze SBOMs to identify most commonly used open source, commercial and other third-party software in the target software
*** For each commercial/OEM developer relationship, identify transferability of licenses
** Potential Liabilities:
*** Analyze target company’s SBOMs for CVEs
*** Analyze target software’s security advisories and security release documentation 
*** Determine if there are incompatible IP licenses in target software based on jurisdiction in the target software
*** For each commercial/OEM supplier, analyze the SBOMs of their software for unpatched vulnerabilities and their security advisories
*** For each commercial/OEM supplier, analyze the SBOMs of their software for appropriate licensing
** Regulatory Compliance:
*** Analyze target software’s SBOM to identify potential sanctioned or prohibited suppliers
*** Analyze all commercial/OEM supplier software suppliers for supply chain risk assessments
*** Many regulations pre-date SBOMs becoming mainstream and instead reference maintaining an inventory of software dependencies. SBOMs provide a method for compliance aligned with the spirit of such regulations.
** Software Maintenance:
*** Determine average age of components
*** Determine quantity of unpatched CVEs
*** Determine SBOM generation process
*** Determine frequency of new software versions
* SBOM fields used
** Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Dependency Relationship, Author of
SBOM Data, Timestamp
* added or cross-linked data
** SBOM should include all components, proprietary, commercial, contracted, COTS, and not just OSS
** Cross linked data should include provenance data, component licenses, conformance statements for 3rd party components, and any export/import compliance documentation for 3rd party components
** Where additional SBOM data is present it should be used as part of an existing process
* benefits achieved
** Reduce the cost of integrating a newly acquired company through transparency of development processes.
** Focus tech due-diligence efforts on areas with greatest risk to ongoing or future business operations
** Identify deal breaking or deal modifying risk elements early

The text of this use case was adapted from [Reference 1](./README.md#references).
