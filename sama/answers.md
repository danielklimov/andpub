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

Non-Overlapping Reusable Architecture (NORA): we focus on identifying duplication, overlap,
and reuse of data assets across domains and systems.

First, we inventory data domains, mapping where key entities (e.g., Customer, Product, Account) are stored and processed.
We then analyze duplicates, overlaps and redundancies, identifying cases where the same data is:

- replicated;
- transformed multiple times in a similar way;
- inconsistently defined across systems.

Next, we assess reuse and interoperability, evaluating whether shared data (e.g., master and reference data)
is exposed via common services, canonical models, or virtualization layers.
We review data ownership and governance, ensuring clear domain boundaries and accountability.

Finally, we document findings using data flow diagrams, and data models, highlighting cases with duplication and
duplicate transformations. This allows us to quantify gaps against NORA principles
and define actions to reduce redundancy, improve reuse, and enable a more modular and interoperable architecture.

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
or stewardship of them to certain business roles. Sometimes new user interfaces (Web UI) must be created for working
with data or defining business rules. Sometimes missing data can be sourced
from spreadsheet-style sources (google sheets, MS Excel files, ods files).
Sometimes ready-made products (e.g. DBT) can be employed instead to deduce missing attributes from existing attributes.
In this case the business role that is responsible for these parts of information is also responsible
for updating respective dbt models.

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


# 4. Enterprise Data Modeling Expertise

## 4.1. Modeling methodology

Our standard data modeling methodology follows a layered approach to ensure clarity, consistency,
and alignment with enterprise architecture principles.

Modeling Standards & Abstraction: We apply conceptual, logical, and physical modeling layers,
using abstraction principles to separate business concepts from system implementation.
Naming conventions and metadata standards follow DAMA-DMBOK guidance to ensure consistency, readability, and maintainability.

Modeling Notations:

- ERD – for relational data structures and entity relationships;
- UML – for system interactions and object modeling;
- BPMN – for describing business processes.

Tools: We leverage tools that are widely known and used in the industry:

- BizzDesign as a tool to map business processes, application and technolory;
- Er/Studio to speed up the creation of ER-Diagrams, schema designs;
- draw.io as the most flexible tool that allows to draw different kinds of diagrams and export
  images of diagrams to common formats.
- Miro - often used for collaborative diagramming.
- Google sheets as collaborative tool for documenting source data schemas, high-level data mappings.
- Github/gitlab pages for auto-generating and storing data documentation with version control leveraging
  the same techniques and git flow as used in software development.

This methodology ensures traceability from business requirements to system implementation,
supports data governance and quality, provides visual artifacts suitable for both technical and business stakeholders,
and allows to employ automation in every step aiming to reduce repetitive labour and speed up the process.

## 4.2. Conceptual Data Model (CDM)

We have strong experience in developing business-centric Conceptual Data Models (CDM) that provide a unified,
technology-agnostic view of enterprise data. Our approach starts with engaging business stakeholders to identify
and define core entities (e.g., customer, account, transaction, product) and their high-level relationships,
ensuring alignment with business processes and regulatory requirements.

We then apply the industry-standard and well-proven concepts and approaches for a high-level
view of the data model for the given industry.

The next step is to integrate the requirements specific to the current platform into the
industry-standard model, extending it where needed while keeping it clear and consistent.

The CDM is developed using ERD notation at a conceptual level, avoiding technical attributes and focusing on semantics,
ownership, and relationships across domains.

The resulting model serves as a common business vocabulary and foundation for 
downstream logical and physical models.

## 4.3 Logical Data Model (LDM)

Our approach to developing a Logical Data Model (LDM) aims at ensuring consistency across all
data domains (e.g., Customer, Product, Finance, Operations).
We start by deriving the LDM from the Conceptual Data Model, refining entities into 
detailed structures with attributes, keys, and relationships.

