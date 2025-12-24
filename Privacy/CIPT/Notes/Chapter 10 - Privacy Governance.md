#CIPT #IAPP 

## Table of Contents
---
Chapter 10 - Privacy Governance
	*David James Marcos, AIGP, CIPM, CIPT; Kira Fuller, CIPM; Nicole Uribe, CIPP/US*
	[[#10.1 Privacy and IT Roles and Responsibilities]]


## 10.1 Privacy and IT: Roles and Responsibilities
---
IT (Information Technology) is central to safeguarding individual privacy in the modern era, as digital and physical lives have become inseparable. The role of privacy engineering is to bridge the complementary perspectives of privacy professionals and engineers.

This requires creating scalable technical solutions that translate privacy principles and safeguards against privacy harms into measurable engineering requirements, accommodating the increasing scope, volume, and complexity of IT. The core goal is developing a practical, measurable governance program that connects privacy objectives with tangible capabilities within IT infrastructure.


## 10.2 Privacy Governance and Engineering: Bridging the Gap
---
The field of privacy engineering bridges the complementary perspectives of privacy professionals and engineers to create scalable technical solutions. The goal is to translate privacy principles and safeguards against harms into measurable engineering requirements.

Effective privacy engineering relies on a structured and enduring privacy governance model. Within this model, the privacy professional acts as a translator, balancing the needs of various stakeholders to ensure the success of the enterprise-wide privacy governance program. This model must integrate several elements:

• **Law, Regulation, and Policy:** These sit at the top, defining the fundamental and organizational requirements that must be translated into manageable and scalable tooling.

• **Compliance:** This element provides the essential structure for implementing and measuring privacy by establishing controls tied to practical measurements.

• **Security:** This is a necessary precursor, focusing on protecting against unauthorized access and malicious actions (Confidentiality, Integrity, and Availability-CIA triad).

• **Responsible AI:** This emerging domain builds upon privacy and security practices to assure appropriate processing of data by AI capabilities.

• **Technology:** This is the foundation where the governance program is realized and actionable, ultimately implementing all requirements via the core computational functions (Create, Read, Update, Delete-CRUD).

• **Industry Standards:** These establish a common language (e.g., ISO 19944, NIST SP 800-53) and provide transparency, aiding the translation of controls into IT requirements.

###### 10.2.1 Understanding Risk
A holistic privacy governance model requires a comprehensive framework to account for privacy risks and their mitigating controls. A risk is a hypothetical scenario that describes an unwanted event and the threats that allow it to occur, potentially leading to privacy harms on personal data.

**Key Components of Risk**
	• **Inherent Risk:** This risk is derived from the processing of personal data, including the type of data collected, its collection location, and the purpose of its use. Sensitive data, children’s data, and data collected from certain jurisdictions are typically considered higher risk.
	• **Key Risk Indicators (KRIs):** Privacy professionals must collaborate with domains like legal, security, responsible AI, and IT to assess these factors and determine the organization's agreed-upon KRIs. KRIs signify the business's threshold for its risk appetite.
	• **Controls and Residual Risk:** Organizations map catalogs of controls (administrative, technical, and physical) to inherent risks to ensure compliance with legal requirements. The remaining risk after these controls are applied is the residual risk.
	• **Privacy Audits:** Robust risk management includes conducting regular privacy audits, based on KRIs, to test the effectiveness of mitigating controls.

Frameworks from regulatory bodies like France's CNIL (which includes context, principles, and risk validation) and the U.S. NIST (which uses core, profiles, and implementation tiers) can help organize and manage these risks.

###### 10.2.2 Law, Regulation, and Policy
Law, regulation, and policy are the highest level of a privacy governance program, defining the foundational and organizational requirements that must be translated into technical and managerial tooling.

Key Concepts
	• **Scope and Variety:** An increasing number of privacy-impacting legal frameworks exist globally, including the EU General Data Protection Regulation (GDPR), which has led many countries like Brazil, India, and China to enact similar comprehensive laws. These are complemented by earlier or sector-specific laws, such as the U.S. Health Insurance Portability and Accountability Act (HIPAA).
	---
	• **AI Regulation:** AI is rapidly becoming a major regulatory focus, notably with the passage of the EU AI Act, imposing significant, overlapping requirements on IT.
	---
	• **Organizational Policy:** From an IT perspective, the legal team helps identify the core requirements and risks of these disparate laws. The organization must define core policies and objectives—such as ensuring employees processing personal data have a legitimate business need—to fulfill its legal obligations.
	---
	• **Flexibility for IT:** These top-level policies should focus on identifying key objectives rather than stipulating technical solutions. This deliberate flexibility affords privacy professionals and engineers the necessary latitude to define the governance program and choose between manual and automated controls, allowing the program to mature iteratively and keep pace with rapid IT evolution.

###### 10.2.3 Compliance
Compliance is a crucial element of a privacy governance program, providing the necessary structure to implement and measure privacy requirements. It translates legal and organizational policies into practical, measurable requirements.

**Key Compliance Concepts**
	• **Reasonable Assurance:** Requirements and objectives are not absolute but practical to implement and manage. This affords flexibility and grounds solutions in common sense.
	---
	• **Internal Controls:** These are objectives tied to practical measurements that evaluate components governed by the privacy program. They come in two forms:
	    ◦ **Preventive:** Designed to stop an activity before it occurs.
	    ◦ **Detective:** Designed to identify problematic activity after an event has occurred.
	---
	• **Continuous Monitoring and Overlap:** Internal controls should be continuously monitored, ideally through IT capabilities, for faster issue identification and remediation. Controls are often designed to overlap, which improves the resiliency of the program and assures objectives can be met even if some controls fail.

Compliance, therefore, provides a clear, measurable, and understandable framework essential for translating high-level policy requirements into actionable safeguards.

###### 10.2.4 Security
Security and privacy are deeply intertwined, with security serving as a necessary precursor to privacy—it is difficult to maintain privacy without adequate security.

**Core Role and Properties**
	• **Security Focus:** Security is primarily concerned with protecting systems against unauthorized access and malicious actions. Security risks are often defined by the **CIA triad**: Confidentiality, Integrity, and Availability.
	---
	• **Privacy Focus:** Privacy, conversely, is about enforcing **appropriate use** within a secure environment.
	---
	• **Technical Maturity:** Security is a technically mature and naturally technical undertaking compared to privacy. This maturity benefits privacy by providing an avenue for developing meaningful IT solutions to safeguard data.

**Relationship to Privacy Engineering**
Security provides a critical language for engineers. By leveraging security terminology, abstract privacy requirements can be translated into terms engineers readily comprehend and utilize.

Furthermore, security and privacy often rely on the same underlying IT capabilities and controls, such as **access control**, reinforcing the mutual value of integrated governance.

###### 10.2.5 Responsible AI
Responsible AI is a fast-growing area in IT that leverages and builds upon existing privacy policy and security practices. It focuses on imposing deeply technical requirements and developing new measures to monitor and assure the appropriate processing of data by AI capabilities.

**Role and Integration**
Responsible AI aims to assure appropriate processing of data by focusing on concepts like fairness and transparency. This domain builds upon and reinforces privacy and security controls.

**Challenges**
Since AI often requires significant data to produce accurate models, its needs may challenge an organization's strict privacy management policies. Therefore, organizations must carefully consider Responsible AI alongside privacy and security to make informed risk decisions.

**Control Example**
An example of an internal control in Responsible AI is the requirement to display conspicuous notice where AI-generated text is displayed to a user. This ensures transparency by augmenting privacy through alerting the user when AI is involved in generating the content.

###### 10.2.7 Industry Standards
Industry standards are critical for an IT-focused privacy governance program, providing structure and methods for measurement. Standards offer two key benefits:
1. **Common Language:** They establish shared terminology to describe privacy controls, which is especially valuable for international operations. These standards often represent a consensus among industry experts on necessary controls across many legal frameworks.
2. **Transparency:** Standards allow an organization to transparently describe its controls in common terms, helping to build trust with customers and supporting third-party audits and certifications.

**Examples of Industry Standards**
Many standards are in use globally, often complementing each other:

• **NIST SP 800-53:** This primary U.S. government standard, widely used by the private sector, was augmented in revisions to include privacy controls in its Appendix J, which are aligned with the Fair Information Practice Principles (FIPPs).

• **ISO 27701 (PIMS):** This standard enhances ISO 27001 (security) with specific privacy controls, covering requirements like those in the GDPR.

• **NIST AI RMF 1.0:** This voluntary framework helps organizations manage risks associated with AI, improving trustworthiness in the design, development, and use of AI systems.

• **ISO 19944:** Designed for cloud services, this standard supports transparent descriptions of cloud ecosystems, focusing on taxonomic categories of data, use, and data flow.

These standards help guide the translation of high-level compliance goals into practical, measurable technical controls within the IT infrastructure.
