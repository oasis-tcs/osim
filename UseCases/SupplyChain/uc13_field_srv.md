# Use Case: Field servicing of software-enabled devices

Producers of software enabled devices such as medical devices, security 
sensors, and heating controls issue SBOMs upon product release. 
These devices are then deployed in an operational technology (OT) 
environment, where they are subject to field servicing and maintenance over 
the lifespan of the device - often measured in years or decades. 
Over that lifespan,, replacement hardware with associated firmware might be 
installed necessitating  updated firmware, however, the device technician 
might not have full access to perform the necessary maintenance.

As part of routine maintenance and troubleshooting, field service 
representatives compare the source SBOM with data from operational devices, 
such as SBOMs, component hashes, or firmware revision comparisons, for 
maintenance and troubleshooting.  
They can also collect security and error logs to detect intrusions or 
failures before escalation. 
For example, a medical device manufacturer managing patient monitors in 
hospitals has encountered unauthorized software on these devices, risking 
patient safety. 
A reference SBOM provides a baseline for identifying expected software, 
aiding maintenance and repairs.

By comparing the source SBOM and its expected contents, to data gathered 
from the deployed device, field service reps can identify changes in 
software components since the device’s deployment. 
These differences may occur for a variety of reasons, such as: repair or 
replacement of essential components needed for the device’s operation, 
addition of non-essential software to the device at the Consumer site, or 
malicious insertion of components. 
Identifying these differences can help a field service rep to diagnose 
problems in device operation and perform maintenance, and can be valuable 
input to the manufacturer’s product security team.

Field service representatives can also compare the patch levels of 
components in the deployed device to the manufacturer-recommended patch 
levels to determine what needs to be upgraded in the deployed devices.

Since cyber-physical devices have long lifespans, SBOMs offer a means to 
reduce maintenance costs for both Producers and Consumers by ensuring that 
an accurate record of expected software within a device is maintained. 
Where field customization of device software is possible, SBOMs enable field 
service reps to determine whether the device is operating within normal or 
expected risk profiles and determine necessary mitigations. 

The key attributes of this use case:

* actors
** Producer Field Service Representatives, Product Security Team, Consumer IT Team, Consumer Security Team
* business motivation
** Maintain reliability of software-enabled devices
** Maintain supportability, performance and availability of software-enabled devices
** Reduce exposure to vulnerabilities from unnecessary components
* functional objectives
** Compare software inventory on a deployed device to the software inventory provided at the time of the device’s release by the manufacturer
* processes or steps to achieve objectives
** Obtain most recently verified deployed device SBOM
** Generate SBOM for deployed device
** Identify differences between two SBOMs
** Determine potential reasons, both intended and unintended, for the differences
** Compare deployed device’s patch level of components to those recommended by manufacturer
** Inform Producer’s Product Security Team and Consumer’s Security Team and IT team of any unintended additions to the device’s software and any security issues in deployed device
* SBOM fields used
** Supplier, Component Name, Version of the Component,
Other Unique Identifiers, Dependency Relationship, Author of
SBOM Data, Timestamp.
* added or cross-linked data
** Manufacturer’s recommended patch levels for components
** Manufacturer’s installation instructions
** Component hash
* benefits achieved
** Assures Consumer that software-enabled devices are performing reliably and securely
** Assures Consumer that device’s software is at latest patch level
** Provides Producer’s field service representatives with software status needed for maintenance


The text of this use case was adapted from [Reference 1](./README.md#references).
