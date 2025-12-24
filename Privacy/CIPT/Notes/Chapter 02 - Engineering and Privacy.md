#CIPT #IAPP 

## Table of Contents
---
Chapter 2 - Engineering and Privacy  
	_Stuart S. Shapiro, CIPP/G, CIPP/US; Travis D. Breaux, CIPT_ 
	2.1 [[#Privacy in an Information Technology Ecosystem]]  
	2.2 [[#Privacy Risk Management]]  
	2.3 [[#Requirements Engineering for Privacy]]  
	2.4 [[#High-Level Design]]  
	2.5 [[#Low-Level Design and Implementation]]  
	2.6 [[#Testing, Validation, and Verification]]  
	2.7 [[#Summary]]


## Privacy in an Information Technology Ecosystem
---
**Privacy in the IT Ecosystem:** Privacy involves multiple roles beyond developers, each influencing how systems are built and used.
- **Key Roles:**
    - **Project Managers:** Ensure resources are sufficient and communication is effective during construction, deployment, and maintenance.
    - **Marketing and Sales:** Gather customer requirements and communicate privacy protections at an appropriate technical level.
    - **Chief Privacy Officer (CPO) / Data Protection Officer (DPO):** Oversee the privacy program, including technical aspects; DPOs under GDPR also handle data security and have independent decision-making authority.
    - **Chief Information Security Officer (CISO):** Responsible for ensuring systems protect personal data and align with the organization’s privacy program.
    - **Lawyers:** Monitor privacy legislation and emerging threats; advise developers on compliance with legal and social norms.
    - **Regulators:** Create, interpret, and enforce privacy laws; examples include the **FTC** (U.S.) and **DPAs** (EU).
    - **Requirements Engineers:** Collect, analyze, and manage software requirements.
    - **Designers:** Translate requirements into software architecture; ensure privacy requirements (e.g., confidentiality, integrity, anonymity) are integrated.
    - **Programmers:** Implement the design into source code using best practices and standard frameworks.
    - **Testers:** Validate software against requirements; identify potential privacy violations or misuse scenarios.
    - **Users:** Operate the software; must understand how personal data is used and have appropriate control over it.
    - **Administrators:** Install and maintain software; ensure operational assumptions of the design are implemented and rely on proper documentation.

![[Pasted image 20251020223152.png]]

**Privacy Engineers:**
- Serve as a **bridge among diverse stakeholders** in software and engineering projects.
- Often start as **software developers**, then become **project managers**, before specializing as **privacy engineers**.
- Key Responsibilities:
    - **Regulatory alignment:** Collect requirements from lawyers to ensure marketing and project requirements comply with laws and social norms.
    - **Privacy requirements:** Propose additional privacy-specific requirements based on project details.
    - **Design collaboration:** Work with designers to implement best practices, assess solutions, and integrate **privacy-enhancing technologies**.
    - **Implementation verification:** Ensure specifications are correctly implemented and achieve intended privacy outcomes.
    - **Post-deployment support:** Assist with **privacy-related bug fixes and enhancements**.
    - **Monitoring and feedback:** Gather user feedback and track privacy developments (blogs, mailing lists, news) to update practices as needed.


**Core Software Development Activities (including privacy considerations):**
- **Requirements Engineering:** Define system constraints, environmental factors, stakeholder goals, and functional/behavioral properties (e.g., privacy, performance, reliability).
- **Design:** Create software designs and architectures, including modular components, assigned functionalities, and connectors such as client-server information flows.
- **Implementation:** Write source code and develop setup/configuration processes for initial system deployment.
- **Testing:** Verify that the system meets requirements through test cases and user testing to observe actual usage.
- **Deployment:** Install and configure the software in the operational environment, including user training for effective operation.
- **Maintenance:** Extend and fix software over its lifetime, either to repair bugs after deployment or provide users with new functionality.
![[Pasted image 20251020224441.png]]


**DevOps Overview:**
- Integrates **system development and operations** to speed up development and deployment.
- Operates as a **continuous loop**: gather feedback → identify changes → implement → deploy. Often visualized as a **figure eight**.
- Heavy automation **increases velocity** but can make embedding **privacy and security** more challenging.
- DevSecOps:
    - Evolves DevOps by integrating **security throughout the life cycle**.
    - Supported by **automated tools** for security control selection, vulnerability scanning, patching, and testing.
    - **Privacy**, beyond security-related confidentiality, is **not yet fully integrated** in DevSecOps.
- Privacy Engineering Methods:
    - Life cycle–based approaches:
        - **OASIS PMRM** (Privacy Management Reference Model and Methodology)
        - **PRIPARE** (Privacy and Security–by-Design Methodology) 
        - **PRAM** (“Privacy Risk Assessment Methodology”)
    - Atomic approaches: Target specific engineering activities, e.g., LINDDUN threat modeling from KU Leuven.
![[Pasted image 20251020225002.png]]


**Preventing Privacy Violations through Software Engineering:**
- Proper **design, implementation, and deployment** can reduce functional privacy violations.
- Developers should **manage steps leading to system failure** to limit privacy risks.
- Key IEEE Definitions (applied to privacy):
    - **Defect:** Flaw in requirements, design, or implementation that may lead to a fault.
    - **Fault:** Incorrect step, process, or data definition in a program.
    - **Error:** Difference between observed/computed values and the correct/theoretical value.
    - **Failure:** Inability of a system or component to perform required functions within specifications.
    - **Harm:** Actual or potential negative impact on an individual’s personal privacy (also called a hazard).
“For example, this occurs when sensitive, personally identifiable information (PII) is disclosed to an unauthorized party. In this scenario, the “defect” is the one or more lines of computer source code that do not correctly check that an access attempt is properly authorized, and the “fault” is the execution of source code that leads to the error. The “error” is the unauthorized access, which is an observed condition that is different from the correct condition, under which “no unauthorized access will occur.” The “failure” is the unauthorized third-party access. Failures are often described outside the scope of source code and in terms of business or other practices."


**Risk** = Potential adverse impact × Likelihood of occurrence.

![[Pasted image 20251020232250.png]]


## Privacy Risk Management
---

**LINDDUN Privacy Threat Modeling:**
- Inspired by **STRIDE** (security threat modeling).
- Acronym represents types of privacy threats:
    - **Linking:** Associating data or actions to learn about individuals or groups.
    - **Identifying:** Discovering an individual’s identity via leaks, deduction, or inference.
    - **Nonrepudiation:** Attributing a claim or action to a specific individual.
    - **Detecting:** Inferring an individual’s involvement through observation.
    - **Data Disclosure:** Excessive collection, storage, processing, or sharing of personal data.
    - **Unawareness & Unintervenability:** Failing to inform or empower individuals regarding data processing.
    - **Noncompliance:** Deviating from **security and data management best practices, standards, and legislation**.



**PANOPTIC™ Privacy Threat Model (MITRE):**
- Inspired by **MITRE ATT&CK®** and similar in approach to LINDDUN.
- Defines **categories of sociotechnical contexts** and **privacy activities** with specific contextual elements and threat actions.
- PANOPTIC Contexts:
    - **Environment:** Domain in which a data action occurs.
    - **Distribution:** Number of entities with which information is shared.
    - **Interaction:** Extent of interaction between the data subject (or proxy) and data custodian, processor, or third parties.
    - **Engagement:** Targeted subpopulations interacting with the entity or proxy.
    - **Data type:** Classes of data involved in the actions.
- PANOPTIC Privacy Activities:
    - **Notice:** Informing the data subject or proxy about data actions.
    - **Consent:** Obtaining assent from the data subject or proxy for defined data actions.
    - **Collection:** Gathering or extracting information.
    - **Insecurity:** Insufficient data protection controls.
    - **Identification:** Associating information with the data subject.
    - **Quality Assurance:** Policies/processes to ensure quality in privacy-related activities.
    - **Manageability:** Allowing the data subject or proxy to access, modify, copy, or delete their data.
    - **Aggregation:** Combining data from one or more datasets.
    - **Processing:** Extracting value or utility from information.
    - **Sharing:** Making information available to another entity.
    - **Use:** Leveraging information to achieve a goal.
    - **Retention and Destruction:** Actions affecting data persistence.
    - **Deviations:** Data actions diverging from established limits.
- PANOPTIC Threat Patterns:
	- Defines generic threat “patterns” as recurring sets of contextual elements and privacy-related threat actions.

**Contextual Integrity**
"privacy that “fits” the situation"
Helen Nissenbaum says privacy is protected when personal information is handled in line with the _informational norms_ of a specific context (e.g., healthcare, education, workplace, social media).

**Contextual privacy norms have three pieces:**
1. **Actors** — who’s involved
    - Information _subject_ (who the data is about)
    - Information _sender
    - Information _recipient_
2. **Attributes** — the type of information (health data, location, financial data, etc.).
3. **Transmission principles** — the rules for how information is shared (consent, confidentiality, need-to-know, purpose limitation, etc.).

**NIST Problematic Data Actions**
Privacy risk comes from the _effects on people_, not just the fact that data is collected

- **Collect** → Surveillance, Interrogation
- **Process** → Aggregation, Identification, Insecurity, Secondary Use, Exclusion
- **Disseminate** → Breach, Disclosure, Exposure, Increased Accessibility, Blacklisting, Appropriation, Distortion
- **Store/Manage** → Retention, Deletion failure

**Calo’s Subjective / Objective Harm Model (S/OD)**
- **Subjective harms**
    - Based on a person’s _feelings or perceptions_ of being watched, tracked, or judged.
    - Accuracy doesn’t matter — if they **feel** observed, the harm exists.
    - Emotional or psychological impact
- **Objective harms**
    - Actual negative consequences caused by the use or misuse of someone’s information.
    - These are real-world impacts: financial loss, discrimination, identity theft, denial of services, etc.
    - Tangible or material consequences

**Taxonomy of Privacy Problems**
Framework to to categorize and explain all the major ways privacy can be harmed.

**1. Information Collection Problems**
Issues arising when data is gathered in intrusive or unexpected ways.
- **Surveillance** – Monitoring, observing, or tracking individuals.
- **Interrogation** – Pressuring, manipulating, or requiring individuals to provide personal information

 **2. Information Processing Problems**
Problems related to how data is handled after it has been collected.
- **Aggregation** – Combining multiple datasets to reveal more than individuals expect.
- **Identification** – Linking information to a specific person, including re-identification.
- **Insecurity** – Failing to adequately protect data.
- **Secondary Use** – Using data for purposes beyond the original intent or user expectation.
- **Exclusion** – Preventing individuals from accessing, correcting, or participating in decisions about their data.

 **3. Information Dissemination Problems**
Issues that arise when data is released, shared, or spread.
- **Breach** – Unauthorized disclosure caused by inadequate security.
- **Disclosure** – Sharing personal information with unauthorized or unexpected parties.
- **Exposure** – Revealing sensitive personal information publicly.
- **Increased Accessibility** – Making personal information easier to find or access.
- **Blackmail** – Threatening to reveal personal information.
- **Appropriation** – Using someone’s identity, data, or likeness for another party’s benefit.
- **Distortion** – Disseminating inaccurate or misleading information.

 **4. Invasion Problems**
Direct intrusions into an individual’s personal life or autonomy.
- **Intrusion** – Invasion into one’s private space, activities, or solitude.
- **Decisional Interference** – Undermining or manipulating an individual’s ability to make autonomous decisions.

**Individual Harms**
NIST groups privacy risk into **Problematic Data Actions** (the _cause_) and **harms to individuals** (the _effect_)

**1. Loss of Autonomy**
People restrict or alter their behavior because they feel observed, profiled, or monitored.  
**Examples**
- Avoiding certain websites due to tracking
- Changing behavior on monitored work devices

**2. Exclusion**
Individuals are denied knowledge about their data or the ability to participate in decisions made with it.  
**Examples**
- Profiles used in decisions but cannot be viewed or corrected
- Hidden algorithms determining eligibility

**3. Loss of Liberty**
The misuse or misinterpretation of data increases the risk of arrest, detention, or legal consequences.  
**Examples**
- Incorrect location data placing someone at a crime scene
- Automated risk systems misclassifying individuals

 **4. Physical Harm**
Data misuse or exposure leads to direct bodily harm.  
**Examples**
- A stalker gains access to location data
- Leaked health data resulting in unsafe treatment

**5. Stigmatization**
Information is linked to an identity in a way that harms reputation, dignity, or social standing.  
**Examples**
- Public exposure of medical conditions
- Revealing unemployment or sensitive personal history

 **6. Power Imbalance**
Data practices allow one party to unfairly influence or control another.  
**Examples**
- Employers using granular monitoring to pressure workers
- Landlords using opaque analytics for screening

**7. Loss of Trust**
Expectations or promises about data handling are broken.  
**Examples**
- Sudden monetization of data previously promised to remain private
- Discovering hidden tracking

**8. Economic Loss**
People experience financial harm, directly or indirectly.  
**Examples**
- Identity theft
- Discriminatory pricing based on inferred data

| NIST Harm        | Related Taxonomy Problems                   |
| ---------------- | ------------------------------------------- |
| Loss of autonomy | Surveillance, tracking, monitoring          |
| Exclusion        | Secondary use, opacity, automation          |
| Loss of liberty  | Identification, inference, aggregation      |
| Physical harm    | Breach, data leakage, authenticity failures |
| Stigmatization   | Inference, distortion, disclosure           |
| Power imbalance  | Surveillance, profiling, coercion           |
| Loss of trust    | Secondary use, deception, breaches          |
| Economic loss    | Breach, misuse, unauthorized disclosure     |

**Privacy Risk Management Framework**
	**1. Characterization**
	Define the system, data, actors, boundaries, and context.
	**2. Threat, Vulnerability, and Event Identification**
	Identify what could go wrong, weaknesses that could allow it, and events that would lead to privacy harm.
	 **3. Risk Assessment**
	Analyze likelihood and impact; prioritize risks.
	 **4. Risk Response Determination**
	Choose how to address the risk (e.g., mitigate, accept, avoid, transfer).
	 **5. Risk Control Implementation**
	Put controls in place (technical, administrative, or policy-based).
	 **6. Monitoring and Reviewing**
	Continuously evaluate controls, system changes, new threats, and adjust as needed.

## Requirements Engineering for Privacy
---
In this section, we will review techniques for acquiring, eliciting, managing, and analyzing privacy requirements.

Requirements engineering is the crucial activity that captures system needs, defining **constraints on the software system** and their relationship to specifications. It provides engineers with an early opportunity to **capture critical privacy properties** before committing to design or deep technological investment. Addressing a defect during the requirements or design phase is significantly less costly than fixing it during implementation (potentially a hundredfold increase in cost)

**Requirement Types**
**Functional Requirements:** Describe a **specific function or action** of the intended system, which a product tester can verify.

    ◦ _Examples:_ "The system shall provide a link to a privacy notice at the bottom of every page".

• **Nonfunctional Requirements:** Describe a **constraint or property** of the system. These must be traced to functional requirements or design elements.

    ◦ _Examples:_ "The system shall not disclose personal information without authorization or consent" and "The system shall clearly communicate any privacy preferences to the data subject".

**Documentation Tools**
**Software Requirements Specification (SRS):** Requirements are collected in an SRS document, often using a **standard format or template**.

**Acquiring and Eliciting Requirements (2.3.2)**
Privacy requirements can be acquired from diverse sources:

| Source Type                               | Details                                                                                                                                                                                                                                                                                                                                  |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Elicitation**                           | Using techniques like **interviews, case studies, and focus groups** with subject-matter experts and stakeholders.                                                                                                                                                                                                                       |
| **Standards & Guidelines**                | Texts such as the **Fair Information Practice Principles (FIPPs)** and the **NIST Special Publication 800-53 control catalog** provide high- and low-level requirements, respectively.                                                                                                                                                   |
| **Laws & Regulations**                    | Require analysis to infer requirements, working with legal counsel to identify relevant mandates. **"Legal standards"** are nonfunctional requirements (e.g., the HIPAA Privacy Rule's "minimum necessary standard"), while **"legal rules"** describe specific mandatory steps (e.g., COPPA Rule steps for obtaining parental consent). |
| **Regulatory Enforcement, News, & Blogs** | These sources provide **insight into what went wrong** when systems failed privacy requirements, allowing engineers to anticipate and avoid pitfalls. For instance, a retrospective analysis on FTC regulatory enforcement actions yielded security requirements that could have prevented system failures.                              |

Regulatory texts often include modal verbs like _may_ (discretionary) and _must_ (mandatory), and terms of art (like "verifiable parental consent") whose definitions are critical to determining legal coverage.

**Managing Privacy Requirements Using Trace Matrices (2.3.3)**
**Trace matrices** are used by requirements engineers to **encode relationships** between requirements and other artifacts.
	• **Trace Link Types:** Links describe the meaning of the relationship (e.g., a link from a requirement to a law means the requirement _implements_ the law; a link to a design element means the design element _implements_ the requirement). These are **many-to-many relations**.
	• **Artifacts Linked:** Trace matrices link requirements to their **origin** (laws, regulations, standards) and to **downstream artifacts** (designs, source code, test cases, and user agreements like privacy policies and terms of use).
	• **Purpose:** The trace matrix ensures **conformance** among software artifacts and identifies the **impact of changes** when requirements or system components are modified.
	• **Rationale:** The rationale for each trace link should be recorded to preserve **interpretations** of standards and laws for future reference, especially for exceptions.

**Legal Interpretation Completeness:**
Engineers can use patterns to broaden the scope of legal interpretations to capture missed requirements:
- **Remove or generalize preconditions:** Apply a requirement to more situations or broader classes of stakeholders than legally required.
- **Preclude preconditions, assume exceptions:** Write requirements that assume a higher standard of care (e.g., using encryption as a safe harbor to avoid breach notification laws).
- **Ground legal terms in the domain:** Extract or articulate implicit conditions and triggers that laws assume but do not state.
- **Refine by Refrainment:** Explicitly prohibit activities that, while not illegal, could create privacy-threatening outcomes (e.g., prohibiting unauthorized access to cryptographic keys).
- **Reveal the regulatory goal:** Identify the broader privacy goal of a law (e.g., protecting an individual from public embarrassment) and apply that goal broadly to novel technologies not covered by the original law.

**Identifying Privacy Threats (2.3.4.2)**
Threat modeling identifies risks based on concrete scenarios, adapting security techniques to anticipate privacy threats.
	• **Antigoals:** These are an **attacker's malicious goals** that obstruct a system's positive privacy goals (e.g., obstructing confidentiality). Analyzing who the attacker agents are and their higher-level goals helps detail the threat.
	• **Misuse and Abuse Cases:** These adapt the existing use case methodology to describe negative intents.
		◦ An **abuse case** describes a complete interaction leading to a harmful outcome.
		◦ The **misuser** in a privacy setting is an actor prone to misusing personal information in a privacy-threatening manner, not necessarily a malicious external attacker

## High-Level Design
---
**Requirements**: Describe what functional and nonfunctional behaviors the system is supposed to exhibit
**Design**: Describe how the system is supposed to implement those behaviors

**Unified Modeling Language**: Provides object-oriented diagrams, sequence diagrams, stat diagrams, and more for describing composition and temporal relationships between elements in the design

**Architecture Types**
- **Client-server Architecture**: describes the relationship between the *client* (Run a program that runs on a local computer), and the *server* (which is the program that runs on a remote computer)
- ==Service-oriented Architecture:== 
- **Peer-to-peer Architecture**: Each peer is both a client and a server. Anonymity is both a privacy benefit and a burden, as malicious peers may transfer personal information
- **Pug-in-based Architecture**: Allows third-party developers (apps) to extend a platform (e.g., Facebook, iOS). This introduces new privacy risks because the platform owner has only a third-party relationship with the app developer.


**Design Patterns and Dark Patterns:** **Design patterns** offer reusable solutions to common privacy challenges (e.g., the *ambient notice pattern* for tracking notification). Conversely, designers must **avoid dark patterns**, which manipulate users into disclosing more personal information than intended

A design pattern is defined by four core components:

**1. Pattern Name:**
    - Allows for **easy reference** and **communication** of the pattern among developers.
 **2. Problem Description:**
    - Details the problem the pattern is designed to solve.
    - Provides enough information to recognize when the pattern applies.
**3. Solution:**
    - Describes the elements of the design (classes/objects), their relationships, roles, and interactions.
    - Is often presented as a template that must be instantiated (modified or extended) for a specific design context.
 **4. Consequences:**
    - Describes the **results** of applying the pattern.
    - Identifies any **trade-offs** (benefits vs. drawbacks) that come from using or not using the pattern.
    - Helps the designer determine if the pattern is a net improvement** to the design.


**Privacy Strategies**
Represent general approaches to privacy design. They can be implemented in different ways and originally conceived as categorizations for design patterns

Design Strategies > Design Tactics > Design Patterns

Eight privacy design strategies and twenty-five supporting tactics (noted parenthetically) have been identified to date:
- minimize (exclude, select, strip, destroy)
- hide (restrict, mix, obfuscate, dissociate)
- separate (distribute, isolate)
- abstract, formerly aggregate (summarize, group)
- inform (supply, notify, explain)
- control (consent, choose, update, retract)
- enforce (create, maintain, uphold)
- demonstrate (audit, log, report)

**Two Types of Privacy Engineering Tools**
Privacy engineering tools are categorized into two types based on their function and integration within the development process:

 **Type 1: General Engineering Process Tools**
These tools support **general engineering processes** into which privacy aspects must be **integrated**.
- **Purpose:** To manage and support the standard system development life cycle (SDLC).
- **Examples:**
    - **Requirements Management** platforms (e.g., incorporating privacy requirements).
    - **Test Management** platforms.
    - **Workflow Management** solutions that span the entire life cycle.
    - **Integrated Development Environments (IDEs)** (single-user or team-based).
- **Driver:** The selection of these tools is primarily **dictated by the larger development environment** and its existing infrastructure.
- **Privacy Engineer's Role:** Ensure privacy is appropriately reflected in these tools (e.g., embedding **privacy requirements** and **privacy design tactics**).

**Type 2: Specific Privacy Mechanism Tools**
These tools are specifically designed to **implement privacy mechanisms or controls** that are then integrated directly into the product or service being built.
- **Purpose:** To provide specific, implementable privacy functionality.
- **Examples:** Tools that implement anonymization, data minimization, secure multi-party computation, etc. (Not explicitly named in the text, but described functionally).
- **Driver:** The selection is driven more by **privacy engineers** and processes specific to privacy engineering.

**Quality Attributes for Privacy**
**Traditional Security Objectives Adapted for Privacy (CIA Triad and PEOs)**
Privacy engineering often leverages and expands upon the traditional security objectives—Confidentiality, Integrity, and Availability (CIA)—and adds modern privacy-specific objectives (PEOs).

| Quality Attribute               | Description and Privacy Relevance                                                                                                                                                                   | Supporting Mechanisms/Concerns                                                                                                                                                                                                        |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Confidentiality**             | The extent to which personal information is **accessible by others**. A failure to protect confidentiality is often a **violation of privacy**.                                                     | Requires **access control** mechanisms (ACLs, RBAC, ABAC), **encryption** (including data in transit and at rest), and **tokenization**.                                                                                              |
| **Integrity**                   | The extent to which the system maintains a **reliable state**, ensuring data is **accurate, complete, and current**. Lack of integrity can lead to the privacy harm of **decisional interference**. | Privacy regulations, such as the GDPR, explicitly require **data quality**. Design must consider how data is **collected and restored** (e.g., cross-checks for manual entry, ensuring corrections propagate to backups).             |
| **Availability**                | The need to ensure information is **accessible when necessary**. This can conflict with confidentiality (e.g., data must be unlocked for use).                                                      | Designers must plan for **emergency access** (e.g., in healthcare), balanced by strong **auditing**. It is also important for enforcing fair information practices, such as providing consumers with **timely access** to their data. |
| **Predictability** (NIST PEO)   | Aims to enable **reliable assumptions** about a system's data and processing by all stakeholders, which is necessary to **avoid function creep**.                                                   | Helps stakeholders, including data subjects and system operators, understand and trust system behavior.                                                                                                                               |
| **Manageability** (NIST PEO)    | The ability to **granularly administer personal information**, including modification, disclosure, and **deletion**. This is necessary to respond to **data subject access requests (DSARs)**.      | Requires strong controls for data handling and system access.                                                                                                                                                                         |
| **Disassociability** (NIST PEO) | The **minimization of connections between data and individuals** to the extent compatible with operational requirements.                                                                            | Can involve architectural data separation, keeping identifiable personal information segregated but linkable to transactional data, or using maximally disassociated data (e.g., aggregated data).                                    |

**Identifiability and Data Localization**
These attributes focus on reducing the risk associated with linking data to a specific person or reducing the potential for secondary data use.

| Quality Attribute      | Description and Privacy Relevance                                                                                           | Supporting Mechanisms/Concerns                                                                                                                                                                                                                                      |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Identifiability**    | The extent to which a person can be uniquely linked to data. **Less identifiability** is preferable to reduce privacy risk. | Strategies include moving toward **pseudonymous** or **anonymous** data. Developers may use techniques to **isolate the collection and use** of non-unique identifiers to limit unwanted inferences (e.g., browser fingerprinting).                                 |
| **Network Centricity** | The extent to which personal information **remains local to the client** rather than being consolidated on a server.        | **Enhances individuals' control** over their information and reduces inappropriate disclosure and secondary use. Requires distributing application logic across client and server. Systems must guard against inappropriate **aggregation** if data is distributed. |
| **Mobility**           | The extent to which a system **moves from one location to another** (e.g., laptops, mobile phones).                         | Introduced risks related to **location tracking** and the possibility of device loss or theft. Requires increased security or **data minimization** on the device.                                                                                                  |

**Emerging Privacy Attributes**
Fairness is an increasingly important system property, especially in the context of Artificial Intelligence (AI) and Machine Learning (ML) systems.

| Quality Attribute | Description and Privacy Relevance                                                                                                                                                                   | Supporting Mechanisms/Concerns                                                                                                                                                                                                          |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Fairness**      | Ensures that systems do not subject individuals, groups, or communities to **unfair decisions and treatment**. Fairness definitions can be mutually exclusive, presenting trade-offs for designers. | Disparate performance in facial recognition or biased outcomes in ML-based decision support tools (e.g., criminal risk assessment) highlight its importance. It presents important design choices regarding **autonomy and intrusion**. |
## Low-Level Design
---
**Development Life Cycle Testing**

| Testing Type            | Focus and Goal                                                                                                                                                                                                | Privacy Relevance                                                                                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Unit Testing**        | Focuses on individual functions and the smallest cohesive components (e.g., object classes, subroutines, web pages, database scripts). Determines if a unit yields an expected output for a predefined input. | Ensures individual functions, like a privacy setting configuration page, correctly update a database entry.                                                                            |
| **Integration Testing** | Focuses on interactions between individual units as members of a subsystem. Tests complex requirements that describe larger system behaviors.                                                                 | Verifies if changing a privacy setting (e.g., restricting email sharing) correctly affects all interacting units (e.g., the unit that generates a marketing list excludes that user).  |
| **System Testing**      | Focuses on the **complete system**, including nonfunctional requirements (like security, performance, and stress).                                                                                            | Involves testing privacy requirements related to gross behavior, such as searching for sensitive data in network traffic or other media that results from operating the entire system. |
| **Acceptance Testing**  | Focuses on requirements **validation** (ensuring customers accept the delivered system and that requirements satisfy user needs).                                                                             | Must involve system users or their representatives to review data subject expectations and ensure system behavior is compatible with those expectations.                               |
| **Regression Testing**  | Focuses on existing systems after changes are made to fix bugs or defects.                                                                                                                                    | Ensures that changes (bug fixes) to one function do not disable a privacy feature that interacts with the change.                                                                      |

**Data Types for Testing**

| Data Type                    | Description and Purpose                                                                                                                                            | Privacy Concerns/Notes                                                                                                                                                                                                                                                                |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Representative/Real Data** | Data obtained from runtime systems or vendors to provide the **best test results** because it reflects real-world use.                                             | If real health data is used to test a function, it must be **protected to the same degree** as in a deployed system. Usage of real data before deployment raises issues regarding how the data was obtained, who performs the test, and how it is accounted for during/after testing. |
| **Synthetic Data**           | Data **generated solely for testing** when real-world data access is restricted. It mimics the desired attributes of real data.                                    | It allows developers to test without needing special **privacy training**. However, it may not adequately represent the **variety and messiness** of real data.                                                                                                                       |
| **Public Data**              | Publicly available datasets, such as U.S. census data.                                                                                                             | Even if statistical disclosure controls are applied, anonymized public data can be **vulnerable to reidentification** if cross-linked with other public datasets.                                                                                                                     |
| **Transformed Data**         | Real data that has undergone **manipulation** (e.g., masking, generalization, suppression) to reduce privacy risk while preserving desired properties for testing. | It differs from synthetic data, which is fabricated from a statistical model. Designing and executing transformations is **labor-intensive**.                                                                                                                                         |
| **Purchased Data**           | Data acquired from another source for immediate testing use.                                                                                                       | The primary risk is that the data provider **may not have been legally allowed to divulge the data** in the first place, creating liability for the organization that receives it.                                                                                                    |
| **Live User Data**           | Data provided by real individuals during **Alpha and Beta testing**.                                                                                               | This carries **inherent privacy risks** because users populate the system with personal information or reveal their behaviors in ways the system collects. Data gathered must be **marked as PII** and treated as it would be in a fully operational system.                          |
**Testing with live Users**
**Alpha Testing (2.6.3.1)**
Alpha testing occurs **early in the implementation process** when the system is **not feature complete**.
	• **Scale and Scope:** It is conducted on a **small scale** (tens to hundreds of users) and is seldom **open to the public**.
	• **Goal:** To identify major bugs and offer **early requirements validation**.
	• **Privacy Risk:** Risks are driven largely by the **incomplete and underdeveloped nature** of the system. Proper data handling and security measures may be absent or not transparent to users.
	• **Mitigation:** Each increment of the system must be **vetted by a privacy and security analyst**. Any data gathered must be **marked as PII** and treated as it would be in a fully operational system.

**Beta Testing (2.6.3.2)**
Beta testing is typically performed on a system that is **feature-complete**.
	• **Scale and Scope:** It occurs on a **large scale** and is often **open to the broader public**.
	• **Goal:** To identify bugs and issues that may interfere with **live deployment**.
	• **Privacy Risk:** Risks relate to the scale and openness of the test; any oversights could have **drastic implications**.
	• **Note:** User accounts and associated personal information created during beta testing **may be retained** for the live version of the system.

**Testing After Deployment (2.6.4)**
Testing continues as an **ongoing process** after the system is deployed. This phase is similar to runtime monitoring.
	• **Log Analysis:** Systems can collect or log large amounts of data, and these logs can become an **unintentional source of personal information**. For example, AOL released user search terms gathered while they interacted with the search service.
	• **Bug Tracking:** Bug reports, especially automated ones, may contain data leading up to the failure, including personal information. Systems should be **transparent** about what PII is contained in an automated report and ensure that if personal information is collected, it is **encrypted or otherwise protected** during transmission and after receipt.
	• **API Testing:** APIs allow services to connect to the system, but developers may **unknowingly expose personal information** through them. If remote procedure calls are logged, the data may become an **unacknowledged repository of PII**.
