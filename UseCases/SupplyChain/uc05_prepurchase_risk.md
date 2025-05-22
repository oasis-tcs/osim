# Use Case: Pre-purchase risk assessment

Prior to purchasing or acquiring software, 
various stakeholders in an organization–purchasing agents, 
contract officers, risk officers, network defenders 
and legal–may need to determine if the target software 
exposes the organization to risks. 
Analysis of the software’s SBOM, and cross-referencing the SBOM data with other common sources, 
can reveal potential security, licensing, compliance 
or maintainability risks 
that the organization will inherit upon deploying the software. 
This analysis provides the organization with an opportunity 
to mitigate these risks prior to purchase, 
thereby reducing their risk exposure. 

In addition, an organization's security, 
risk or vendor compliance teams can use information 
from their analysis of multiple SBOMs supplied by the same vendor 
(from different software applications 
or different versions of the same application) 
to assess the evolving risk level of the vendor’s 
software and whether that risk is increasing 
or decreasing over time 
and whether additional mitigations are required.

The key attributes of this use case:

* actors
   - Procurement, Purchasing, Contracting Officer, Risk/Compliance Officer, Legal, Security Teams, Network Defenders
* business motivation
   - Avoid introduction of new security, compliance or supportability risks to the organization from software that is being considered for purchase or acquisition
* functional objectives
   - Assess security risks of software to be acquired,
   - Assess licensing risks of software to be acquired,
   - Conform to regulations requiring SBOMs of suppliers
   - Assess vendor risk based on multiple SBOMs supplied by the same vendor.
   - Identify mitigations to reduce risk of new software being acquired
* processes or steps to achieve objectives
   - Use components identified in SBOM to discover vulnerabilities in target software 
   - Determine if vulnerabilities pose risks to our organization
   - Determine mitigations to reduce risk
   - Identify licenses associated with components in target software
   - Determine any risks associated with software licenses
   - Determine if there are end of life (EOL) considerations for software components that introduce future risks related to maintainability, reliability or compatibility
   - Determine if any components originate from sanctioned or prohibited suppliers
   - Conduct risk scoring of potential acquired software leveraging the SBOM to assess its level of risk
   - Use information from multiple SBOMs provided by the same vendor as input into a vendor risk score.
* SBOM fields used
   - Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Dependency Relationship, Author of
SBOM Data, Timestamp
* added or cross-linked data
   - EOL
   - Licenses
   - Information about Ownership and Controlling Interest
   - Sanctions lists such as the U.S.Federal Communications Commission Covered Entities list
   - Vulnerability Information Sources 
* benefits achieved
   - Provides purchasing actors with information to assess risks from target software, and engage in risk-mitigating discussions with suppliers.
   - Provides information for purchasing actors to disseminate to legal and risk/compliance officers to inform the risk assessment process.
   - Identify risk mitigation actions

The text of this use case was adapted from [Reference 1](./README.md#references).
