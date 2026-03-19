Answers to SAMA questions:



# 3. ODA - design, documentation, roadmap.

## 1. Current state assessment.

Our methodology for assessing enterprise data architecture state and maturity
combines several frameworks and practical techniques and approaches.

We evaluate the data architecture from these perspectives:
- data governance, data ownership;
- data modeling and metadata;
- data quality and completeness;
- data integration architecture;
- data usage, analytics, decision making;
- technology and tools used.

Frameworks for assessing the current state. We leverage:

- Zachman for artifact classification and mapping across systems, processes and stakeholders.
- DMBOK to evaluate data management practices.

Diagramming and Modeling. We document data architecture using:

- ERDs for data models, wherever possible,
- UML for system interactions, 
- BPMN for business process flows, and ArchiMate for.

## 2. Documents and artifacts

The key artifacts and documents usually comprise:

- Data Flow Diagrams (DFD) to visualize how data moves between systems.
- Entity-Relationship diagrams (ERD) for data models if needed.
- Simplified ERD created as Excel workbooks or Google sheets or Gitlab pages or Confluence pages.
- Data Catalog - description of business semantics of entities and fields.
- Data Landscape Map - high-level view of databases, applications and their relationships.
- Governance and Data Quality Report – ownership, policies, metrics.
- Business processes models.
- Technical architecture document, documenting environments, servers, networks and their interactions.
- Data integration matrix - describing technologies and approaches used for data integration.
- Application inventory - list of systems and applications.
- Maturity matrix - assessments across domains.

## 3. Gap analysis

We perform gap analysis by comparing the current ODA against the desired target architecture,
identifying gaps across:
- data duplication issues;
- data integration bottlenecks;
- data quality;
- governance/compliance.
This includes analyzing data flows, lineage, and data storage silos, redundant pipelines.

Identified gaps are then quantified (impact, risk, business value) and translated into processes aimed to bridge them.
We prioritize using a value vs. effort and risk-based approach and structure delivery into phased roadmaps -
short-, mid-, long-term with clear ownership, milestones, and KPIs.
This ensures alignment with business objectives and enables measurable outcomes.

## 4. Modern Architectures

We have extensive experience designing and implementing modern data architectures, such as:
- Data Mesh, or federated Data warehouses;
- Data Lakes, delta lakes, lakehouses and diffrenet combination of those using different technology stacks;
- Traditional DBMS-based DWHs, using MPP databases, sometimes in combination with delta lakes;
- Employing Data Vault architecture for both Spark-based and DBMS-based storage solutions;
- Integrating kafka-based messaging for CDC and delivery from data sources to the lakehouse;
- Cloud-native Data platforms, that is,architectures designed to leverage advantages of tools and technologies specific to the particular cloud provider, such as AWS, Google Cloud, DataBricks, Oracle Cloud
- Cloud data platforms that are deployed in the cloud but are not tied to a particular cloud provider, using either completely open source stack or partly open source and partly - commercial tools (such as Greenplum DB or DataBricks).
- On premises or hybrid solutions where data storage is deployed in the cloud (AWS s3) and the rest of the components is deployed on premises.

Our approach is technology-agnostic and driven by business needs, data maturity, and organizational structure.

We recommend the appropriate paradigm based on key criteria: 

- organizational model and ownership (e.g., decentralized domains favor Data Mesh);
- integration complexity;
- legacy landscape;
- analytical requirements and data volumes;
- regulatory and compliance constraints;
- data quality requirements;
- ensuring the selected architecture balances autonomy, control, and performance.

This ensures a fit-for-purpose architecture that aligns with business strategy
while enabling scalability, interoperability, and long-term sustainability.


## 5. Big Data Considerations

Our approach to big data management combines scalability, governance,
and standards alignment to ensure both performance and control.
We follow internationally recognized guidance such as the NIST Big Data Reference Architecture,
structuring the architecture into ingestion, storage, processing, and consumption layers with clear roles and responsibilities.

We implement cloud-native, distributed architectures (e.g., lakehouse patterns) to support high-volume,
high-velocity, and high-variety data, while enforcing strong governance policies,
data quality control, lineage tracking, and security by design.
Data is managed through standardized pipelines that can work in parralel and self-recover after most types of failures,
schema management, and automated monitoring, ensuring consistency and traceability at scale.

To balance scalability with control, we apply
- policy-driven governance;
- role-based access;
- data lifecycle management;
- performance and quality KPIs.

This ensures the platform remains elastic and cost-efficient, while meeting regulatory, audit, and business requirements.

## 6. Master Data Design in ODA

Our approach to Master Data design within the ODA is domain-driven. 
We begin by identifying and prioritizing core master data domains or entities (e.g., account, product, client)
based on business criticality, regulatory requirements, and cross-domain usage.

We then define data ownership and stewardship models, establishing clear data ownership through business-aligned roles.
This includes defining golden records, data standards and data quality rules.

Next, we assess the system landscape and integration needs to select the appropriate MDM style:
(registry, consolidation, coexistence, or centralized) and assign roles for data management
to specific systems (applications) that will be considered as source of truth in the target MDM system.

Next we assess parts of master data that do not have clearly-defined systems that own them.
For these parts of data we define rules how they can be sourced or calculated, and assign ownership
or stewardship of them to certain business roles. Sometimes new user interfaces (usually Web UI) must be created for working
with data or defining with business rules. Sometimes ready-made products (e.g. DBT) can be employed instead.

Finally, we integrate master data into the broader data architecture, supported by:
- metadata management;
- data quality checks. 

This ensures master data becomes a trusted, reusable asset across the enterprise.

## 7. Data Governance Alignment

We ensure alignment with SAMA’s Data Governance framework and NDMO policies 
by embedding regulatory requirements into every layer of the ODA design. 
This includes mapping data domains to classification levels, implementing localization and residency controls,
and defining data sharing rules and access policies in line with national guidelines.

Our approach uses policy-driven architecture, where governance rules are reflected in metadata,
data catalog, and data quality controls.

We incorporate auditability and compliance checkpoints, ensuring that master data, integration pipelines,
and analytics data adhere to SAMA and NDMO standards. This ensures that the ODA not only meets business objectives
but also maintains regulatory compliance, security, and trustworthiness.
