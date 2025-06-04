# Broader Supply Chain Value Propositions and Use Cases
To fully appreciate the value of the OSIM use cases 
requires understanding of the broader supply chain uses
in which OSIM plays a role.
For example to see the value of information modeling to 
software bill of materials (SBOM), 
you first have to understand the value of SBOMs.

The use cases in this directory are broader than OSIM 
and show the value of supply chain transparence in general.

The purpose of these use cases is to demonstrate the benefits of 
SBOMs to software producers and consumers. 
It strives to answer the questions: 
“Once we generate or receive an SBOM, what do we do with it?” and 
“What additional insights or intelligence can we gain from the SBOM 
that will benefit my organization?”

The document answers these questions in two major ways: 

1. It defines the SBOM lifecycle by explaining and depicting what happens to an SBOM from the point after its generation by the software producer to its analysis and consumption by the consumer. 
2. It provides thirteen practical use cases that exemplify how the SBOM can be used by a variety of stakeholders to benefit their organizations.

The SBOM lifecycle depicts operations that occur through three major phases of an SBOM’s life: production, sharing, and consumption. 
It further categorizes these operations into three levels of maturity: 
* Basic SBOM Operations cover the SBOM’s generation, verification, publishing, storage, and consumption. 
* Advanced SBOM Operations describe how producers or consumers work with SBOMs to derive further value; for example, they can compare, enrich, or merge SBOMs and analyze SBOMs for a variety of risks. 
* Continuous Vulnerability Management operations are the most mature, such as regular post-release monitoring of SBOMs for newly discovered risks.

Thirteen use cases describe real situations in which producers or consumers 
utilize SBOMs to extract information of value to their organizations. 
These use cases span the SBOM’s Lifecycle and 
cover topics such as how SBOMs can be used to: 
pinpoint differences between software versions; 
identify security, licensing or compliance risks; 
alert organizations when software components are nearing their end of support; 
inform incident responders of impacted software; and support procurement or 
mergers and acquisition (M&A) decisions. For each use, the document provides a brief 
narrative description followed by a table that summarizes the use cases’ actors, 
business motivation, objectives, steps to achieve the objectives, SBOM elements used, 
other supplementary data, and benefits achieved.

The use cases are:
* [Use Case 01 - Pre-deployment CVE vulnerabilities](./uc01_Pre-deployment_CVE_vulnerabilities.md) 
* [Use Case 02 - Post-deployment CVE vulnerabilities](./uc02_post_deployment_cve.md)
* [Use Case 03 - Open source licensing risks](./uc03_licensing.md)
* [Use Case 04 - End of Life (EOL) and non-maintained component alerting](./uc04_eol.md)
* [Use Case 05 - Pre-purchase risk assessment](./uc05_prepurchase_risk.md)
* [Use Case 06 - Component usage across an organization](./uc06_component_useage.md)
* [Use Case 07 - Incident response](./uc07_Incident_response.md)
* [Use Case 08 - M&A and investment risk assessment](./uc08_investment_risk.md)
* [Use Case 09 - Verification of accessory software](./uc09_verify_acc_sw.md)
* [Use Case 10 - Differences in components between builds or versions](./uc10_component_changes.md)
* [Use Case 11 - Conformance with disparate Governance, Regulatory, and Compliance (GRC) specifications](./uc11_grc.md)
* [Use Case 12 - Operational Technology](./uc12_OT.md)
* [Use Case 13 - Field servicing of software-enabled devices](./uc13_field_srv.md)

## References
Much of the text in this document was based on previous work.
This section provides the documents that were referenced above.
### SBOM Operations Working Group
1. SBOM Community, SBOM Operations Working Group. Improving Risk Management Decisions with SBOM Data. (2025, March 2). https://docs.google.com/document/d/1vFVbWEJmNsAbNPRAtHclC89YQlLUt6xYIvKmFGRkcQA/edit?tab=t.0#heading=h.10zm8vq6u9e0 {Editor's Note: Link will be replaced once doc published on CISA website}
