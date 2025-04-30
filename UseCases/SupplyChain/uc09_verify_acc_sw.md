# Use Case: Verification of accessory software

Both Producers and Consumers must assess security and compliance risks 
from the total software product they produce or deploy. 
Many software products include accessory software – such as installers, 
download managers, runtime dependencies, or Software Development 
Kits (SDKs) – that facilitate installation, updates, 
or integration with other systems. 
Because these components are not directly compiled into core executables, 
they are often excluded from the core product SBOM. 
While accessory software may have their own SBOMs, 
these may be overlooked during security and compliance reviews 
of a core product’s SBOM, thereby creating significant risks 
to the organization. 

From a security perspective, installers or SDKs run with elevated privileges 
or fetch external code, making accessory software 
an attractive target for attackers. 
Unverified accessory code introduces an expanded attack surface, 
increasing the risk of exploitation. 
From a compliance standpoint, organizations must verify 
that no accessory software originates from sanctioned 
or prohibited suppliers. 
Even if the primary vendor is not sanctioned, 
the inclusion of prohibited components can result in non-compliance.

To address these concerns, 
SBOM analysis of both core and accessory software is required. 
This comprehensive approach ensures that all components 
with elevated privileges or external integrations 
are programmatically vetted–reducing the risk of false assurance, 
and helping maintain security, licensing, and compliance. 
Ultimately, the use cases for SBOM-driven verification 
of accessory software mirror those of the core product, 
reinforcing a holistic, end-to-end risk management strategy.

The key attributes of this use case:

* actors
** Security Teams, Incident Response Teams, Engineering Management, Regulatory, Governance, Vendor Management, Audit and Compliance
* business motivation
** Maintain organizational security posture and regulatory compliance 
** Ensure vendor compliance with contractual terms and conditions 
** Ensure compliance with terms and conditions of cyber insurance policies
* functional objectives
** Assess security risks of accessory software 
** Assess licensing risks of accessory software 
** Conform to regulations requiring SBOMs of suppliers
** Assess vendor risk based on multiple SBOMs supplied by the same vendor.
* processes or steps to achieve objectives
** Request complete inventory of all accessory software packaged with a software capability
** Confirm that the supplier has delivered SBOMs for each piece of accessory software and all relevant updates and service packs
** Analyze SBOMs to identify remote access utilities in accessory code for subsequent removal or monitoring
* SBOM fields used
** Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Dependency Relationship, Author of
SBOM Data, Timestamp
* added or cross-linked data
** Vulnerability Information Sources, Licenses, and other compliance-relevant databases of designated or precluded software
* benefits achieved
** Supply chain visibility on all packaged components of an installed software product


The text of this use case was adapted from [Reference 1](./README.md#references).
