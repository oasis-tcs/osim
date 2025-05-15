# Practioner Playbooks

This directory represents practioner use cases of value to sFractal Consulting
in their work creating software, evaluating, and using software.

The use case are organized hierarchically, categorized by how information modeling is used:
1. Extraction of Supply Chain Information from Data
2. Deciding based on Supply Chain Information
3. Combining Supply Chain Information, particularly from disparate sources
4. Converting Supply Chain Information into different data formats 

## 1. Extraction of Information from Data
This category of use cases involves extracting the information content from a data source.
It is foundational to many of the other categories of use cases, which will all start with information
gleaned from this category of use cases. 
For now, it is organized by 'type' (overused and overloaded term, probably need better word than 'type' and explanation)
of information

### 1.1 Extraction of Component Information
This use case derived from
[Supply Chain Use Case 06 - Component Useage](../../SupplyChain/uc06_component_useage.md).
It is also derived from
[Supply Chain Use Case 10 - Component Changes](../../SupplyChain/uc10_component_changes.md)
which, from an information modeling viewpoint, is just the previous use case at two different points in time.

This 1.1 use case is fundamental to virtually all the other use cases.

There are many variants, e.g.:
- deriving from SPDX SBOM data file
- deriving from CycloneDX SBOM data file
- deriving from build artifacts (eg in building initial build SBOM)
- deriving from analytical artifacts (eg in building analytical SBOM from binary analysis, or from derived behavior such as successful exploit by Kali Linux)

But all come down to deriving component information.

For details, see:
[Use Case 1.1 Extraction of Component Information](./uc01.01-extract_component.md)

### 1.2 Extraction of Licensing Information
This use case is derived from 
[Supply Chain Use Case 3 - Licensing](../../SupplyChain/uc03_licensing.md).
Note this is the extraction of the licensing data from:
- an SPDX SBOM data file
- a CycloneDX SBOM data file
- from other data sources (e.g. github repo, company info, other tools).

Using the licensing information is in other use cases, mostly 
[Category 2 - Deciding based on Supply Chain Information](README.md#2-deciding-based-on-supply-chain-information). e.g.:
- a software developer, seeing a copy-left licence, deciding not to use a library 
- a customer deciding not to buy a product because of a 'no military' license 
- a Mergers & Acqusition Risk Assessment Team using licensing data as part of [Supply Use Case 8 - Investment Risk](../../SupplyChain/uc08_investment_risk.md) 
- a Corporate Risk Officer using licensing data as part of [Supply Use Case 11 - GRC](../../SupplyChain/uc11_grc.md)

Note in implementing the information model for this use case that there is an ISO standard on the licenses
used by both SPDX and CycloneDX. 
The standard references 
https://spdx.org/licenses/ so we should use it to derive our licensing information model.
Ie we shouldn't make up our own list.

For more details, see
[Use Case 1.2 Extraction of Licensing Information](./uc01.02-extract_licensing.md)

### 1.3 Extraction of Vulnerability Information
blah overview

note could be deriving from SPDX or CycloneDX data or could be deriving from NVD or other sources of vulnerability data.
It could even be derived from direct security research (ie this is the 'original source' of the 'information').

[Use Case 1.3 Extraction of Vulnerability Information](./uc01.03-extract_vulnerability.md)

### 1.4 Extraction of Exploitation Information
blah overview

[Use Case 1.4 Extraction of Exploitation Information](./uc01.04-extract_exploitation.md)


### 1.5 Extraction of Provenance Information
blah overview

reference

[Use Case 1.5 Extraction of Provenance Information](./uc01.05-extract_provenance.md)


### 1.6 Extraction of Completeness Information
blah overview

Is this it's own category with 'know unknowns' and 'unknown unknowns' or is it a subset of quality.
Does just asking this question make it it's own category of information?
Has this kind of distinction been made in other infomation modeling efforts?

[Use Case 1.6 Extraction of Completeness Information](./uc01.06-extract_completeness.md)


### 1.7 Extraction of Quality Information
blah overview

[Use Case 1.7 Extraction of Quality Information](./uc01.07-extract_quality.md)


### 1.8 Extraction of Risk Information
blah overview\

note this may be derived info from other extracted information (ie output of Category 3 analysis)
or it may be 'extracted' directly from risk data (eg data supplied to/from GRC systems eg about the company producing the software).

[Use Case 1.8 Extraction of Risk Information](./uc01.08-extract_risk.md)


### 1.9 Extraction of Trust Information
blah overview

should 'confidence' (eg in SBOM itself) be a differnt type of information or part of 'trust'?
It is derived info from other factors such as completeness, quality, provenance, type of SBOM, etc.

[Use Case 1.9 Extraction of Trust Information](./uc01.09-extract_trust.md)

### 1.10 Extraction of Metadata
At moment this is catchall and placeholder. 
Hopefully it will disappear as other sections get added ahead of it.
One example not covered in 1-9 is what CISA Working Group called 'type' (bad choice of word even though Duncan was original one who used it that way circa 2017),
eg "source SBOM", "build SBOM", "analyzed SBOM", ...


## 2. Deciding based on Supply Chain Information
In it's simplist form, this category of use cases is just making use
of the extracted information to make a decision.
This may be based on a single piece of information 
(eg is a particular version of a particular component present),
or it may be based on many pieces of one type of information 
(e.g. the entire component list for two different products in two different data formats, 
one in SPDX and one in CDX),
combined with many other categories of information 
(eg licensing, vulnerability, exploitability, completeness, and provenance information)
to make a decision 
(eg picking open-source library "whatever" 
or vendor product "whichever" 
as a software component in building
a new "whatsoever" widget)

### 2.1 Deciding something based on what component/versions present 
The simplest decision use case is a subset of 
[Supply Chain Use Case 6 - usage across an organization](../../SupplyChain/uc06_component_useage.md)
and asks the simple question "Is component blah present?".
This use case has many variants. 
The simplest example would be "Is Log4J present anywhere in my organization?".
sFractal Counsulting would 'assume' (dangerous) the answer to be "no" 
since Log4J is a java library,
and sFractal only programs in Elixir (90%), Erlang, Python, or C.
But better process would be actaully extract the information and make sure that component is not present
anywhere in it's enterprise.
Note that this is a 'yes'/'no' question. 
Only if the answer is yes do you need to go to other use cases
requiring more information like which versions do you have, and which versions are affected by
the Log4Shell vunerability.


## 3. Combining Supply Chain Information, particularly from disparate sources


## 4. Converting Supply Chain Information into different data formats

Should this be "one" use case or "several" classes of use cases or "a gazillion specific use cases"?

Simplest example of a conversion use case is a software developer is making an application which 
uses two components in addition to their software. Component one has an SPDX SBOM. 
Component two has a CycloneDX SBOM.
The software developer wants to make both an SPDX SBOM and an equivilent CycloneDX SBOM
for his application containing his code, component 1, and component 2.
This involves converting Component one SPDX to CycloneDX, and Component 2 CycloneDX to SPDX.
In both cases, this involves first use case 1.1 (deriving the SBOM information from the resprective data formats),
combining the information, and producing both SPDX and CycloneDX data from the combined information.

There are many variants to the above using all combo's of the 9 extraction use cases, all the category 2 and 3 use cases,
and using for many different uses (eg [all 13 of the supply chain use cases](../../SupplyChain/)).