To ensure normalization and non-redundancy, we apply standard normalization techniques
(3NF/BCNF where appropriate), eliminate duplicate entities, and enforce clear primary and foreign key relationships.
We maintain application independence by modeling based on business semantics,
validated through stakeholder workshops and cross-domain alignment.

Alignment with business requirements is ensured through continuous validation with business owners,
traceability to processes (e.g., via BPMN), and adherence to best practices from DMBOK.

In case of Data Warehouses (DWH) we are trying to maintain a clean separation of entities between
data layers according to chosen architecture and trying to align with well-proven methodologies, like Data Vault
to be able to later create a data integration flow resilient to failures.

This results in a consistent and scalable logical model that serves as the foundation for physical implementation and integration.

## 4.4. Physical Data Model (PDM)

Our approach to developing Physical Data Models (PDM) starts with systematically translating
the Logical Data Model (LDM) into platform-specific implementations, while preserving business meaning and data integrity.
We adapt the model based on the target platform—normalized schemas for relational systems,
denormalized/star schemas for datamarts, creating Data Vault-type entities for Business Layers,
and define flexible structures for data lakes and staging areas.

Performance and scalability are addressed through indexing strategies, partitioning, clustering,
and data distribution techniques, as well as optimization for query patterns and workload types (OLTP vs OLAP).
We also incorporate data lifecycle management, storage optimization, and access patterns to ensure efficient processing at scale.

Throughout the process, we maintain alignment with data governance standards,
ensuring traceability from LDM to PDM, consistency of definitions,
support for data quality, security, and regulatory requirements.

## 4.5. Cross-domain Coverage

Our approach to cross-domain integration modeling focuses on establishing a consistent,
enterprise-wide data foundation across all domains. 
We identify and define shared entities (e.g., customer, product, counterparty) and model
them as canonical data structures, ensuring a single, standardized representation used across systems and integrations.

We implement reference data management to standardize key dimensions (e.g., codes, classifications, hierarchies),
ensuring consistency and interoperability across domains.
Integration models are designed using canonical schemas and data contracts,
reducing point-to-point complexity and enabling scalable, reusable data exchange.

This approach is supported by strong metadata management, governance, ensuring consistency,
traceability, and controlled evolution of shared data assets across the enterprise.

## 4.6. Metadata Management

We ensure that metadata, data lineage, and data definitions are embedded from the very beginning
directly into data model documentation, data models themselves, and managed as integral components
of the architecture rather than as separate artifacts. Each entity and attribute in the models
is supplied with business definitions, ownership, data classification, and quality rules.

We implement end-to-end data lineage by linking conceptual, logical, and physical models to source systems,
transformations, and target outputs, enabling full traceability from origin to consumption.
This is supported by integrated metadata repositories and data catalogs like OpenMetadata,
ensuring synchronization between data models, transformation pipelines, and data layers.

This approach provides consistent definitions, transparency, and auditability, supporting governance,
regulatory compliance, and impact analysis across the data lifecycle.

## 4.7. Data Domain Coverage

We engage business stakeholders through a structured, domain-driven approach.
This includes conducting workshops and interviews with domain owners to identify
key entities, business definitions, data usage patterns and data sources.

Then we define and validate data catalogs (if available) or import metadata from source
databases into a temporary project database. Google sheets then used to create or update
metadata, add missing pieces of information, describe business rules. Business users
are involved in creating and reviewing these descriptions, comments, questions and answers.
The temporary project database is updated keeping the version history.

At the same time we iteratively define and validate Conceptual Data Models,
ensuring alignment with processes and regulatory requirements.
Cross-domain sessions are used to harmonize shared entities and resolve duplicates or inconsistencies.

To ensure completeness, we apply coverage checklists, statuses and traceability to business capabilities and processes.
This ensures that all domains are consistently modeled, validated, and aligned with business needs.

## 4.8. Data Governance Alignment

