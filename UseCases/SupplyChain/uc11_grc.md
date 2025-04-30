# Use Case: Conformance with disparate Governance, Regulatory, and Compliance (GRC) specifications

Many software delivery contracts now require the delivery of an SBOM, 
each with particular specifications for content and detail. 
Producers must meet these requirements upon delivery of the software 
and Consumers must ensure they have been met prior to software acquisition 
and deployment.

Further, emerging regulations require SBOMs or similar software inventories 
to be delivered to Consumers and/or Regulators where the expectation 
is that the Producer and Consumer are using the SBOM 
for internal risk management. 
For example:
* The U.S.Food and Drug Administration (FDA) implemented changes made by Congress to the Food, Drug, and Cosmetic Act, creating section 524b which requires medical device manufacturers to provide SBOMs for specified FDA regulatory filings. The FDA “Cybersecurity in Medical Devices: Quality System Considerations and Content of Premarket Submissions” details the SBOM requirements.
* Article 13 (24) of the European Cyber Resilience Act (EU-CRA) (EU Regulation 2024/2847), references an SBOM as an obligation of a manufacturer, and Annex I Part II (1) requires an SBOM be created with a minimum detail level comprising top level components. Details on SBOM format or elements will be published by December 2025.
* The U.S.Department of Defense (US DoD) Systems Engineering Standards and Specifications in DI-SESS-82433 as requested under the Department of the Army memo covering “Software Bill of Materials Policy” detail SBOM data elements that go beyond that of both the NTIA minimum fields and available fields from the most recent respective SPDX or CycloneDX specifications.

Producers’ internal technical, legal, and compliance teams collaborate 
on assessing, enriching and tailoring SBOMs to ensure conformance 
with various contractual or regulatory requirements. 
Data that is not covered in the initial, automatically-generated SBOM 
may be brought in from other sources to supplement or enrich the SBOM 
consistent with regulatory specifications.

Consumers, subject to their own GRC constraints, 
use the enriched Producer-supplied SBOM to assess the software’s conformance 
with distinct regulatory and contractual requirements prior to deployment 
of the Producer’s software or its inclusion in a Consumer’s product.

The key attributes of this use case:

* actors
** Risk/Compliance Officer, Auditors (internal and external), Legal, Board
* business motivation
** Meet internal governance processes and practices associated with legal and regulatory requirements within specific jurisdictions, market segments, or vertical sectors
* functional objectives
** Provide an SBOM meeting specific requirements established by the jurisdiction that a Producer operates in, or provides their products or services in.
** Assess the risks documented within the Supplier SBOM as they relate to specific regulations and whether those risks present regulatory challenges to the Consumer
* processes or steps to achieve objectives
** Identify regulations that specify an SBOM requirement or reference a need for a software inventory
** Determine the level of SBOM data required (e.g., only direct dependencies)
** Identify if requisite data fields require supplementation from external data sources (e.g. date the commercial support agreement expires)
** For SBOMs from direct suppliers, identify if requisite information required for compliance is present, and implement policies for missing information or non-conformant components
** Determine disclosure requirements, including timeframes and locations for disclosure (e.g. within x days of a new release an SBOM must be uploaded to a designated repository)
** Based on the requirements of individual contracts and regulations, enrich with supplemental information or tailor the disclosed SBOM to meet the specific requirements of the regulation without excess disclosure
** Identify SBOM sharing constraints and the processes to ensure they are followed
* SBOM fields used
** SBOM should include data elements specified by the regulation, which may not reference NTIA minimum fields. 
** Non-US based regulatory efforts may not reference NTIA elements.
** An SBOM can facilitate compliance with these regulations after required fields have been identified through a comprehensive review of the relevant laws and regulations.
* added or cross-linked data
** Varies by regulation.
** To meet varied GRC requirements, Producers may be required to include all components, proprietary, commercial, contracted, COTS, and not just open source
** Cross linked data available for inclusion in a GRC oriented SBOM may also include ownership and control information, conformance statements for 3rd party components, support statements, incident response process documentation, and any export/import compliance documentation for 3rd party components
* benefits achieved
** Ensure that contractual and regulatory requirements are met by Producer and Consumer of software.


The text of this use case was adapted from [Reference 1](./README.md#references).
