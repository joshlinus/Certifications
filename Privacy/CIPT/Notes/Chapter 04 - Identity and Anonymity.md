#CIPT #IAPP #Identity #Access_Control

## Table of Contents
---
Chapter 4 - Identity and Anonymity 
	*Chris Clifton*
	[[#4.1 What is Identity?]]
		[[#4.1.1 How is Identity Used?]]
		[[#4.1.2 Representing Identity]]
	[[#4.2 Authentication]]
		[[#4.2.1 Passwords]]
		[[#4.2.2 Devices]]
		[[#4.2.3 Location]]
		[[#4.2.4 Biometrics]]
		[[#4.2.5 Multifactor Authentication]]
	[[#4.3 Identity Issues]]
		[[#4.3.1 Individually Identifiable Data]]`
	[[#4.4 Anonymization]]
		[[#4.2.2 Approaches to Anonymization]]
		[[#4.4.4 Aggregation-Based Approaches]]
		[[#4.4.5 Client-Side Control of Anonymization]]
	[[#4.5 Summary]]


## 4.1 What is Identity?
---
Identity is the crucial link between a piece of information and the individual(s) associated with that data. It's important to remember that information systems contain data _about_ people, not the people themselves. Formal definitions are necessary to clearly state how systems should utilize identity.

**Levels of Identity**
1. **Identified Individual:** This is the strongest form of identity, where a data item d is linked directly to a known individual i via an identity function I(d).
2. **Pseudonymous:** The data items are known to be about the same individual, but the individual’s legal identity is not necessarily known. Pseudonymous identity provides a greater level of privacy than an identified individual.
3. **Anonymous:** This provides the greatest level of privacy.

###### 4.1.1 How is Identity Used?
1. **Access Control**
	    ◦ This is the most obvious use of identity.
	    ◦ It determines whether a specific individual should be allowed to view a given piece of data.
	    ◦ While access control seems to necessitate an "identified individual," this is often unnecessary and may be inappropriate from a privacy viewpoint.
	    ◦ IT can support identification based on **roles** rather than requiring individual identification, which can significantly improve privacy.

2. **Attribution**
	◦ This serves as a second reason, besides access control, why an information system needs to know the identity of an individual.
	• For instance, in a credit card transaction, the merchant needs to be able to show that a purchase is legitimate (i.e., establish attribution).
	• While systems are often set up to require an **identified individual** for attribution, only a **role** (such as an authorized user) is truly needed.

3. **Personalization**
	    ◦ Identity is used to enhance the user experience, particularly through personalization.
	    ◦ For example, web searches by an identified individual can be customized based on their previous history or expressed desires.
	    ◦ In the case of personalization, only a **pseudonym** is usually needed. Knowing that a set of searches originated from the same individual is effective even if the individual's legal identity is unknown.

###### 4.1.2 Representing Identity
**Identifiers**
	• Identity can be represented by names, addresses, or account numbers. Uniqueness is a key challenge.
	• **Strong identifiers** are clearly identifying numbers, such as a national identification, passport, or credit card number.
	• **Weak identifiers** must be combined with other information (like name combined with birth date or address) to determine identity.
	• **Quasi identifiers** refer to data that can be linked to an individual when external knowledge is combined with it.

That's a useful comparison of identity representations. Here are the pros and cons for those three common identity mechanisms:

| Mechanism                                                  | Pros                                                                                                                                                                                                                                                                                   | Cons                                                                                                                                                                                                                                                                                       |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **User IDs (Login Names)**                                 | The system can guarantee **uniqueness** (by forbidding the use of an already taken ID). This approach provides a measure of **pseudonymity** if the individual is allowed to choose the ID, offering an additional measure of privacy.                                                 | Users may want the same ID, which can lead to conflicts and authentication failures (if too many incorrect passwords lock out the legitimate user). To reduce conflict, systems may require user IDs of a certain length or combination of characters, creating a **usability trade-off**. |
| **System-Generated IDs**                                   | They ensure privacy for all users if properly created, even those unaware of associated privacy risks. They provide the same opportunity for **pseudonymity**.                                                                                                                         | If they are based on other identifying data, they may not truly provide privacy. For instance, U.S. Social Security numbers, while unique, are generated using location and date information that **can help link individuals** to their numbers.                                          |
| **Externally Created Identifiers** (e.g., email addresses) | They are **user-friendly** because the user reuses another identifier and doesn't need to remember multiple sets of credentials. They outsource the burden of **ensuring uniqueness**. Email addresses can offer the option of **pseudonymity** if created without revealing identity. | They make it easier to **link information across multiple systems**, which creates a **privacy risk**. This linkability eases fraud or misuse of identity; for example, the widespread use of the U.S. Social Security number led to increased identity theft and fraud.                   |

**Representation Systems**
	• Systems created specifically for identity representation include the **X.500 standard**, which provides a flexible framework for storing and maintaining identifying information.
	• **Cryptographic certificates** and **Public Key Infrastructure (PKI)** provide mechanisms to verify identity. These systems typically combine identity representations with identity-related data like name and address.

**Biometrics**
	• **Biometrics** (like fingerprints or retinal scans) are used to represent identity and should ideally identify a specific individual with little effort.
	• Caution must be exercised when using biometrics, and the accuracy must be appropriate for the planned use. For example, a 2017 facial recognition attempt resulted in 92% false positives.
	• Using the same biometric for both identification and authentication poses risks because a false positive could grant access to the wrong person.

## 4.2 Authentication
---
Authentication is the process used to ensure that an individual performing an action matches the expected identity. It is closely tied to identity. Informally, authenticating to a computer system is often called "logging in".

Authentication can be accomplished by a variety of mechanisms, which fall into four main categories:
1. **What you know:** Secret knowledge held only by the individual corresponding to the identity (e.g., a password)
2. **What you have:** Authentication requires an object possessed by the individual (e.g., an identification badge or computing device).
3. **What you are (Biometrics):** Methods such as fingerprints, face and voice recognition, or retinal scans.
4. **Where you are (Location):** Location is generally viewed as a secondary form of authentication, used to provide stronger evidence that the primary authentication is correct.

These approaches can be combined using **multifactor authentication** (e.g., requiring a device and a password) to significantly decrease the risk of impersonation
###### 4.2.1 Passwords
Passwords or Personal Identification Numbers (PINs) are the most common authentication approach and are an example of "what you know" authentication, assuming only the authorized individual holds this secret knowledge. They can offer a high level of assurance, but improper use can easily break them.

**Attacks on Passwords**
Attacks generally fall into two categories: guessing the password and attacking the system itself.
1. **Guessing Attacks (Brute Force/Dictionary):**
	    ◦ Users tend to choose easy-to-remember words (dictionary attacks).
	    ◦ With short passwords like four-digit PINs, guessing is effective because people often choose predictable number patterns.
	    ◦ Systems attempt to mitigate this risk by disabling access after a few failed attempts, balancing security needs against the user burden of having to reset the password.

2. **System Attacks (Man-in-the-Middle and Replay):**
	    ◦ In a **man-in-the-middle (MiTM) attack**, a program intercepts traffic and reads the password.
	    ◦ To combat this, modern systems generally avoid storing the password itself. Instead, the system stores a **one-way hash** of the password.
	    ◦ However, an attacker who intercepts the hash can simply **replay** that hash to gain unauthorized access.
	    
	 ◦ **Defense:** This is countered using **challenge response** authentication, which issues a unique encryption key (the challenge) for each authentication session. The user application encrypts the password hash with this unique key, meaning the previous hash replay fails because it wasn't encrypted with the current challenge key.

**Secondary Authentication**
Systems often ask for answers to **security questions** (e.g., high school name) as a secondary form of authentication, especially during password resets. These answers must target private information that is unlikely to be known by an attacker. Like passwords, the answers must be protected, usually through a hash mechanism, to prevent disclosure

###### 4.2.2 Devices
This approach relies on an object possessed by the individual. It typically uses computing devices, such as identification badges or smart cards.
	• **Mechanism:** Authentication requires the computing terminal to be able to read the device. A convenient method is embedding a **Radio Frequency Identification (RFID) chip** in the device, which requires a corresponding reader.
	• **Privacy Risk (RFID):** RFID technology poses a privacy risk because a malicious actor using a remote RFID reader can detect when the user is nearby, even if the user is not trying to authenticate.
	• **Replay Attack:** If the actor reads the RFID card, they may be able to "become" that individual through a **replay attack**.
	• **Mitigation:** More advanced RFID systems mitigate replay attacks by using a **challenge-response approach**.
	---
	• **Device Loss:** Device-based authentication is problematic if the device is lost or stolen, compromising access until the loss is recognized and reported. For this reason, device authentication is usually combined with passwords or other authentication forms to ensure the lost device alone cannot grant access.

###### 4.2.3 Location
Location is generally viewed as a **secondary form of authentication**. Its primary purpose is to provide **stronger evidence** that the primary form of authentication (like a password or device) is correct.

###### 4.2.4 Biometrics
This form of authentication is growing increasingly popular.
• **Mechanism:** Biometrics use inherent individual characteristics such as fingerprints, face and voice recognition, and iris or retinal scans.
• **Adoption:** Portable devices like phones, tablets, and laptop computers commonly include the necessary sensing devices (cameras, readers, microphones) to support these methods.
• **Consideration:** While biometrics offer advantages, they also raise specific privacy issues
	• **Data Revealed** Biometrics vary regarding the amount of ancillary information they reveal about individuals. For example, fingerprints tend to reveal little extra information, perhaps only whether someone has engaged in significant manual labor (indicated by worn ridges). However, retinal images have the potential to indicate health conditions, such as diabetes.
	• **Linkage Potential** A trade-off exists regarding linkage opportunities. Fingerprints, because they are a frequently employed biometric (second only to facial images), potentially offer a multitude of linkages with other datasets containing auxiliary information. Retinal images, being relatively uncommon, tend to offer fewer linkage opportunities.
	• **Revocation** Biometric data raises specific privacy issues. Revoking biometric data is generally impossible. Therefore, systems using biometrics for authentication must be constructed using **strong cryptographic techniques** to ensure that this data is never compromised.

###### 4.2.5 Multifactor Authentication
Multifactor authentication (MFA) involves combining different authentication approaches to achieve a stronger verification of identity. This combination significantly decreases the risk of impersonation.

Mechanisms are combined across the categories of authentication:
1. **What you know + What you have:** Combining a password with a physical device (like an identification badge or computing device) is common. For example, due to the risk of a device being lost or stolen, device-based authentication is usually combined with a password to ensure the lost device alone cannot grant access.
2. **Location as a Secondary Factor:** Location ("Where you are") is generally considered a **secondary form of authentication** that provides stronger evidence that the primary authentication (like a password or device) is correct.
3. **Security Questions:** Systems also commonly ask for answers to security questions as a secondary form of authentication, particularly during processes like password resets

## 4.3 Identity Issues
---
###### 4.3.1 Individually Identifiable Data
Almost all privacy regulations define the scope of information they apply to; for example, the EU General Data Protection Regulation (GDPR) applies to personal data, and the U.S. Health Insurance Portability and Accountability Act (HIPAA) applies to protected health information.

While data not about an individual is clearly not covered, and data that is overtly identified clearly is, a large middle area exists where data is not overtly identified but may be _identifiable_.
• **Re-identification Risk:** Determining exactly how much information is needed to cross the threshold into individually identifiable data has little clear guidance. Early guidance from the European Commission Article 29 Working Party (WP29), now carried on by the European Data Protection Board (EDPB), suggests that no individuals should be identifiable.
• **The Sweeney Example:** Latanya Sweeney famously demonstrated this risk using publicly available data. She was able to identify numerous individuals by cross-referencing state-gathered hospital admission data (presumed to be anonymous) with publicly available voter registration data. Given a person’s postal code, date of birth, and gender, she estimated that 87% of U.S. persons could be identified. Consequently, this type of data is considered privacy sensitive

**HIPAA and Pseudonymity:** HIPAA provides a convoluted yet precise legal definition of **pseudonymity**. A deidentified dataset may include a code for re-identification, provided that the code is not derived from or related to the individual's information and cannot be translated to identify the individual. Furthermore, the code or the re-identification mechanism cannot be used or disclosed for any other purpose

The term **Limited Datasets (LDSs)** refers to a special provision made under the U.S. HIPAA Privacy Rule, which otherwise does not apply to anonymous data.

Here are the key details regarding LDSs:
• **Pseudonymity:** LDSs are datasets that are not individually identified. They are created as pseudonymous datasets by replacing individual identifiers with a number.
• **Purpose:** They serve as a good model for health care research. For example, names, addresses, and identifying numbers may be removed from hospital records for use in research, even though the full records are required for patient treatment.
• **Handling:** LDSs are handled with particular care because records within them (like birth dates and postal codes) are often identifiable. Access to LDSs must be restricted.
• **Sharing:** An LDS can be shared under a data use agreement, but it **may not be publicly released**.


## 4.4 Anonymization
---
###### 4.2.2 Approaches to Anonymization
Anonymization aims to reduce or remove identity information from data, but it remains an open research area, as advancements in anonymizing data are often met with advancements in reidentifying supposedly anonymous data. However, the risk of misuse of identifiable data is generally much larger than the risk posed by external attackers gaining access to data that has undergone anonymization.

Here are the core approaches to anonymization:
1. Suppression and Generalization (Microdata)
Anonymization is commonly applied to **micro datasets**, which contain individual records where identifying values have been suppressed, generalized, or had noise added to protect privacy.
	• **Suppression:** This is the simplest approach, involving removing identifying values from a record, such as names and identifying numbers.
	• **Generalization:** This involves replacing a specific data element with a more general element.
	    ◦ Example techniques include removing the day and month from a birth date, or replacing a full postal address with only the city and state/province.
	    ◦ Generalized individually identifiable data may still be covered by privacy law, but generalization does reduce the risk of damage if the data is inadvertently disclosed.

• **Guidelines:** The "Checklist on Disclosure Potential of Proposed Data Releases" offers guidelines for microdata release, such as generalizing geographic units to regions with at least 100,000 individuals, and top-coding ages over 85.
• **HIPAA Safe Harbor:** The HIPAA safe harbor rules provide a legal benchmark for what makes data individually identifiable. If a dataset meets these steps, it can be considered deidentified and not subject to the HIPAA Privacy Rule.

2. Formal Privacy Models
Formal definitions have been established to measure and protect privacy in microdata:
	• **k-anonymity:** This model requires every record in a micro dataset to be indistinguishable from at least k other people based on its quasi-identifying information. It ensures no record can be individually identified.
	• **l-diversity:** This model extends k-anonymity by requiring at least l distinct sensitive values within each group of k records to prevent privacy breaches where sensitive information (like occupation) is homogeneous within the indistinguishable group.
	• **t-closeness:** This model further refines protections beyond the limitations of k-anonymity and l-diversity.

3. Aggregation-Based Approaches
Instead of publishing deidentified records (microdata), aggregate statistics derived from the data can be released.
• **Re-identification Risk:** It is often possible to determine individual values from aggregate statistics through comparison or mathematical calculation.

• **Frequency vs. Magnitude Data:**
    ◦ **Frequency data** (where individuals contribute equally, such as a count of individuals at a given income/age) may be sufficiently protected by rounding techniques.
    ◦ **Magnitude data** (where individuals contribute unequally, such as average income by age) typically requires noise addition or entire cell suppression to ensure privacy.

• **Differential Privacy:** This is the most widely accepted formal definition for aggregate data release and noise addition. Differential privacy ensures that the chance of any single individual's data being revealed is bounded. A key challenge is determining the appropriate value (∈) for differential privacy, as it measures the quality of the aggregate rather than the risk to an individual. Differential privacy can also be used to release microdata, which would resemble synthetic microdata.

4. Client-Side Control
Anonymization is usually done by the data custodian, but client-side techniques can enhance anonymity.
	• **Proxies:** Proxy servers can hide the IP address of a request by replacing it with their own.
	• **Routing:** Techniques like onion routing (e.g., Tor) and crowds further extend the notion of proxies by hiding IP addresses even from the proxy server itself, using encryption to ensure only the first peer knows the request's origin and only the last peer knows its destination server.

The Trade-Off
The more personal information is sanitized or deidentified, the less privacy risk it presents, but the less useful the data is likely to be for analysis

###### 4.4.4 Aggregation-Based Approaches
Database reconstruction is a critical privacy concern when dealing with aggregate statistics derived from data.

The Problem
	• **Definition:** Database reconstruction is the process of building a dataset that would accurately generate the published aggregate statistics.
	• **Risk:** When a large enough set of aggregates is published, it is often possible to determine individual values. A reconstructed database can often be shown to be unique, or at least many of the records in the reconstructed dataset must exist in any dataset that generated those aggregates.
	• **Identifiability:** The data produced through reconstruction is essentially a micro dataset, making it vulnerable to the same reidentification attacks discussed for individual-level data.
	• **Real-World Vulnerability:** Real-world published aggregates, such as census tables, are vulnerable to database reconstruction.

Example of Reconstruction
It takes surprisingly few aggregates to inadvertently reveal individual information. For instance, if a company publishes three statistics about a cohort of three people:
1. The exact count (3).
2. The median age (30).
3. The average age (44).
4. The maximum age (72).

This set of statistics exactly reveals that the individual ages in that cohort must be thirty, thirty, and seventy-two.

**Mitigation**
Standard anonymization techniques, such as suppression, rounding, generalization, and top- or bottom-coding, do **not** guarantee protection against database reconstruction.
	• **Noise Addition:** The only way to provide guaranteed limits on this risk is through **noise addition**.
	• **Differential Privacy:** This approach adds sufficient noise to the aggregate results to hide the impact of any single individual. If the aggregate values (like mean and median) were published with a small amount of noise, any attempt at reconstruction would not be certain to yield the correct individual values

###### 4.4.5 Client-Side Control of Anonymization
While anonymization is typically a function of the data custodian, client-side techniques can be used by individuals to enhance their own anonymity.

Key Client-Side Anonymization Techniques
1. **Proxy Servers and Advanced Routing**
	    ◦ **Proxy Servers:** These servers hide the user's IP address by replacing it with the proxy server's address for the request.
	    ◦ **Advanced Routing:** Techniques such as onion routing and crowds extend the concept of proxies by hiding IP addresses even from the proxy server itself.
	    ◦ **Tor:** Tor (The Onion Router) is a practical example of such a system. It is a peer-to-peer network where a request is routed sequentially to multiple peers until the final peer makes the actual request to the destination server. Encryption ensures that only the first peer knows the request's origin, and only the last peer knows the server to which it is routed.

2. **Stripping Identifying Information**
	    ◦ Most internet traffic, such as a typical Hypertext Transfer Protocol (HTTP) request, contains considerable identifying information, including the browser type, the last page visited, and the type of machine.
	    ◦ **Private Web Search:** This is a browser plug-in designed to strip such identifying information from the request, leaving only the search text itself. However, even the search text alone may be sufficient to identify an individual, as shown by the AOL query log disclosure.

3. **Cover Queries (Decoy Traffic)**
	    ◦ Tools have been developed to generate **"cover queries"** (fake query traffic) intended to disguise a user's actual search request.
	    ◦ **Purpose:** This operates based on "security through obscurity," creating ambiguity about whether a specific query was issued by a person or automatically by a program.
	    ◦ **Example:** TrackMeNot is an add-on (for Firefox and Chrome) that protects a user's privacy by issuing decoy queries to major search engines.
	    ◦ **Mechanism:** The plug-in mimics a real user's behavior by sometimes performing a large number of queries quickly and selectively choosing whether or not to click through to a link

