# Oracle EBS Developer Technology Landscape

**Baseline: Oracle E-Business Suite R12.2 · Reviewed: 27 October 2026**

This reference lists what an EBS developer needs to know, in four parts:

- **Application Concepts:** ideas about how EBS works, such as the data model, organization context and security.
- **Technology:** languages and products that exist outside EBS, such as Oracle SQL, PL/SQL and Java.
- **Tools:** software you use to build, test, migrate and diagnose.
- **Application Capability:** what EBS lets you build or use, such as Workflow, Concurrent Programs and Public APIs.

Every row has a **level**, which is the last column of each table. The rows are ordered by level: Core, Specialist, Awareness, then Optional.

<img src="assets/level-legend.svg" width="560" alt="Legend: Core, Specialist, Awareness, Optional">

| Level | Meaning | You can | Example |
| :--- | :--- | :--- | :--- |
| <img src="assets/level-core.svg" width="16" alt="Core"> **Core** | Breadth: the EBS developer foundation, including build, test and release. Every developer needs it. | Do the work without help. When more than one approach is valid, explain the choice you made and the alternative you rejected. | Call a public API with the right application context and handle its message stack. Write a PL/SQL package that sets the WHO columns and handles its exceptions. |
| <img src="assets/level-specialist.svg" width="16" alt="Specialist"> **Specialist** | Depth: expertise in one track (Report, Forms, OAF, Integration, Workflow, Data Migration & Upload, APEX, or ECC), listed in the tracks table below. | Design, build, test and troubleshoot a deliverable of the track. | Build an OAF page, a Publisher template or a workflow process. |
| <img src="assets/level-awareness.svg" width="16" alt="Awareness"> **Awareness** | Some knowledge of another subject area, such as functional, DBA or infrastructure. The work itself belongs to that team. | Read the results, name the terms, and name the team to ask and the evidence to bring. | Functional: explain which setup controls what an HCM Self-Service page shows. DBA: read an `adop` log and name the phase that failed. Infrastructure: read a certificate error and name the host. |
| <img src="assets/level-optional.svg" width="16" alt="Optional"> **Optional** | An additional platform or tool that the team selects. EBS works without it, and an example tool in this document is not a requirement to buy or install it. | Work at the depth of its capability once the project selects it. | Run a SonarQube scan and act on its findings. |

Specialist includes Core: a track is added to the Core foundation, and everything outside your track stays at Core, Awareness or Optional. Self-Service is a web page where an employee or a manager does their own task.

The Specialist tracks:

| # | Track Name | Technology | Tools | Application Capability |
| --: | :--- | :--- | :--- | :--- |
| 1 | **Report** | Oracle SQL<br>Oracle PL/SQL<br>XML<br>XSLT | Report Builder<br>BI Publisher Template Builder for Word | BI Publisher / XML Publisher<br>Oracle Reports<br>Concurrent Programs<br>Value Sets<br>Output Post Processor (OPP)<br>Bursting |
| 2 | **Forms** | Forms<br>Oracle PL/SQL | Forms Builder | Forms Personalization<br>`CUSTOM.pll`<br>Flexfields<br>Message Dictionary<br>Profile Options<br>Attachments |
| 3 | **OAF** | OA Framework (OAF)<br>Java | JDeveloper with OA Extension | OAF Personalization<br>Extensions and Substitutions<br>Metadata Services (MDS)<br>Lookups<br>Profile Options |
| 4 | **Integration** | REST<br>SOAP<br>XML<br>JSON<br>Oracle Advanced Queuing (AQ) | SoapUI / Postman<br>Oracle Integration Repository | Integrated SOA Gateway (ISG)<br>XML Gateway<br>Service Invocation Framework<br>Web ADI |
| 5 | **Workflow** | Oracle PL/SQL | Oracle Workflow Builder | Oracle Workflow<br>Business Event System (BES)<br>Notifications<br>Oracle Alert<br>Approvals Management (AME)<br>Account Generator |
| 6 | **Data Migration & Upload** | SQL*Loader<br>`UTL_FILE`<br>External Tables<br>Oracle Data Pump | FNDLOAD<br>WFLOAD<br>XDOLoader<br>JPXImporter / XMLImporter | Open Interface Tables<br>Public APIs<br>Import Programs<br>Lookups<br>Value Sets |
| 7 | **APEX** | APEX<br>Oracle REST Data Services (ORDS)<br>Oracle SQL<br>Oracle PL/SQL | APEX App Builder<br>SQL Workshop | Public APIs |
| 8 | **ECC** | Oracle SQL | — | Enterprise Command Centers (ECC)<br>ECC Framework<br>Data Sets<br>Dashboards |

