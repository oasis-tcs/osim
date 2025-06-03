## **Q: What is the value of supply chain information modeling standards?**

A: One might wonder about the value of supply chain information model standards to the various participants in technology supply chains: vendors, governments, enterprises, open source maintainers, service providers, and so on. A productive place to begin is to abstract the discussion from specific actors and instead examine roles which are variously shared, and not, across the ecosystem.

NTIA ([2019](https://www.ntia.gov/files/ntia/publications/ntia_sbom_use_cases_roles_benefits-nov2019.pdf)) has previously used the roles of *Producer, Chooser, and Operator* to analyze and examine the roles and benefits of Software Bills of Materials. We extend that framework slightly, describing the primary roles as **Producer, Evaluator, and Consumer** as follows:

* **Producer**: Creates components (hardware, software, data) for use in the supply chain.
    * *Examples*: Hardware manufacturers, software developers, cloud service providers.
* **Evaluator**: Selects or assesses components, products, or services produced by others.
    * **Observer**: Monitors the supply chain for performance, security, or compliance.
        * *Examples*: Security auditors, monitoring platforms, third-party certification authorities.
    * **Regulator**: Sets rules, policies, or standards that govern how a supply chain should operate safely.
        * *Examples*: Governments, standards bodies (e.g., ISO, NIST), industry consortia.
* **Consumer**: Uses or manages components, products, or services produced by others.
    * **Operator**: Runs, manages, or maintains the supply chain components over their lifecycle.
        * *Examples*: Cloud operators, DevOps teams, IT administrators.
    * **End User**: Directly uses the final product or service.
        * *Examples*: Retail consumers using devices, enterprise developers integrating APIs, developers building with OSS.

In this frame, we can articulate the individualized benefits which information model standardization brings to each role:

* **Producer**: Streamlines integration into downstream workflows, reduces duplication, and broadens market reach.
* **Evaluator**: Provides readily comparable information for decision-making, enhancing trust and reducing risk in procurement.
    * **Observer**: Improves visibility, simplifies monitoring, enhances the ability to detect and respond to issues, and aids reasoning across heterogeneous supply chains and technology landscapes.
    * **Regulator**: Enables clear, enforceable frameworks that improve compliance and reduce ambiguities.
* **Consumer**: Simplifies component selection and ensures compatibility.
    * **Operator**: Enables automation, simplifies maintenance, and ensures consistent processes across heterogeneous environments.
    * **End User**: Receives safer, more reliable products and can make more informed choices. Standardization enhances trust and enables clear, trustworthy labeling regarding security, privacy, and product origin.
