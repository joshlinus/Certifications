#CIPT #IAPP 

## Table of Contents
---
Chapter 9 - Cybersecurity and Privacy
	*Hanan Hibshi*
	[[#9.1 The Breadth of Computer Security Work]]

## 9.1 The Breadth of Computer Security Work
---
![[Pasted image 20251216193737.png]]

###### 9.1.1 Securely Provision
This category covers the tasks specifically focused on developing software to be secure.

• **Requirements Planning:** Software development begins by defining both security and privacy requirements, drawing on stakeholder input and legal considerations. For instance, a system may need to support controls mandated by the GDPR, such as the ability to efficiently identify all personal data belonging to a single individual.

• **Architecture Design:** Once requirements are defined, the system architecture is designed. This involves determining the necessary technologies and how data will be organized to meet both functional and security/privacy needs. For example, data storage for a large system might be partitioned geographically to comply with national privacy regulations.

• **Development and Testing:** In this phase, the requirements and architecture are turned into a functional system. System components are then subjected to tests and evaluation to ensure they meet all requirements.

• **Systems Development and Risk Management:** "Systems development" ensures all phases, from gathering requirements to testing, are effectively carried out. "Risk management" involves identifying and managing all associated risks, including those related to software quality, regulatory compliance, security, and privacy.

###### 9.1.2 Operate and Maintain
The operation and maintenance of a system are essential for meeting its security and privacy goals. This work category involves several critical tasks:

• **Systems Administration:** Ensures the system is properly installed, configured, and managed over time to meet security and privacy objectives.

• **Network Services:** Focuses on the similar administrative tasks necessary for the computer networks supporting the system.

• **Customer Service and Technical Support:** This area is often targeted by attackers attempting to steal proprietary or personal data. For instance, SIM-card-swapping attacks exploit technical support processes to gain access to a victim's private information.

• **Data Administration:** Involves managing the databases that house potentially sensitive data generated or accumulated by the systems.

• **Systems Analysis:** Examines how different systems within an organization interoperate.

• **Knowledge Management:** Ensures the organization tracks and manages information regarding its systems and how to operate them.

###### 9.1.3 Protect and Defend
This work category focuses on actively safeguarding the system against threats and includes several critical tasks:

• **Vulnerability Assessment and Management:** This involves evaluating the system to identify potential flaws that an attacker could exploit and developing a plan to address those threats.

• **Intrusion Detection and Prevention Systems (IDS/IPS):** Security efforts include infrastructure such as firewalls, which prevent malicious network traffic, and monitoring systems to detect attacks. IDS and IPS systems detect and, in the case of IPS, block malicious activity, often leveraging AI and machine learning to analyze traffic patterns (e.g., detecting anomalies in banking transactions or network packets).

• **Cyber Defense Analysis and Infrastructure Support:** This covers using defensive components (like IDS/IPS) to prevent or detect attacks and maintaining the underlying infrastructure required for these defenses.

• **Incident Response:** When an attack succeeds, incident response is the process of documenting the attack's details, determining its impact, and taking appropriate remedial actions, including notifying affected users and developing plans to fix the vulnerabilities exploited. Failure to patch known vulnerabilities promptly, as seen in the Equifax breach, can significantly contribute to the success of an attack or its fallout.

This work often involves trade-offs between privacy and security, as collecting more detailed usage data can improve security by detecting attacks, but also increases privacy risks for users whose data is collected.

###### 9.1.4 Investigate
This work category is activated when a cybersecurity event or crime occurs and focuses on gathering information to understand the nature of the breach. The investigation primarily serves three purposes:
1. **Discovering Compromised Data:** Determining exactly what specific data may have been compromised so that consumers can be notified.
2. **Identifying the Attack Method:** Determining the specific way the system was compromised to help avoid similar attacks in the future.
3. **Identifying the Perpetrator:** Determining who perpetrated the attack so they can be prosecuted.

The success of this investigation is heavily dependent on the amount of operational data collected about the system.

## 9.2 Attacks and What Makes Them Possible
---
Attacks that compromise computer systems typically involve exploiting flaws like software vulnerabilities, using malware, or misusing stolen login credentials.

**Software Vulnerabilities**
These are bugs that an attacker can exploit to carry out an attack.
	• **Buffer Overflow** This is a well-known vulnerability where data larger than the allocated memory area overflows and overwrites adjacent memory.
	• **Input-Validation Flaws** These flaws allow attackers to inject malicious content. Examples include **cross-site scripting (XSS)**, where code is injected into a user’s web browser, and **SQL injection**, which alters database queries to corrupt or access sensitive data.

**Malware**
Malicious programs (**malware**) are often installed covertly, sometimes through phishing emails or exploiting vulnerabilities.
	• **Keyloggers** record a user’s keystrokes to steal sensitive information like credentials.
	• **Rootkits** are malware that changes the computer system's behavior to avoid detection.
	• A widespread network of infected computers, known as a **botnet**, is often used to launch **Distributed Denial-of-Service (DDoS)** attacks that overwhelm and crash victim servers.

**Stolen Credentials**
Most system breaches involve stolen credentials. These are typically obtained through **social engineering** attacks:
	• **Phishing** tricks victims into providing login credentials on fake websites.
	• **Spear phishing** involves messages customized with personal information to target a specific victim.
	• **Whaling** is a type of spear phishing that targets high-value individuals, such as corporate executives.

**Other Causes**
Breaches can also result from systemic errors:
	• **Misconfiguration** For instance, improperly set firewalls or mistakenly leaving internal files publicly accessible can lead to significant data exposure.
	• **Insider Threats** These are security risks posed by users who possess elevated access privileges or knowledge that can be leveraged to steal sensitive data.


## 9.3 Security Properties and Types of Adversaries
---
Computer system security is often defined by three core properties, collectively known as the **CIA triad**:

1. **Confidentiality (Secrecy):** This property ensures sensitive data is protected from unauthorized users or attackers. A breach of confidentiality, where sensitive personal information is stolen, is also considered a violation of privacy.

2. **Integrity:** This involves preventing unauthorized modification of data, ensuring it is correct and complete. Privacy regulations like the GDPR require data quality, which is linked to maintaining integrity.

3. **Availability:** This ensures systems are accessible to legitimate users when needed, even under attack. Availability is critical for privacy because enforcing certain rights (like providing timely access to data) requires a functional system.

These three properties are often in tension; improving one may make achieving another more difficult (e.g., keeping many copies of data to ensure integrity may increase the risk to confidentiality).

**The Adversary and Security Threats**
To determine how well security mechanisms achieve these properties, the concept of the **adversary** must be considered. The security mechanisms must anticipate the adversary's computational capabilities and knowledge.

The general threats to security properties can be summarized using the acronym **STRIDE**:
	• **Spoofing** an entity is mitigated by **authentication**.
	• **Tampering** with data is mitigated by **integrity** checks.
	• **Repudiation** (denying responsibility for an action) is mitigated by **nonrepudiation** controls like digital signatures and audit logs.
	• **Information disclosure** is mitigated by **confidentiality**.
	• **Denial of service (DoS)** impacts **availability**.
	• **Elevation of privilege** is mitigated by proper **authorization**.


## 9.4 Access Control
---
Access control is the process of regulating which users have access to what data and the manner in which they can use it. It is crucial for protecting the confidentiality and integrity of data.

Access control consists of two major components:

1. Authentication

Authentication is the process of verifying a user's identity when they attempt to access protected resources ("logging in").

• **Confidence Levels** Different authentication methods (like usernames/passwords versus temporary mobile codes) provide varying levels of confidence in the user’s identity.

• **Privacy Risks** Authentication systems often gather and store private information (like phone numbers or answers to "security questions") for backup authentication purposes. If the authentication system is compromised, this accumulation of personal information increases the potential for harm.

2. Authorization

Authorization is the process of determining whether an authenticated request to access a resource should be granted. This involves coordinating a technical **mechanism** (the means of allowing or denying access) and a **policy** (the specific rules).

• **Granularity:** Access mechanisms vary in how fine-grained they are, ranging from protecting entire files to controlling access to specific rows within a database table,. Authorization also regulates the **type** of access allowed, such as read, write, or execute.

• **Complexity:** When access control systems are overly complex to configure, administrators may make errors that unnecessarily expose data, despite the system offering theoretically tighter controls,.

**Access Control Models**
Different approaches guide how access control policy is structured:

• **User-Based Access Control (UBAC):** Permissions are defined for individual users, providing fine-grained granularity.

• **Role-Based Access Control (RBAC):** Permissions are tied to defined roles (e.g., "administrator"). Users are assigned roles, which simplifies management, but this can lead to users having broader access than strictly needed,.

• **Attribute-Based Access Control (ABAC):** Policy is specified using various attributes related to the user, the object being accessed, or the environment (e.g., "Charlie can access sensitive files only from the corporate network").

• **Mandatory Access Control (MAC):** Policy is strictly set by administrators and cannot be changed by general users, even for their own data.

• **Discretionary Access Control (DAC):** Allows users to change access control policies for data they own.

**Federated Identity (Single Sign-On)**
Federated identity management (or SSO) outsources user authentication to an external Identity Provider (IdP). While convenient for users who only need one login, the IdP gains a detailed profile of all the services the user visits, including when, where, and in what order, which is a major privacy concern.


## 9.5 Principles for Building and Operating Systems to Be More Secure
---
To reduce the chance of an attack succeeding and minimize the harm a successful attack can cause, computer systems should follow a set of fundamental security principles. These principles are widely accepted and have remained relatively unchanged since the mid-1970s.

**Core Security Principles**
• **Economy of Mechanism:** Simpler security mechanisms are preferred because they are less likely to contain flaws than complex ones.

• **Open Design:** Security mechanisms should not rely on the details of their operation remaining secret from an attacker ("security by obscurity"). This suggests relying on a mechanism's strength rather than its secrecy. While open design doesn't mandate using open-source software, research has shown that open design can benefit vulnerability testing and repair.

• **Complete Mediation:** Every possible avenue by which a resource can be accessed must be protected by a security check. This principle requires protection not just for data access, but also for access-control policy itself.

• **Least Privilege:** Any user, system, or system component should only have the minimum privileges or capabilities required to perform its intended job. This minimizes the potential harm if that component is compromised.

• **Multiple Layers of Defense (Defense-in-Depth):** A system's security should be protected by redundant or complementary mechanisms to ensure that a single mistake cannot compromise the entire system.

• **Psychological Acceptability:** Security mechanisms must be usable by their intended operators. If mechanisms are too inconvenient or demanding, users may intentionally circumvent them (e.g., sharing passwords on sticky notes), thereby reducing security. This is a major concern in policies like **Bring Your Own Device (BYOD)**, where cost and convenience are often weighed against security risks.

• **Safe Defaults:** Systems should be configured to provide security automatically, without requiring user intervention out of the box. Unsafe defaults can leave a system vulnerable to attack before a user manually adjusts settings.

These principles are crucial for guiding how engineers design and operate systems, recognizing that security involves careful balancing of mechanisms and usability.