We ensure that data models are maintained as living artifacts by embedding them within the data lifecycle
and change management process. Data Models, when they are created or updated are version-controlled, regularly reviewed
and documented. Models are updated through formal architecture governance processes
with change requests (using JIRA or similar system),
ensuring continuous alignment with evolving business and regulatory requirements.

Data model metadata with text descriptions and other attributes (foreign keys etc.)
are also stored and updated directly in DBMS or object storage systems (Iceberg tables in Spark).
As a separate measure of keeping data model descriptions up to date, a separate Data Catalog
product (Open Metadata) can be used and regularly updated either automatically or by data analysts.

Data models are tightly integrated with data governance frameworks,
including classification, ownership, lineage, and quality rules. 

This ensures models remain current, auditable, and compliant, while supporting architecture change processes
and enabling consistent, enterprise-wide data governance.

We have developed a "Data Management Capabilities Assessment Framework" (DCAF) - a methodology developed
by Andersen Data Practice, that is being continuously used and approved within the company.
DCAF is used for internal self-assessmant to check the maturity of data delivery, operational readiness
and the quality of the data governance environment.
DCAF criteria are data checking patters used in real projects (ETL logs, schemas, reconciliation methods, audit tests).

Workstreams that are executed in DCAF-diagnostics:

- Baseline DWH and BI - architecture, data streams, data sources, bottlenecks;
- Reconciliations and KPI definitions;
- DevOps / ETL Reliability;
- Data Quality and Data Lineage;
- Controls and auditability - accesses, test environment, evidence pack, data audit and complience;
- Operating Model and Vendor Dependency - ownership, escalation, roles and responsibilities, the model
  of interaction with vendors, the plan to reduce dependencies.



## 4.9 Meta Modelling Methodology

Our meta-modeling methodology is based on a model-driven engineering approach.
We define meta-model, that is, the set of rules and standards that we follow for designing actual models,
that standardizes how all entities, relationships and other architecture artifacts should be structured, related, and governed.

We establish core meta-entities (e.g., entity, attribute, relationship, process, application) and their semantics,
ensuring consistency across conceptual, logical, and physical models.

We implement the meta-model within the same tools we use for data modeling,
using standardized templates, naming conventions, and reusable patterns.

The meta-model integrates not only data, but also technology stack and data integration patterns,
ensuring consistency, traceability and interoperability for different domains and models.

Therefore, this approach enables scalable, consistent, and automated (where possible) modeling,
supporting governance, compliance, and efficient evolution of the enterprise data architecture.

## 4.10 Industrial Standard Adoption

Our modeling approach is based on industrial standards, namely Banking Financial Services Data Model (FSDM),
ensuring that all entities, attributes, and relationships align with globally recognized banking semantics
and regulatory requirements. We leverage the FSDM as a baseline reference model,
mapping its standard entities (e.g., customer, account, transaction, product) to the bank’s actual data domains.
Then we extend FSDM where needed, using the specifics of the current project
while trying to remain as close as possible to the industry standard in order to
make the system more flexible and receptive to possible updates and developments in future.

This includes:

- Reusing standard entities and relationships from FSDM to avoid reinventing models;
- Enforcing consistency and naming conventions;

This approach significantly reduces effort and time, ensures alignment with regulatory and industry standards, and produces
well-auditable models.


# 5. Data Integration and Interoperability - Strategic Design

## 5.1 Integration Patterns

Our integration architecture is based on layered reference models that separate ingestion,
processing, and consumption, aligned with modern data platform patterns (e.g., lakehouse, delta lake).
We design integration using a mix of standardized, reusable patterns to ensure scalability, flexibility, and governance.

We have extensive experience implementing:

Batch ETL/ELT for large-scale, scheduled data movement and transformation, optimized for data warehousing and reporting.

We have extensive experience implementing:

Batch ETL/ELT using tools such as Apache Spark, Airflow, dbt for large-scale transformation,
orchestration, and data warehousing use cases.

