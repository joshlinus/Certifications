#CIPT #IAPP 

## Table of Contents
---
Chapter 7 - Interference
	*Travis D. Breaux, CIPT*
	[[#7.1 Framework for understanding Inference]]
	[[#7.2 Interference from a Technology Perspective]]
		[[#7.2.1 Notifications, Unsolicited Messages, and Spam]]
		[[#7.2.3 Behavioral Advertising as Decisional Interference]]
		[[#7.2.4 Content Filtering and Recommnedations]]
		[[#7.2.5 Administrative Decision-Making]]
		[[#7.2.6 Cyberbullying as Interference with Personal Identity]]
		[[#7.2.7 Disinformation and Fake Representations]]
		[[#7.2.8 Social Engineering and Interconnected Systems]]
		[[#7.2.9 Administrative Intrusions into Personal Spaces]]


## 7.1 Framework for Understanding Inference
---
Interference is defined as any act that prevents or obstructs a process from being properly carried out. For individual privacy, it aligns with the right "to be let alone" and Alan Westin's concepts of solitude and reserve, representing a disruption of individual autonomy.

The risk of interference increases with the amount of information collected and maintained about a person. This can lead to a sense of intrusion, often called "creepiness," even if the inferred attribute is accurate.

Interference is commonly categorized into three general types:
1. **Obstruction or Decisional Interference:** This involves actions that interfere with decisions affecting a person's daily life, such as their ability to travel, get a loan, or obtain employment. This can be difficult to detect if the decision-making process is complex or hidden from the affected individual.
2. **Intrusion into Physical, Psychological, or Informational Spaces:** This includes actions that violate a person's solitude or reserve, such as searching private spaces, restricting movement, or sending alerts that divert their attention. Surveillance itself can cause psychological intrusion and subjective harm by making people feel uncomfortable behaving naturally under persistent monitoring.
3. **Interference with Representation of Self:** This category covers actions that alter how an individual is represented, such as changes to their marital, financial, or political status, potentially leading to unwanted attention.

Interference may be **direct**, where the affected person is involved and may challenge the decision, or **indirect**, where the effects occur separately from the act of interference itself.

For example, unwanted advertising, particularly if based on deeply inferred personal attributes (like pregnancy), can interfere with a person's private affairs by circumventing their ability to control the timing and circumstances of a disclosure.

![[Pasted image 20251214123338.png]]


## 7.2 Interference from a Technology Perspective
---
![[Pasted image 20251214123633.png]]

###### 7.2.1 Notifications, Unsolicited Messages, and Spam
Unsolicited messages, commonly referred to as "spam," and frequent notifications constitute an intrusion into an individual's psychological space (Type 2 interference). This interference can affect individuals differently depending on the message type and time of day.

**Key Details on Unwanted Messages:**
	• **Forms of Spam:** While spam is often limited to email, unwanted messages are increasingly sent via mobile or wearable app notifications and SMS texts. Unwanted app notifications and SMS texts are considered more intimate intrusions because they arrive on personal devices.
	• **Scale and Scope:** Spam is a significant security and economic threat, estimated to account for roughly 78% of the total volume of email sent.
	• **Regulation (U.S. Example):** The U.S. Controlling the Assault of Non-Solicited Pornography and Marketing (CAN-SPAM) Act was passed in 2003 to regulate spammers. Under this act, companies must provide one-click access to unsubscribe from bulk commercial emails. The unsubscribe link must be prominently displayed, and the receiving website cannot create obstacles or require additional information to complete the unsubscribe request.
	• **Regulation (EU Example):** In other jurisdictions, such as Europe, companies must obtain opt-in consent before sending marketing messages.
	• **Mitigation:** Companies can use opt-in or opt-out mechanisms to communicate more effectively with potential customers and provide them control over unwanted interference. Unwanted email is generally easy to filter using Bayesian algorithms.

Software Application Programming Interfaces (APIs) can expose personal data, leading to privacy violations, particularly when they allow data collected for one purpose to be used for another. This typically falls under Type 2 interference (intrusion) or Type 3 interference (interference with self-representation).

**Case Study: Path and Contacts**
In 2012, the social networking app Path was found to be copying users’ entire mobile address books (including full names, emails, and phone numbers) to its servers without user notification.
	• **Motivation:** Path's CEO stated the data upload was intended to "help the user find and connect to their friends and family on Path quickly and efficiently".
	• **Privacy Violation:** This was a misuse of contact information, originally collected for private communication (email and phone calls), for a secondary purpose: bootstrapping social network relationships.
	• **Response:** The discovery led to negative user reviews, press coverage, and eventually an apology from Path's CEO, who ordered the deletion of all user-uploaded contact information from the servers.
	• **Regulatory Context:** Path’s practice was found to be similar to a 2010 violation by Google Buzz, which resulted in the FTC finding Google engaged in deceptive business practices and requiring a 20-year privacy audit. Both cases violated the FTC’s Fair Information Practice Principles (FIPPs) regarding notice/awareness, choice/consent, and access/participation.

**Responsibility and Mitigation**
	• **Shared Responsibility:** Responsibility for API-related data exposure may be shared between the platform provider (like Apple, which provides the API platform to access contacts) and the app developer (like Path, which implemented the API call).
	• **Safeguards:** Companies can prevent this by implementing purpose-based access controls for APIs and requiring users to actively consent to contact mining. For example, Facebook and LinkedIn offer users the choice to mine their contacts, balancing the advantage of improving their network experience with the risk of unwanted exposure.

###### 7.2.3 Behavioral Advertising as Decisional Interference
Behavioral advertising involves constructing a longitudinal profile of an individual’s interests to serve targeted ads, an industry that generates billions in revenue annually. The FTC has noted that certain applications of this technology interfere with consumer privacy expectations.

**Classification of Interference**
![[Pasted image 20251214135742.png]]

**Approaches and Risks**
Behavioral advertising is conducted via two main approaches:
	• **First-Party:** The organization collecting the data is the same one using it for profiling (e.g., Amazon's recommendation service).
	• **Third-Party:** A distinct advertiser collects user behavior across multiple websites. Third-party approaches pose a higher risk of interference because they use two primary methods of profiling:
		◦ **Web-Based Profiling:** Uses browser technology to track users only on websites partnered with the advertiser.
		◦ **Network-Based Profiling:** Poses a serious interference risk because it involves partnering with ISPs and using deep packet inspection (DPI) to monitor user network traffic. Browser plug-ins designed to block web-based methods are ineffective against this highly intrusive technique.

The mere existence of a behavioral profile, especially if the individual lacks awareness or control over it, can constitute a **subjective privacy harm**.

**Case Example**
The NebuAd program illustrates the risks of the third-party model. NebuAd created network-based profiles without adequate customer awareness through partnerships with ISPs. When this practice came to light, customers complained, leading to congressional scrutiny, resulting in NebuAd losing its partners and halting its behavioral advertising development.

###### 7.2.4 Content Filtering and Recommendations
Content filtering and recommendations are used to tailor user experiences—such as recommending products or music—to increase engagement and support individual preferences.

This process relies on underlying models that can label content, such as using sentiment analysis to classify the emotional tone of text or identifying characteristics like race and gender in images.

A landmark example of this technique's potential for interference was a Facebook study where researchers used sentiment analysis to filter user feeds. They found that intentionally biasing the feed toward negative emotional posts made users more likely to post messages reflecting negative emotions, demonstrating an "emotional contagion" effect.

This manipulation of a user's emotional state is categorized as a **Type 2 interference** (intrusion into psychological or informational spaces)

###### 7.2.5 Administrative Decision-Making
Machine learning (ML) systems, driven by statistical analysis of vast amounts of data, are essential in consequential decision-making across domains such as credit scoring, employment, finance, and policing. When these systems fail, it is often difficult to explain the specific reasons for a result (explainability).

Interference and Bias
Administrative decision-making can cause interference, categorized as Type 1 (obstruction/decisional interference) and Type 3 (interference with self-representation).
	• **Employment and Bias:** ML models can be biased, potentially penalizing certain demographics. For example, personalized search advertising has been shown to differ based on the ethnicity associated with a person's name. Amazon scrapped an AI resume-selection tool because it penalized women candidates, demonstrating how algorithms can encode existing biases and interfere with job applications (obstruction).
	• **Justice System Bias:** The Loomis v. Wisconsin case involved the use of a proprietary algorithm (COMPAS) during sentencing to estimate the risk of recidivism. If algorithms are trained on historical data containing inherent biases (like those from over-policing certain neighborhoods), the resulting prediction system will perpetuate that bias.
	• **Transparency Challenge:** Even if the underlying data and algorithms were transparently released, they may be too voluminous or complex for manual review, forcing reliance on another ML system for interpretation. This raises questions about fairness when a decision about a person's freedom relies on an incomprehensible computed result.

###### 7.2.6 Cyberbullying as Interference with Personal Identity
Cyberbullying typically involves using technology to expose hidden personal details or fabricate information about an individual, which constitutes **Type 3 interference** (Interference with representation of self). It is a profound disruption of the right "to be let alone".

**The Clementi Case**
The seriousness of cyberbullying was highlighted by the suicide of Rutgers freshman Tyler Clementi in 2010. His roommate, Dharun Ravi, used a webcam to spy on Clementi and recorded him with another man. Ravi subsequently tweeted about the incident and posted the video, which became an international news story. The incident prompted New Jersey to enact the Anti-Bullying Bill of Rights, which made speech that "substantially disrupts or interferes with" a student's rights a violation of law.

**The Nature of Digital Interference**
	• **Persistence:** Unlike traditional privacy intrusions, cyberbullying is persistent and compounded by IT communications, extending beyond the event itself.
	• **Fabrication:** IT allows malicious actors to interfere without physical access through the use of "fake content" or interactions with "fake users".
	• **Mitigation:** Companies whose products are used to disseminate covertly collected or fabricated information can reduce the overall impact of the interference by creating features that allow users to report abuses quickly.

###### 7.2.7 Disinformation and Fake Representations
Disinformation involves creating and disseminating false information with the intent to mislead. This area primarily illustrates two types of interference:
1. **Type 1 Interference (Obstruction):** Fake product reviews, intended to trick consumers into purchasing items, are common examples of deception and constitute a **Type 1 violation** because they obstruct genuine purchasing decisions. The FTC has addressed this with updated disclosure guidelines and legal actions against companies buying fake reviews.
2. **Type 3 Interference (Representation of Self):** This is the core risk in this section, covering actions that alter how an individual is represented.

**Technologies and Risks**
Advances in technologies, such as large language models (LLMs) like ChatGPT and Bard, enable the generation of realistic fake content on demand, including short stories, product reviews, and computer code.
	• **Social Bots and Fake Users:** AI-powered **social bots** (sockpuppeting/astroturfing) manipulate social media discourse, stoke unrest, and systematically abuse others, constituting interference. Efforts to sway public opinion are Type 1 violations, while abusive actions are Type 2 intrusions.
	• **Deepfakes:** Deep neural networks create **deepfakes**—realistic, but entirely fake, audio, video, and photographic content. Examples include synthesizing a person's voice, creating non-consensual explicit videos, or fabricating defamatory videos of public figures. This is a severe Type 3 violation.
	• **Intrusiveness:** While detection technologies (often relying on other neural networks) exist, they may not be effective against targeted attacks aimed at individuals. The same generative AI tools used for legitimate business purposes—such as creating helpful, lifelike **chatbots** or advanced voice assistants—can be used maliciously for gaslighting, catfishing, or scamming at scale.

To mitigate harm, companies whose products are used to disseminate covertly collected or fabricated information can create features that allow users to report abuses quickly

###### 7.2.8 Social Engineering and Interconnected Systems
Social engineering is the use of psychology to manipulate people into divulging valuable information or granting access to property. When combined with technology knowledge, it becomes a powerful technique for interfering with user privacy.

**Case Study: Mat Honan Hack**
The compromise of journalist Mat Honan’s digital identity in 2012 (including his Twitter, Gmail, Apple ID, and Amazon accounts) demonstrated the vulnerability of interconnected systems to social engineering.

• **The Exploitation:** The attacker manipulated human decision processes in customer service centers, particularly at Amazon, to gain access. Initial access was gained by adding a credit card to Honan's Amazon account using easily obtainable information. A subsequent call used the last four digits of that card—a security flaw at the time—to change the account's email address.

• **Interconnection:** Access to the Amazon account revealed the last four digits of a credit card, which the hacker then used to illegally obtain a temporary password for the Apple ID. The Apple ID, in turn, was used to reset the passwords for Honan's Twitter and Gmail.

• **Interference Type:** This manipulation of security processes constitutes **Type 1 interference** (obstruction/decisional interference). The resulting false posts on Twitter were **Type 3 interference** (interference with self-representation).

• **Resolution:** Both Amazon and Apple quickly fixed the security flaws after the incident was publicized.

IT architects should proactively consider how their business processes—both human and automated—are vulnerable to exploitation by social engineering for conducting privacy attacks.

###### 7.2.9 Administrative Intrusions into Personal Spaces
Administrative monitoring is conducted by organizations, such as schools and workplaces, to ensure that employees or students conform to organizational practices and procedures. This monitoring often occurs in environments influenced by power relationships.

When monitoring involves mobile computing, organizational policies can extend to personal spaces outside the institution.
	• **School Example:** The FBI investigated the Lower Merion School District after administrators used webcams on school-issued laptops to spy on students inside their homes. A lawsuit was filed when surveillance photos taken in a student's home were used to confront them about alleged inappropriate behavior.
	• **Workplace Example:** The U.S. Supreme Court ruled in _City of Ontario v. Quon_ (2010) that a police department’s review of an officer’s personal messages on an employer-provided device did not violate privacy because the review was a work-related audit.

Administrative intrusions fall under Type 2 interference (encroaching on personal spaces) and potentially Type 1 interference (decisional interference) when the collected information is used to invoke governing policies. Organizations must assess the extent to which such monitoring interferes with the broader privacy expectations of their employees or students.