# End of Life (EOL) and non-maintained component alerting 

End of Life (EOL) is a supplier-determined designation 
that reflects a formal and explicit organizational decision 
to cease maintenance of a particular product or version. 
This designation must be understood 
in the context of legal and contractual obligations 
that exist between vendors 
(including both product and professional services firms) and customers. 

While EOL data sources are not publicly consolidated 
(i.e. this information exists on corporate web sites 
and security advisories), organizations are responsible 
for creating and monitoring this data on their own. 
Once the EOL information about a component 
and its version is obtained (e.g., by using sources 
such as https://endoflife.date/), 
an organization can use this information in conjunction 
with the SBOM to identify software components 
that are close to EOL status and 
plan for upgrade, migration or self-maintenance.

More colloquially and especially with regard to open source packages 
and software components, 
“EOL” is often used to mean “non-maintained,” 
i.e. a package has been abandoned. 
There is a critical functional difference 
between “non-maintained” and “EOL,” 
which is: a non-maintained open source package can be 
maintained by new community members or 
even by a Consumer if it makes economic sense to do so.

Non-maintenance is important for software security, 
operational risk and integration cost. 
Unlike EOL, thresholds for active maintenance 
can be defined by Consumers and governed in the context of SBOM analysis. 

For a Producer’s development teams, 
SBOM analysis of the maintenance status of components 
provides early feedback to the teams requesting usage 
of these components to either minimize usage or update the package early on. 
For Consumers, SBOM analysis to identify EOL or non-maintenance triggers 
in their software can be used to plan for 
replacement of unsupported software or 
allocation of resources for self-maintenance.

The key attributes of this use case:

* actors
   - Security/Compliance/Risk management, Engineering/Development Teams, Program Managers, Open Source Program Office (OSPO), Procurement Office (for commercial components)
* Business Motivation
   - Plan for deprecation of use and Risk Mitigation
* Functional Objectives
   - Alert when a software component is reaching End Of Life (EOL) early enough for products and services to upgrade or replace the component before the event.
   - Alert when an open source component is not actively maintained, early enough to either update the component or participate in the active maintenance of a component, either via upstream contributions or by forking and/or backporting.
* Processes or Steps to Achieve Objectives
   - Set EOL dates for specific components based on communication from suppliers, release cycles, or general observations.
   - Plan for EOL events within product or service release cycles.process
   - Plan for issues that may arise from upgrades
   - Determine thresholds for active maintenance of open source components
* SBOM Fields Used
   - Supplier, Component Name, Version of the Component,
Dependency Relationship, Timestamp
* Added or Cross-linked Data
   - Product EOL status data
   - Vulnerability Information Sources
* Benefits Achieved
   - Reduce unexpected downtime due to software upgrade
   - Increase resilience of software products



The text of this use case was adapted from [Reference 1](./README.md#references).