In the tables, tool alternatives are separated by `/`, and a level applies to the area, not to every named product.

## Application Concepts

Ideas about how EBS works that you must understand to use it correctly.

| # | Area | Concepts | Level |
| --: | :--- | :--- | :--- |
| C1 | EBS Architecture | Database Tier<br>Application Tier<br>Client Tier<br>Application Top<br>Environment Files | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| C2 | Data Model | APPS Schema<br>Product Schemas<br>Synonyms<br>Table Relationships<br>WHO Columns<br>Trading Community Architecture (TCA) | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| C3 | Organization Context | Ledgers<br>Legal Entities<br>Operating Units<br>Inventory Organizations<br>Multi-Org Access Control (MOAC)<br>Application Context | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| C4 | Security & Access | Responsibilities<br>Menus and Functions<br>Function Security<br>Data Security<br>Grants<br>Role-Based Access Control (RBAC) | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| C5 | Online Patching | Run and Patch Editions<br>Edition-Based Redefinition (EBR)<br>Editioning Views<br>Dual File System | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| C6 | Functional Processes | Financials<br>Supply Chain<br>Human Resources<br>Functional Setup and Configuration | <img src="assets/level-awareness.svg" width="16" alt="Awareness"> Awareness |

## Technology

Languages and products that exist outside EBS and that you use for EBS work.

| # | Area | Technology | Level |
| --: | :--- | :--- | :--- |
| T1 | Database | Oracle SQL<br>Oracle PL/SQL | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| T2 | Data Formats & Transformation | XML<br>JSON<br>XSD<br>XPath<br>XSLT<br>CSV | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| T3 | Scripting & Automation | Unix/Linux Shell Scripting<br>SQL Scripts<br>PL/SQL Scripts | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| T4 | Testing & Code Quality | utPLSQL Framework | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| T5 | User Interface & Extensions | Forms | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Forms) |
| T6 |  | OA Framework (OAF)<br>Java | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (OAF) |
| T7 |  | APEX<br>Oracle REST Data Services (ORDS) | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (APEX) |
| T8 | Integration & Services | REST<br>SOAP<br>Oracle Advanced Queuing (AQ)<br>EDI | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Integration) |
| T9 | Data Loading & Migration | SQL*Loader<br>`UTL_FILE`<br>External Tables<br>Oracle Data Pump | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Data Migration & Upload) |
| T10 | Integration & Services | Oracle Integration<br>SOA Suite / BPEL | <img src="assets/level-optional.svg" width="16" alt="Optional"> Optional |
| T11 | EBS Architecture & Runtime | Oracle HTTP Server (OHS)<br>Oracle WebLogic Server<br>Oracle Forms Services | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| T12 | Database | SQL Monitor<br>DBMS_PROFILER<br>DBMS_HPROF | <img src="assets/level-optional.svg" width="16" alt="Optional"> Optional |

## Tools

Software you use to build, test, migrate and diagnose.