Real-time streaming (e.g., Kafka) often combined with Debezium for change data capture (CDC),
enabling event-driven architectures that are able to perform low-latency processing and
delivery of data to staging area of a lakehouse. Futher processing is usually orchestrated
by Airflow.

API connectivity using API gateways and microservices to expose and consume reusable data services
to/from other components of the system or external systems.

Data virtualization, leveraging engines such as Trino, to enable federated querying across different data sources
(databases, lakehouse, APIs) without physical data movement. With this setup Trino acts as a broker
and provides a uniform SQL interface to different types of data sources.

These patterns are selected based on latency requirements, data volume, integration complexity, and business use cases, and are governed through metadata, lineage, and security controls aligned with DAMA-DMBOK. This ensures a robust, scalable, and compliant integration architecture.

## 5.1 Interoperability Strategy and Data Flow Documentation

Interoperability strategy focuses on enabling uniform, governed data exchange patterns across both on-premise and cloud platforms.

We start by defining a semantic layer that standardizes business definitions, shared entities, and data models, ensuring consistent interpretation of data entities across all domains and systems.

To enforce consistency, we seek to use standard data storage formats and exchange protocols,
decoupling producers and consumers and reducing 
integration complexity. Data integration is implemented by one of:

- batch ETL/ELT (Spark, Airflow, dbt);
- real-time streaming (Kafka, Debezium);
- API services;
- data virtualization (Trino).

Data flow are documented end-to-end data flows using:

- ERD for data structures;
- BPMN for process flows.

Semantic layer is defined through the following steps:

- Identifying core business entities and domains;
- Defining standardized business definitions;
- Mapping Source Data to Semantic Layer - providing descriptions of source data attributes in terms of business definitions.
- Formalize the semantic layer - create a Logical Data Model.

Canonical data formats standardize technical structures and data exchange of interoperability. The process
of managing these in data interoperability involves:

- defining all required data sources;
- defining of a canonical schemas (meaning interoperable) tables or messages based on semantic layer;
- creating a mapping of data source entities to the canonical model;
- defining transformations between source structures and canonical structures (various tools can be used for that, e.g. dbt).

Documentation of End-to-End Data Flow. Steps:

- Collect Source-to-Target mapping information;
- Identify all data sources: databases, APIs, streaming platforms, SaaS systems, files;
- Identify data consumers: analytics platforms, dashboards, applications, reports.
- Record tables, fields, message structures, and file formats.
- Document ETL/ELT jobs: which fields are extracted, transformed, and loaded.
- Describe real-time streaming transformations (Kafka topics, CDC events).
- Describe intermediate steps, tables, views.
- Draw Data Flow Diagrams (DFDs) showing systems and data movement.

Documentation can be centralized in:

- git repository with a user web-interface like Github or Gitlab;
- git repository objects can be exported to Confluence pages if Confluence is accepted as a standard document storage in the organization.

Model diagrams can be created using any of the popular packages: Lucidchart, Draw.io, Visio, BizzDesign, Archi, Signavio.
The the central repository for all documentation concerning dataflow, canonical models and semantic layer is in GitLab or GitHub.

## 5.3. Master Data Management (MDM) Advisory

Following the strategic design of Master Data architecture,
we define the MDM roadmap as a phased, business-driven transformation. 

We start by assessing current-state maturity (data quality, duplication, ownership, system landscape),
then identify priority domains (e.g., Customer, Product).

We then design a target MDM operating model, which is:

- governance (data owners/stewards);
- golden record definitions;
- selection of the appropriate MDM style (registry, consolidation, coexistence, centralized).

Based on this, we define implementation phases:

- data standardization;
- cleansing, matching/merging;
- integration with upstream/downstream systems.

The roadmap includes tooling enablement, integration patterns, and data quality controls,
ensuring alignment with governance standards such as DMBOK.

Each phase is designed in such a way that it is linked to measurable outcomes:

- reduction in duplicates;
- improved data quality KPIs;

