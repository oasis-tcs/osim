# Use Case: Differences in components between builds or versions

Producers, Distributors and Consumers of software 
need to understand, communicate and respond to 
risks emanating from software vulnerabilities, 
inappropriate licensing, non-compliance, and lack of support. 
However, risks involving software are not static; 
they change over time and need to be reassessed 
with new builds or versions of the software. 
Since an SBOM is a snapshot in time of the software, 
an SBOM produced for each major build or version 
of a software application represents a new snapshot of time. 
These new SBOMs can be analyzed for important changes 
in the risks posed by the software’s components over time.

For example, a component with no known vulnerabilities 
at the time of the software’s initial version 
may be associated with a newly discovered vulnerability 
in a future version. 
Another third-party or open source component 
that was adequately supported upon initial release 
may have diminishing support over time. 
Such changes can be tracked by analyzing SBOMs 
across builds or versions of the software. 
Information from the SBOMs can then be correlated with vulnerability 
or other information to understand when risks were introduced 
or identified as well as when those risks were mitigated or remediated.

Security, Engineering, Compliance, and Governance functions 
within both Producer and Consumer organizations can use these analyses 
to track progress on the introduction and remediation of risks, 
plan for reductions in software supportability, 
and maintain compliance over time. 

The key attributes of this use case:

* actors
   - Engineering (Development, Operations, Security), Engineering Management, Governance, Audit and Compliance
* business motivation
   - Reduce exposure to vulnerabilities, ensure license compliance, compliance to internal policies, and maintain regulatory adherence.
* functional objectives
   - Assess security and license risks over time.
   - Assess compliance and risk mitigation progress over time.
* processes or steps to achieve objectives
   - Identify changes in software components between builds or versions.
   - Identify if changes in software components have fixed prior security, licensing or supportability issues or introduced new ones. 
   - Identify persistent or recurring security, licensing or supportability issues between builds and versions.
   - Track software composition to correlate new risks with existing software. 
   - Track issues over time for metric based performance tracking, and compliance.
* SBOM fields used
   - Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Dependency Relationship, Author of
SBOM Data, Timestamp
* added or cross-linked data
   - EOL 
   - Licenses
   - Vulnerability Information Sources 
   - Inventory systems that include runtime data
* benefits achieved
   - Provides engineering with the ability to track progress on fixing vulnerabilities, addressing license concerns, and assessing supportability.
   - Provides management with the ability to track progress in mitigating risks across builds and versions.
   - Provides engineering management with insight into allocation of resources to address changes in risk.
   - Provides audit and compliance personnel with the ability to pinpoint compliance findings and track progress towards compliance for a given software project/product.
   - Provides Consumers with what vulnerabilities have been fixed between versions.
   - Provides Consumers with information to update risks to their organization from new software versions and update vendor risk scores


The text of this use case was adapted from [Reference 1](./README.md#references).
