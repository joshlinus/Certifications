#CIPT #IAPP

## Table of Contents
---
Chapter 1 - Introduction to Privacy for the IT Professional
	*Travis D. Breaux, CIPT*
	1.1 Who should use this book?
	1.2 [[#What is Privacy?]]
	1.3 [[#Privacy Risks]]
	1.4 [[#Security, Privacy, and Data Governance]]
	1.5 [[#Privacy Principles and Standards]]
	1.6 [[#The Data Life Cycle]]
	1.7 [[#Individual Expectations of Privacy]]


## What is Privacy?
---
##### Prominent viewpoints on privacy
**Alan Westin’s Four States of Privacy:**
- **Solitude:** Being alone and free from observation by others.
- **Intimacy:** Sharing information and trust within a small, private group where secrecy is mutually respected.
- **Anonymity:** Remaining unidentifiable and free from surveillance while in public spaces.
- **Reserve:** Choosing to withhold communication or disengage to create a psychological barrier against intrusion, even in a crowd.
These four states describe **how individuals experience and expect privacy**, and how **technology can support or challenge** those expectations.

**Helen Nissenbaum’s Contextual Integrity:**
- Privacy is defined by **context-specific norms** that govern **how information is accessed and shared**.
- **Norms differ by domain** (e.g., banking vs. healthcare information follow different rules).
- **Norms are also personal and situational**, reflecting individuals’ expectations and reasons for controlling their information in specific contexts.
- **Key challenge for IT professionals:** identifying and preserving these relevant norms when designing or updating technology.

D**aniel Solove’s Taxonomy of Privacy:**
- Defines privacy through the **types of activities that invade it**, often identified in legal cases.
- Includes actions such as **interrogation and surveillance** (forcing disclosure of information).
- Covers **secondary use, appropriation, and distortion**, such as misusing or altering someone’s image or data.
- Helps identify **when technology may create privacy-threatening outcomes**.

**Ryan Calo’s Harm Dimensions:**
- **Objective harms:** Measurable, observable privacy violations with direct, known consequences.
- **Subjective harms:** Perceived or expected harms without measurable evidence but still impactful on individual behavior.
- **Impact:** Both types of harm can equally affect individuals’ sense of privacy and trust.
- **Challenge for IT professionals:** Recognize that **perceived harm** can be as damaging as actual harm, and use **privacy notices and controls** to maintain user trust.

## Privacy Risks
---
**Privacy Risks**: the likelihood that a privacy threat will exploit a vulnerability and the impact of this exploit on the individual and organizations that retain information on them.

**Threat Agents:** Sources of privacy or security threats can be **internal** (insiders) or **external** (outside actors).
- **Insider Threats:**
    - **Malicious insiders:** Employees intentionally stealing or misusing personal information.
    - **Nonmalicious insiders:** Employees who unintentionally cause harm due to **carelessness**, **mistakes**, **lack of training**, or **weak policies and controls**.
- **External Threats:**
    - Attackers outside the organization using similar tools and methods as security professionals.
    - **Phishing:** A social engineering tactic that tricks individuals into sharing sensitive information via seemingly trusted communications.
    - **Spear-phishing / Whaling:** Targeted phishing aimed at **high-profile individuals** (e.g., executives, HR managers) with greater access to sensitive data.


## Security, Privacy, and Data Governance
---
- **Confidentiality:** Ensures information is **accessible only to authorized individuals**.
- **Integrity:** Ensures information is **accurate and unaltered**, preventing unintentional or unauthorized modifications.
- **Availability:** Ensures information is **accessible and usable when needed** by authorized users.

## Privacy Principles and Standards
---
**Prominent Privacy Principles Developers Should Know:**
- **Fair Information Practice Principles (FIPPs)** – Published by the **FTC in 1977**; provides foundational privacy guidance for U.S. businesses.
- **OECD Guidelines (1980)** – Focuses on **privacy protection and trans-border data flows** among member countries.
- **APEC Privacy Framework (2005)** – Promotes **consistent privacy standards** across the Asia-Pacific region.
- **Generally Accepted Privacy Principles (GAPP)** – Published by **AICPA and CICA in 2009**; offers **privacy assurance standards** for organizations.
- **NISTIR 8062 (2017)** – Introduces **privacy engineering and risk management** concepts for U.S. federal systems.

**OECD Privacy Principles:**
- **Collection Limitation:** Limit personal data collection to lawful and fair means, with the knowledge or consent of the individual where appropriate.
- **Data Quality:** Ensure data is relevant, accurate, complete, and up to date for its intended purpose.
- **Purpose Specification:** Clearly state the purpose of data collection at or before collection, and limit use to that purpose or compatible ones.
- **Use Limitation:** Do not use or disclose data for other purposes without the individual’s consent or legal authorization.
- **Security Safeguards:** Protect personal data with reasonable measures against loss, unauthorized access, destruction, or misuse.
- **Openness:** Maintain transparency about data practices, including what data is held, its purposes, and the identity of the data controller.
- **Individual Participation:** Give individuals rights to access, review, and correct their personal data, and to challenge refusals or inaccuracies.
- **Accountability:** Data controllers are responsible for implementing and upholding all these principles.

## The Data Life Cycle
---
![[Pasted image 20251020213816.png]]
**Data Life Cycle Responsibilities:**
- Organizations must **define the purpose** for which personal data is collected and ensure **actual use aligns with stated purposes**.
- **Challenge for IT professionals:** Data purposes may **change over time** as business practices evolve.
- Under the **EU GDPR:**
    - **Data Controllers** – Decide the purposes and means of processing personal data  
    - **Data Processors** – Process data on behalf of the controller, following those defined purposes.


**Types of Data Collection:**
- **First-Party Collection:** Data is provided **directly by the individual** (e.g., filling out and submitting a web form).
- **Surveillance:** Data is **observed or captured** from a person’s behavior or activity **without their direct interaction**.
- **Repurposing:** **Reusing previously collected data** for a **different purpose** than originally intended (e.g., using a shipping address for marketing).
- **Third-Party Collection:** **Transferring data** to another entity that then **collects or uses it** for new purposes.


**Active vs. Passive Data Collection:**
- **Active:** The individual is **aware** that data is being collected.
- **Passive:** The individual is **unaware** that data is being collected.


**Consent Best Practices:**
- **Prior consent:** Always obtain consent **before data collection** to allow individuals to **opt in or opt out** and avoid misconceptions.
- **Explicit consent:** The individual must **actively take an action** to communicate agreement.
- **Passive or implied consent:** Consent is **assumed** through the individual’s use of a system, often guided by a **privacy notice** linked on a webpage, in installation instructions, or user manuals, without any direct action from the user.


**Overt vs. Covert Data Collection:**
- Collection is **overt** when individuals can access and understand privacy notices to infer what data is being collected.
- Collection may be **covert** if disclosures are vague, preventing individuals from anticipating the **scope or purpose**of data collection (e.g., online behavioral advertising).
**Repurposing Risks:**
- Using data collected for one purpose for a **different purpose** can **harm privacy** and may be **illegal** under some regulations.
- IT professionals should ensure **data uses and disclosures align** with the originally stated purposes.
**Data Retention and Disposal:**
- Consider **how long data is kept** to meet business or legal needs.
- Ensure **secure destruction** of data once retention is no longer required.
- Data Destruction Techniques (NIST SP 800-88, Appendix A):
    - **Clearing:** Overwriting data with pseudorandom values.
    - **Degaussing:** Using magnetic fields to erase data on electromagnetic storage.
    - **Physical destruction:** Incinerating or otherwise destroying the media.
- Best Practice: The **level of destruction** should match the **sensitivity of the data**.


![[Pasted image 20251020214939.png]]


## Individual Expectations of Privacy
---
- **User-Control Approach:**
    - Give individuals **control over their own privacy settings** to manage personal privacy risks.
    - Assumes individuals **understand their unique privacy risks** better than IT professionals.
- **Limitations:**
    - Individuals may **misjudge long-term privacy preferences**.
    - Protecting privacy may require collecting **more personal data** (e.g., age, gender, lifestyle), which can **increase exposure to risks**.
- **IT Professional Responsibility:**
    - Monitor and **mitigate privacy harms**.
    - **Refactor systems** with privacy controls as needed.
    - **Balance** individual privacy expectations with **business data needs**. (Utility vs Privacy)