Thus, we ensure that each part of the MDM system becomes a trusted foundation for interoperability, analytics,
and regulatory compliance.

MDM rarely works as a separate product. Rather, it is a combination of:

- Data quality tools (dbt, OpenMetadata, Airflow);
- Integration tools (dbt, Airflow, Spark, Kafka);
- Data catalog tools (OpenMetadata);
- Documentation (Confluence etc.).

## 5.4. Data Quality and Validation

We design automated data quality and validation controls as embedded components of data integration pipelines,
ensuring data is validated at every stage—from ingestion to consumption.
We define data quality rules from different perspectives:

- schema validation (data conforms to a predefined structure);
- completeness (all required attributes are not empty);
- accuracy (all attributes are correct - i.e. within limits or follow certain rules);
- consistency (all objects adhere to certain complicated business rules and referenced objects exist);
- timeliness (all data integration pipelines produce correct results in accordance with expected schedules and those results can be measured).
- anomaly control (unusual behaviour of objects, unusual trends and patterns).

There are several layers where data quality checks are performed:

- directly within pipelines using tools such as dbt, Apache Spark, custom SQL queries in Airflow DAGs, and Airflow itself
  is used as a tool to trigger alerts if checks fail.
- Data Catalog tools (e.g. Open Metadata) are used as a data quality monitoring and rule engine. It can monitor
  data profiling (e.g., distributions, completeness) as well as track historical trends and failures.
- Custom dashboards in BI tools, alerts triggered by BI tools.

Checks descriptions and expected results are integrated with metadata, lineage, and governance platform,
ensuring traceability, auditability, and continuous improvement.
This approach ensures data is fit for use, reliable, and compliant across all systems.

## 5.5. Security and Compliance (NDMO/NCA)

Our approach embeds security, privacy, and regulatory compliance by design across all data integration and interoperability layers.
We align with national frameworks such as National Data Management Office (NDMO) and National Cybersecurity Authority (NCA),
as well as international standards like General Data Protection Regulation and PDPL,
ensuring consistent enforcement of data protection requirements.

We implement:

- data classification (categorization according to sensitivity and regulatory requirements);
- encryption (at rest and in transit);
- masking;
- tokenization based on sensitivity level, along with role-based and attribute-based access controls (RBAC/ABAC)
  to restrict data access.

Data localization and residency requirements are enforced through architecture design and cloud controls,
ensuring regulated data remains within approved jurisdictions.

Within integration pipelines (batch, streaming, APIs, and virtualization), we embed security controls:

- secure APIs;
- authentication/authorization;
- audit logging and monitoring, ensuring all data exchanges are traceable and compliant.

Governance is reinforced through metadata, lineage, and policy enforcement, aligned with DMBOK,
enabling full auditability and regulatory compliance.

This ensures the data architecture is secure, compliant, and resilient, while still enabling requied 
data access and interoperability across the system.

## 5.6. Use cases support

Our approach ensures that the whole architecture is flexible enough to support multiple use cases:

- analytics;
- AI usage including ML, various data science models;
- reporting, dashboarding;
- be used as web services with secure APIs;
- output data in different formats to be used by other applications or users in various other use cases.

Our goal is to build data foundation that avoids duplication and silo creation. 
We centralize data through shared platforms (lakehouse) and expose it via standardized access layers
such as APIs. In certain cases data virtualization (e.g., Trino) can be used to enable external systems consume
trusted data without actually creating a separate data silo.

We implement canonical data models - a standard unified view of the entity across multiple systems that store
data for this entity, ensuring consistency across domains and use cases.
Integration patterns (batch, streaming, API) are selected based on latency and consumption needs,
while metadata, lineage, and data quality components ensure that all consumers access reliable and well-governed data.

This approach promotes data reuse, interoperability, and scalability, which
enabling analytics, AI, and reporting workloads to operate on a single source of truth without
the need to introduce new silos.