| # | Area | Tools | Level |
| --: | :--- | :--- | :--- |
| L1 | Database | Toad for Oracle<br>PL/SQL Developer<br>Oracle SQL Developer<br>SQL*Plus<br>SQLcl<br>SQL Trace<br>TKPROF<br>DBMS_XPLAN | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| L2 | Testing & Code Quality | utPLSQL<br>JUnit | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| L3 | Source Control & Release | Git<br>CI/CD tooling selected by the team<br>Global Standards Compliance Checker (GSCC)<br>Online Patching Database Standards Checker | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| L4 | EBS Diagnostics | Electronic Technical Reference Manual (eTRM)<br>EBS Diagnostics<br>FND Logging<br>Concurrent Request Logs<br>Forms Trace<br>OAF Diagnostics | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| L5 | User Interface & Extensions | Forms Builder | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Forms) |
| L6 |  | JDeveloper with OA Extension | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (OAF) |
| L7 |  | APEX App Builder<br>SQL Workshop | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (APEX) |
| L8 | Reporting & Document Generation | Oracle Reports Builder<br>BI Publisher Template Builder for Word | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Report) |
| L9 | Workflow & Business Events | Oracle Workflow Builder | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Workflow) |
| L10 | Integration & Services | Oracle Integration Repository<br>SoapUI / Postman | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Integration) |
| L11 | Data Loading & Migration | FNDLOAD<br>WFLOAD<br>XDOLoader<br>JPXImporter / XMLImporter<br>iSetup | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Data Migration & Upload) |
| L12 | DBA Services | `adop`<br>AD Administration (`adadmin`)<br>AutoConfig (`adautocfg.sh`)<br>AD Splice (`adsplice`) | <img src="assets/level-awareness.svg" width="16" alt="Awareness"> Awareness |
| L13 | Infrastructure | `top`<br>`vmstat`<br>`df`<br>`openssl`<br>`keytool`<br>`curl` | <img src="assets/level-awareness.svg" width="16" alt="Awareness"> Awareness |
| L14 | Testing & Code Quality | SonarQube | <img src="assets/level-optional.svg" width="16" alt="Optional"> Optional |
| L15 | Remote Access & File Transfer | PuTTY<br>WinSCP<br>SFTP / SCP | <img src="assets/level-optional.svg" width="16" alt="Optional"> Optional |

## Application Capability

What EBS itself lets you build or use: its modules, frameworks and features.

| # | Area | Capability | Level |
| --: | :--- | :--- | :--- |
| A1 | EBS Application Foundation | Application Object Library (AOL)<br>Concurrent Programs<br>Flexfields<br>Value Sets<br>Lookups<br>Profile Options<br>Message Dictionary<br>Attachments<br>System Administrator<br>User Management (UMX) | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| A2 | Public APIs & Open Interfaces | Public APIs<br>Open Interface Tables<br>Import Programs | <img src="assets/level-core.svg" width="16" alt="Core"> Core |
| A3 | User Interface & Extensions | Forms Personalization<br>`CUSTOM.pll` | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Forms) |
| A4 |  | OAF Personalization<br>Extensions and Substitutions<br>Metadata Services (MDS) | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (OAF) |
| A5 | Reporting & Document Generation | BI Publisher / XML Publisher<br>XML Data Templates<br>RTF/PDF Layouts<br>eText<br>Bursting<br>Output Post Processor (OPP)<br>Oracle Reports | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Report) |
| A6 | Search & Analytics | Enterprise Command Centers (ECC)<br>ECC Framework<br>Data Sets<br>Dashboards | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (ECC) |
| A7 | Workflow & Business Events | Oracle Workflow<br>Business Event System (BES)<br>Notifications<br>Event Subscriptions<br>Account Generator<br>Approvals Management (AME)<br>Oracle Alert | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Workflow) |
| A8 | Integration & Services | Integrated SOA Gateway (ISG)<br>Service Invocation Framework<br>XML Gateway<br>Web ADI<br>Desktop Integration Framework | <img src="assets/level-specialist.svg" width="16" alt="Specialist"> Specialist (Integration) |

## Design and documentation deliverables

Developers read these documents and write the parts that concern their own work. They are deliverables, not technologies, so they have no level.

| Document | Purpose |
| :--- | :--- |
| **MD050** | Functional design of the business requirement |
| **MD070** | Technical design of the extension |
| **MD120** | Build and conversion documentation |
| **Setup document** | Functional and technical setups needed to run the deliverable |
| **CEMLI inventory** | List of customizations, extensions, modifications, localizations and integrations, with technical review |
