# Use Case: Incident response

SBOMs (Software Bill of Materials) can significantly 
enhance incident response processes by enabling faster identification, 
containment, and remediation of incidents, ultimately improving the overall 
security posture and resilience of organizations. 
Incident response teams can analyze their portfolio of SBOMs, 
e.g, by importing SBOMs into configuration management databases (CMDB) 
or Security Incident Event Management (SIEM) tools, 
to identify which systems and applications 
within their environment are affected 
by a vulnerable component or identify 
where shared weaknesses across suppliers is indicated 
in supplier cyber security attestations.

For instance, if a security incident is due to a vulnerability 
in a specific component, a repository of SBOMs could 
proactively alert for the new vulnerability and 
can easily be scanned or queried to identify 
all the applications actively using the vulnerable component. 
This process simplifies the identification and remediation effort, 
significantly reducing the mean time to detect (MTTD) for 
analysis and investigation. 
By streamlining these tasks, 
organizations can lower resource costs and 
allocate efforts more effectively, 
prioritizing and addressing affected vulnerable applications 
with greater efficiency. 

Additionally, organizations can use SBOMs to 
implement immediate actionable steps 
as part of the incident response process, 
such as isolating affected systems or 
deploying temporary safeguards to 
mitigate the vulnerability's impact. 

SBOMs can further improve incident response actions 
by providing a standardized framework for collaboration 
among Security Researchers, Software Publishers, 
and Vulnerability Coordinators. 
This common language facilitates the effective communication 
and disclosure of vulnerabilities, 
including sharing CVE status, enabling faster 
and more accurate resolution to security issues.

The key attributes of this use case:

* actors
** Teams performing: Incident Response, Engineering/Development, DevSecOps and IT, Security, Legal and Regulatory
* business motivation
** Respond swiftly and intelligently to cybersecurity incidents,
** Minimize business impacts from the incident,
** Minimize risks through proactive and effective actions,
** Improve the mean time to detect and address vulnerabilities,
** Reduce financial costs associated with incident response, 
** Conserve resources by streamlining response efforts.
* functional objectives
** Empower the security incident response team to rapidly identify vulnerable components and the systems impacted by their usage, 
** Enable software engineers or cyber defenders to take swift and effective actions to remediate the vulnerabilities.
* processes or steps to achieve objectives
** Identify root cause components and versions from SBOMs of the affected system.
** Use SBOMs associated with the affected system to evaluate incident impact.
** Compare the intended SBOM of the affected system to the current state of the system.
* SBOM fields used
** Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Author of SBOM Data, Timestamp
* added or cross-linked data
** Multiple SBOM types (design, build, runtime) 
** Software Attestations 
** Vulnerability Information Sources
** Supplier Security Assertions (e.g., VEX) 
* benefits achieved
** Reduction of mean time to detect (MTTD) is directly linked to resiliency of the organization and positively impacts vendor reputation and revenue.

The text of this use case was adapted from [Reference 1](./README.md#references).
