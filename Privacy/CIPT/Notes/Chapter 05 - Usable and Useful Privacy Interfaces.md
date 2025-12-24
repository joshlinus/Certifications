#CIPT #IAPP 

## Table of Contents
---
Chapter 5 - Usable and Useful Privacy Interfaces 
	*Florian Schaub, CIPP/US, CIPT; Lorrie Faith Cranor, CIPT*
	[[#5.1 Why User-Centered Privacy Design?]]
	[[#5.2 Privacy Decision-Making, Behavior, and Concerns]]
		[[#5.2.1 Privacy Preferences versus Behavior]]
		[[#5.2.2 Factors Affecting Privacy Decision-Making and Behavior]]
			[[#5.2.2.2 Bounded Rationality]]
			[[#5.2.2.3 Context Dependence]]
		[[#5.2.3 Manipulation of Privacy Behavior]]
	[[#5.3 Usability and User Experience]]
	[[#5.4 Design of Privacy Interfaces]]
		[[#5.4.1 Types of Privacy Interfaces]]
		[[#5.4.2 Common Usability Issues of Privacy Interfaces]]
		[[#5.4.3 Privacy Design Principles]]
		[[#5.4.4 Privacy Design Process]]
			[[#5.4.4.5 Leverage the Available Design Space]]
	[[#5.5 Usability Testing and User Studies for Privacy]]
		[[#5.5.2 What to Test]]
		[[#5.5.3 How to Test]]


## 5.1 Why User-Centered Privacy Design?
---
A design that prioritizes the user experience (UX) is crucial for three main reasons:

1. **Meeting Legal Obligations:** Privacy laws globally increasingly include **usability requirements** alongside transparency and choice mandates.
	 ◦ The EU General Data Protection Regulation (GDPR) demands that information be provided in a "clear and plain language" and be "concise, transparent, intelligible and easily accessible".
	 ◦ U.S. laws often require privacy policies to be "clear and conspicuous".
	 ◦ Newer laws prohibit the use of **deceptive designs** (often called "dark patterns") that impair a consumer’s ability to exercise their rights, such as the CCPA regulations against subverting a choice to opt-out.

2. **Minimizing Surprise:** When users are surprised by unexpected data practices, they are likely to become angry and lose trust.
	    ◦ **Aligning Expectations:** Users often assume their data will only be used to fulfill requests, not for secondary or unrelated purposes. Transparency is needed for all device capabilities, even inactive sensors.
	    ◦ **Understanding Controls:** Privacy controls must clearly explain their function and any potential **side effects**, such as how granting location access to an app might enable location-based advertising,.
	    ◦ **Reducing Regret:** Techniques like "nudges" (e.g., social media reminders about post audience) or short time delays (e.g., before sending an email) can reduce the opportunity for users to regret sharing information due to mistakes.

3. **Facilitating Trust:** Trust is gained by communicating clearly, treating users fairly, and providing controls.
	    ◦ **Clarity in Communication:** Organizations must communicate about privacy in a straightforward way, making users aware of the efforts taken to protect them (e.g., if employees manually listen to voice commands for service improvement).
	    ◦ **Meaningful Choices:** Providing users with actual, meaningful choices and controls, such as fine-grained mobile permission requests, gives them a sense of agency and control, fostering trust,.


## 5.2 Privacy Decision-Making, Behavior, and Concerns
---
###### 5.2.1 Privacy Preferences versus Behavior
The global privacy framework operates on the "notice and choice model," assuming consumers make informed, rational decisions (the "privacy calculus") aligned with their preferences after being given transparency about data practices.

In practice, privacy behavior is often inconsistent and rarely rational. This leads to the phenomenon known as the **Privacy Paradox**.

The Privacy Paradox describes the contradiction where individuals state high privacy concerns but then freely share personal information anyway. For example, a person concerned about health privacy may still use a fitness tracker, giving detailed health data to companies in exchange for personal insights.

A less common outcome is the **"reverse privacy paradox,"** where individuals exhibit privacy-protective behaviors despite expressing dismissive privacy perspectives

###### 5.2.2 Factors Affecting Privacy Decision-Making and Behavior
**Incomplete Information and Uncertainty:** People often lack full transparency about how their data is collected, processed, or shared for secondary, unexpected purposes. This uncertainty can lead to misconceptions about privacy protection. Sometimes, this results in the **control paradox**, where perceived control over data leads individuals to share _more_ information

![[Pasted image 20251209144228.png]]

###### 5.2.2.2 Bounded Rationality
Bounded rationality describes how humans rely on mental shortcuts, or **heuristics**, rather than fully rational processing when making privacy decisions due to limited time and ability to process all relevant information. This reliance can lead to inaccurate judgments about complex situations

**Heuristics (Mental Shortcuts)**
- **Availability Heuristic:**
    - **Concept:** People judge the **probability of risks** based on **readily available cues** rather than complex, uncertain information (like a privacy policy).
    - **Example:** Instead of reading a privacy policy, a user judges an online store's privacy risk based on its **visual design, reputation, brand name,** or the mere **presence of a privacy policy link**.
- **Representativeness Heuristic:**
    - **Concept:** People judge the likelihood of an event by how much it resembles a typical or known example. Since privacy intrusions (like tracking) are **often invisible** and rarely **personally encountered**, people perceive them as **low-probability events**.
    - **Example:** An individual rarely "sees" behavioral tracking, so they conclude that privacy intrusions are uncommon, even if they occur frequently in the background.

**Biases (Systematic Errors in Thinking)**
- **Anchoring:**
    - **Concept:** Initial, available information creates a **reference point** (an **anchor**) for future decisions.
    - **Manifestation:**
        - **Social:** How others disclose information informs one's own disclosure behavior.
        - **Ordering Effects:** Survey participants disclose **more information** if the survey **starts with intrusive questions** (the anchor) and then reduces in sensitivity, compared to the reverse order.
- **Loss Aversion:**
    - **Concept:** Individuals **dislike losses more than they like equivalent gains**.
    - **Privacy Context:** Explains why people are concerned about companies collecting their data (a perceived loss) but are **reluctant to pay** for a better privacy product (avoiding a financial loss/cost).
- **Hyperbolic Discounting:**
    - **Concept:** People place a much **higher value on immediate rewards** over future rewards, leading them to **discount** future risks.
    - **Privacy Context:** **Immediate gratification** (using an app/service, getting a "like") outweighs **hypothetical, uncertain, and non-immediate privacy risks**. Privacy is rarely the primary motivating factor.
- **Optimism Bias:**
    - **Concept:** People **systematically underestimate** the likelihood of a negative event happening **to them personally**, even when they recognize the general risk.
    - **Example:** Users recognize the risk of identity theft after a data breach but underestimate the chance of their **own identity being stolen**, leading them to potentially avoid taking protective action.
- **Default Bias:**
    - **Concept:** People have a general preference for **default choices** and tend to keep them.
    - **Reasons for Keeping Defaults (even if invasive):**
        - Lack of **awareness** of the setting or its privacy implications.
        - **Transaction costs** (time/effort to find and change the setting).
        - The **assumption** that default settings are set to protect them.

###### 5.2.2.3 Context Dependence
Privacy preferences and concerns are highly sensitive to the specific situation (context), not just generalized feelings. Your willingness to share information depends on factors like who is receiving the data, what type of information is shared, and the purpose of the transaction.

**Core Concepts**
	• **Contextual Integrity:** This framework links privacy expectations directly to context-dependent norms. When a data practice adheres to the established informational norms of a context (e.g., medical information shared with a doctor), it is usually accepted. Violating these norms is perceived as a privacy breach.
	• **Privacy Borders:** Privacy violations often occur when established boundaries governing information flow are broken. These borders include:
	    ◦ **Natural borders** (e.g., walls, encryption).
	    ◦ **Social borders** (norms of confidentiality and trust).
	    ◦ **Spatial or Temporal borders** (distance or passing of time).
	• **Boundary Regulation:** Individuals engage in a dynamic process of boundary regulation to continuously manage their privacy, attempting to find the desired balance between keeping information private and sharing it

NOTE: “As people go about their daily lives, they transition through many, sometimes overlapping contexts and, in doing so, engage in what Irwin Altman describes as a continuous and dynamic “boundary regulation process” to manage their privacy.45 People’s context-specific privacy preferences are affected by “external changes,” such as changes in context, actors, information, or transmission principles, as well as “internal changes,” such as changing privacy attitudes, preferences, prior experiences, or new knowledge. People adjust their behavior in attempts to achieve levels of privacy that align with their privacy preferences.”

###### 5.2.3 Manipulation of Privacy Behavior
Privacy-related decisions and behaviors can be manipulated through the system’s "choice architecture," steering users toward outcomes preferred by the business. These deceptive practices, often called **dark patterns**, intentionally exploit cognitive and behavioral biases inherent in human decision-making. Such manipulation is unethical because it restricts a person's self-determination and agency over their privacy

These patterns exploit cognitive biases to steer user behavior toward choices that benefit the service provider (e.g., maximizing data collection).

**Exploiting Cognitive Biases**
- **Default Settings and Preselection:**
    - **Exploits:** **Default Bias**. Most users don't review or change pre-set options.
    - **Pattern:** Settings are often defaulted to the most **privacy-invasive** option (e.g., automatically opting into targeted advertising).
    - **Result:** Users rarely exercise the **opt-out** choice, even if they dislike the practice.
- **Framing and False Hierarchy:**
    - **Concept:** The way choices are **described and presented** significantly affects user behavior.
    - **Framing:** Emphasizing **benefits** or **trust cues**, while **de-emphasizing risks**, nudges users toward riskier decisions.
    - **False Hierarchy:** The choice benefiting the organization is **highlighted and emphasized** over the consumer-benefiting choice.
    - **Example:** A large, brightly colored button for **"Accept All Cookies"** is contrasted with a smaller, subdued (e.g., gray) link for **"Manage or Reject Cookies."**
- **Norm Shaping:**
    - **Exploits:** **Anchoring** (or social proof).
    - **Pattern:** Presenting **other people's observed information-sharing behavior** (e.g., in a social media feed) to establish a perceived "norm" of disclosure.
    - **Result:** Users are more likely to disclose revealing information themselves if they see it modeled as acceptable by others. Content algorithms can purposely highlight specific posts to steer user behavior.

**Manipulating Effort and Access**
- **Cumbersome Privacy Choices (Unequal Paths):**
    - **Concept:** Making the path to the **privacy-friendly choice** significantly more **difficult, arduous, or lengthy**than the privacy-invasive choice.
    - **Result:** Users are deterred by the effort required and default to the easier, less private option.
- **Distractions and Delays:**
    - **Concept:** Inserting small **distractions or delays** between a user's **awareness of a privacy risk** (e.g., seeing a notice) and their **final action**.
    - **Result:** The intended protective effect of the privacy notice is often canceled out as the user focuses on their goal, not the risk.
- **Forced Action or Registration:**
    - **Exploits:** **Hyperbolic Discounting** (prioritizing immediate access).
    - **Pattern:** Users are **forced to accept** a data practice to continue using a desired service.
    - **Forced Registration:** Requires users to provide **more information** than necessary (e.g., during a simple purchase) just to complete the transaction.

**Using Incentives and Penalties**
- **Rewards and Punishment:**
    - **Pattern:** **Rewarding** the service's preferred choice or **punishing/deterring** privacy-friendlier choices.
    - **Reward Example:** Granting access to special features only if location data is provided. A "meter" that fills up as a profile is completed (exploits need for **immediate gratification**).
    - **Punishment Example:** Stronger constraints than necessary are applied when a user selects the privacy-friendly option (e.g., reducing core functionality when it's not strictly necessary).
    - **Problem:** This is particularly problematic when the incentive/penalty is **not directly related** to the data/choice being made.

## 5.3 Usability and User Experience
---
Good user experience (UX) design is the key to creating usable and useful privacy interfaces. UX design focuses on meeting users' needs, which includes fostering understanding, building useful systems, and ensuring people can use the system as intended.

**1. Usability** Usability refers to how easy a system or interface is to use. The International Organization for Standardization (ISO 9241-11) defines it as the extent to which a system helps specified users achieve specific goals with effectiveness, efficiency, and satisfaction in a defined context of use.
	Usability involves several components:
		• **Learnability:** How easily users can accomplish basic tasks the first time they encounter the system.
		• **Efficiency:** How quickly users can perform tasks once they have learned the system.
		• **Memorability:** How easily users can reestablish proficiency after a period of not using the system.
		• **Errors:** The number and severity of errors users make, and how easily they can recover.
		• **Satisfaction:** How pleasant the system is to use.

**2. Utility** Utility concerns functionality: Does the system support users in satisfying their needs and accomplishing their goals? A usable interface is useless if it does not align with users' actual needs and expectations. A useful system has both good utility and good usability.

**3. User Experience (UX)** UX design is a holistic approach centered on users and their needs, encompassing all aspects of the end-user's interaction with the company, its services, and its products. It integrates usability, utility, aesthetics, and simplicity.

The User-Centered Design Process
Good UX design follows a systematic, principled process that typically involves three phases, often completed iteratively:
	1. **UX Research:** Aims to understand the context of use and user needs. This involves methods like interviews, surveys, and competitive analysis to identify user populations, analyze characteristics, and define design requirements.
	2. **UX Design:** Aims to create solutions that meet user needs and requirements. Designs are iterative, starting with basic prototypes and sketches, and leveraging established best practices known as **design patterns**.
	3. **UX Evaluation:** Validates that the designs and prototypes meet the user needs and requirements identified in the research phase. Evaluation methods include usability tests, A/B testing, and quantitative assessments.

**Value-Sensitive Design (VSD)**
VSD is a crucial design approach for privacy that accounts for ethical values, such as privacy, in addition to standard usability goals. VSD methods help systematically assess values in relation to technology and stakeholders and develop designs that respect those values. The process places not just people and their needs, but also their values, at the center of the design

The VSD Process Steps
VSD involves a systematic process to integrate values into technology development:
	1. **Clarify Project Values:** The team must first define the ethical values (e.g., privacy, transparency, informed consent) relevant to the project and determine what those values mean within that specific context.
	2. **Identify Stakeholders:** The assessment must identify stakeholders who are directly impacted by the technology (data subjects, data processors) and those who are indirectly affected (e.g., bystanders or other household members incidentally recorded by sensors).
	3. **Identify Benefits and Harms:** Analyze the potential benefits and negative impacts (harms) for every identified stakeholder group at the individual, societal, and environmental levels. Empirical investigations, like user research, can help understand the reasoning behind users' sentiments.
	4. **Identify and Elicit Potential Values:** Map the identified benefits and harms to the corresponding ethical values (e.g., unanticipated data sharing is mapped to privacy concerns).
	5. **Develop Working Definitions of Key Values:** Operationalize key values by defining their components for the specific context. For instance, informed consent must include components like comprehension and voluntariness.
	6. **Identify Potential Value Tensions:** Recognize where values conflict (e.g., security versus privacy). VSD shifts the focus from binary trade-offs to framing how security requirements can be met while still respecting privacy.
	7. **Value-Oriented Design and Development:** Design efforts focus on the co-evolution of the technology and the social structures, developing prototypes and mockups that respect these values. Flexibility should be built into the technical architecture to support necessary value-driven changes.


## 5.4 Design of Privacy Interfaces
-----
###### 5.4.1 Types of Privacy Interfaces
The four core functions of privacy interfaces are transparency, choice, control, and access.

1. **Transparency (Privacy Notices)**
Privacy notices provide clarity about an organization’s data collection, processing, and sharing practices.

| Type                        | Description and Key Detail                                                                                                                                                                  |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Privacy Policies**        | The most common, but often ineffective, tool. They are lengthy (reading all annually would take about 244 hours) and often use legal jargon, making them difficult for users to understand. |
| **Informational Resources** | Complement policies by summarizing or highlighting important practices in a more accessible way, often using visual aids or videos.                                                         |
| **Integrated Notices**      | Short, relevant explanations embedded within the service's UX (e.g., during account creation).                                                                                              |
| **Privacy Indicators**      | Cues in the user interface or on a device indicating the state of a data practice (e.g., an LED light showing a camera is recording).                                                       |
| **Privacy Reminders**       | Used to remind users of previously agreed-upon data practices or legal obligations (e.g., U.S. financial institutions providing annual Gramm-Leach-Bliley Act notices).                     |

2. **Choice (Consent Interfaces)**
For consent to be valid, it must be a **freely given, specific, informed, and unambiguous** indication of agreement. It must be equally possible to agree or disagree.
	• **Opt-in vs. Opt-out:** Opt-in requires explicit consent before data processing begins. Opt-out assumes consent and provides the user an option to stop the practice. 

Integrated Opt-Out
These are opt-out choices that are presented directly within the user experience (UX) and are easily accessible in the context where they apply.

| Feature       | Description                                                                                                               |
| ------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **Placement** | Integrated into the user flow or contextually relevant part of the service's UX.                                          |
| **Example**   | An **"unsubscribe" link** in an email communication. Its presence is in the context where a user is likely to need it.    |
| **Benefit**   | They are readily available in the context where they are needed, making them easier to use and increasing user awareness. |

Decoupled Opt-Out
These choices are separated from the immediate action or flow, requiring the user to actively seek them out.

| Feature       | Description                                                                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Placement** | They are often described in a privacy policy, in separate advertising or cookie policies, or as part of general privacy settings.                         |
| **Challenge** | The main difficulty is that users may be unaware the data practice is occurring or may not know where to look for the control. They lack discoverability. |
| **Example**   | A choice to opt out of targeted advertising that is only explained deep within a lengthy **privacy policy**.                                              |

Effective design often centralizes privacy controls **(Decoupled)** while still presenting highly relevant options **(Integrated)** where and when users need to make a decision
	• **Integrated Prompts:** Requests are integrated into the UX (e.g., account creation checkboxes). **Deceptive Design:** Pre-checked boxes are discouraged because they are a deceptive design pattern that cannot guarantee a deliberate decision was made by the user.
	• **Delegated Consent:** Consent is obtained by a separate entity, such as a mobile operating system (platform) generating a permission prompt for an app.

3. Control (Privacy Settings)
Privacy settings aggregate choices and controls, enabling users to manage their privacy preferences in one location.
	• **First-Party Settings:** Controls made available and managed by the service provider or product manufacturer.
	• **Platform Settings:** Controls provided by the operating system (like iOS or Android) or browser, which regulate what information an app or service has access to.

4. **Access (Privacy Dashboards)**
Privacy dashboards typically give users organized access to the data an organization has collected about them.
	• **Functionality:** They facilitate core user rights, including viewing activity timelines, accessing data summaries, correcting inaccurate data, exporting data, and requesting deletion of data (Data Subject Access Requests or DSARs)

###### 5.4.2 Common Usability Issues of Privacy Interfaces
While privacy interfaces are intended to provide transparency and control, many fail to achieve these goals, leading to user surprise, distrust, and potential regulatory scrutiny. Most usability problems can be traced back to several common issues:

1. **Conflating Compliance and User Needs:** Interfaces are frequently created primarily to demonstrate **compliance** to regulators, often neglecting the actual needs of the user. Policies written by lawyers for lawyers are lengthy, use complex jargon, and often remain too abstract, making them ineffective as tools for creating user awareness.

2. **Lack of Meaningful Choices:** Users are often forced into "take-it-or-leave-it" scenarios (accept all terms or abandon the service). This fosters **digital resignation** and may lead to suspicion or regulatory investigation if the consent obtained is not genuinely informed and freely given.

3. **Poor Integration with UX and Habituation:** Privacy management is typically a secondary task for the user. When notices block the primary user experience (UX) flow or are shown at inopportune times, they are often dismissed quickly. Repeated exposure to seemingly irrelevant or disruptive privacy notices causes **habituation**, leading users to automatically ignore the content.

4. **Poor Discoverability:** Privacy notices and controls are often **decoupled** from the system’s primary UX, making it difficult for users to find them unless they possess substantial digital literacy. Due to inconsistent placement across services, finding controls can become a frustrating "scavenger hunt," causing users to incorrectly assume they have seen all relevant options.

5. **Confusing Interfaces:** Poor design can result in ambiguity. Issues include confusing or ambiguous wording or icons, choices with unclear effects (e.g., what an opt-out actually stops), and controls that behave contrary to a user’s mental model or expectation.

###### 5.4.3 Privacy Design Principles
A user-centric approach starts by understanding the privacy needs of different user populations (e.g., primary, secondary, and incidental users). It considers how humans perceive and process information using models like the Communication-Human Information Processing (C-HIP) model.

1. User Centric
	The design must ensure the user interface (UI) successfully achieves the following steps:
		• **Communication:** Ensure the privacy interface can gain user attention despite environmental distractions.
		• **Attention:** Get users to notice the interface and maintain attention long enough to process it. Habituation (ignoring repetitive notices) is a risk here.
		• **Comprehension:** Ensure users understand the interface's purpose, the implications of their choices, and the system's data practices.
		• **Intention & Behavior:** Translate comprehension into motivation and subsequent successful actions without error.

2. Relevant
	Privacy information and controls must be relevant to the user's specific context, transaction, or activity, rather than providing a comprehensive overview like a privacy policy. Notices should be explicit about:
	• What information is collected, processed, or shared.
	• Why the data practice is necessary and how it benefits the user.
	• What controls are available.
	Openly communicating privacy risks is also an opportunity to highlight protective measures that are in place.

3. Understandable
	Privacy information should be written in simple, plain language, avoiding legal and privacy jargon. Many existing privacy policies require advanced reading skills (e.g., college-level or higher) and are often too long to be useful. Focusing on contextual, concise notices allows for simpler, more direct writing.

4. Actionable
	Privacy notices are typically ineffective if they do not include an associated action or choice. Choices must be meaningful and provide agency, rather than forcing users into a "take-it-or-leave-it" decision regarding an entire privacy policy. Any feature limitations resulting from a user's choice should be clearly constrained to the immediate context of that choice.

5. Integrated
	Privacy information and controls should be seamlessly integrated into the system’s primary user experience (UX) rather than added on as an afterthought. They should use the same interaction methods as the system’s primary UX and be provided at interaction points when they matter most.

###### 5.4.4 Privacy Design Process
The Privacy Design Process is a systematic methodology for creating usable and useful privacy interfaces, combining principles from User Experience (UX), Privacy Impact Assessments (PIAs), and Value-Sensitive Design (VSD). This process ensures privacy requirements are met while aligning with users’ needs.

Here are the first four steps of the process:

**1. Build on Privacy Assessment, Management, and Engineering Practice** The process begins with a solid understanding of the system's data practices and associated privacy implications, often derived from formal PIAs, risk assessments, and compliance checks. This foundation identifies user rights and transparency requirements. Recommendations from these assessments might include mandates for data minimization, changes to collection practices, or requiring opt-in consent. Addressing privacy implications early allows for the inclusion of technical safeguards in hardware design, such as adding a physical lens shutter or recording indicator lights, which is central to Privacy by Design principles.

**2. Identify Users and Their Privacy Needs** This step requires identifying and consulting stakeholders impacted by the system to elicit their specific privacy expectations, concerns, and needs for information and control,. It is crucial to categorize the types of users interacting with the system:

• **Primary Users:** The intended audience who enrolls in the system, uses configuration wizards, and sets privacy controls.

• **Secondary Users:** Individuals who actively use the system but may have an incomplete understanding of its data practices (e.g., a child using a parent’s smartphone app).

• **Incidental Users:** People inadvertently or unwillingly subjected to data collection (e.g., guests recorded by a smart door lock or bystanders recorded by a drone).

**3. Identify Unexpected Data Practices** The design should focus particular attention on system data practices that users are likely to be unaware of or surprised by. This knowledge dictates which practices must be communicated prominently in the user experience. Practices that violate a user's expectations—such as a fitness watch recording location data when users only expect step counts—must be highlighted. Making users aware of these unexpected practices reduces surprise and is an opportunity to explain the necessity, benefits, and associated privacy risks while communicating the measures taken to mitigate those risks,.

**4. Integrate Privacy Interfaces into a System’s UX** Privacy notices and controls should be integrated into the primary User Experience (UX) where they are most relevant to the user's specific context or transaction,. Integration helps privacy interfaces gain user attention and makes them more concise, as they can rely on the context of the user's interaction,.

• **Layered Approach:** Privacy information should be concise and relevant, often provided through layered notices. This follows the **details on demand** design pattern, presenting an overview first and allowing the user to retrieve greater detail as needed.

The last step of this process is to **Conduct User Testing**, which validates the usability and usefulness of the developed interfaces against user needs

###### 5.4.4.5: Leverage the Available Design Space
This phase of the Privacy Design Process focuses on the practical implementation of privacy notices and controls by exploring all possible design choices (the "design space"). The aim is to develop user-centric privacy interfaces that operate successfully within the specific constraints of the system, such as limited screen size or interaction modalities.

![[Pasted image 20251209223440.png]]

The design space is structured by four key dimensions, helping designers generate and evaluate viable solutions:

1. Timing

The point in time when information or controls are presented significantly impacts a privacy interface's usability and relevance.

|   |   |
|---|---|
|Timing Type|Description|
|**At Setup**|Interfaces shown during initial use (e.g., account enrollment). Should only include information truly essential before use.|
|**Just-in-Time**|Shown in the same transactional context as the data practice, supporting immediate reasoning and allowing for concise notices (e.g., permission requests).|
|**Context-Dependent**|Triggered by the user’s specific context (e.g., physical proximity to a sensor or a change in sharing behavior).|
|**Periodic Reminders**|Used to renew consent or remind users of background data practices they previously agreed to.|
|**Persistent Indicators**|Continuously shown while a data practice is active (e.g., an LED light indicating a camera is recording).|
|**On-Demand**|Allows users to seek out and review privacy information or settings at any time, typically in a centralized location.|

2. Channel
	This dimension determines the communication path used to deliver the interface.
		• **Primary Channel:** The main device the user interacts with, typically the system involved in the data practice (e.g., a smartphone).
		• **Secondary Channel:** A different device or context, useful if the primary channel has limited capacity for complex interactions (e.g., a companion app for a smart speaker).
		• **Public Channel:** Used when data subjects cannot be reached individually, such as using public signs to notify about security cameras in an environment.

3. Modality
	The way privacy interfaces are presented or interacted with, engaging different senses.
		• **Visual:** The most common form, using text, icons, and graphical user interfaces. Combining icons with explanatory text is preferred, as privacy concepts are difficult to convey solely through visuals.
		• **Auditory:** Uses sound or voice commands (e.g., a camera shutter click or a voice notice that "This call may be recorded").
		• **Haptic and Other:** Utilizes vibration or ambient light cues as indicators for data collection.
		• **Machine-Readable Specifications:** Allows the consistent presentation and aggregation of notices and controls across different apps and systems (e.g., mobile apps declaring permissions to the operating system).

4. Control
	This dimension defines how user choices, consent dialogs, and privacy settings are delivered, affecting user interaction.
		• **Blocking Controls:** Force users to interact with the interface before proceeding (e.g., mobile permission requests). This is necessary when consent is mandatory, but all options (allow/deny) must be equally easy to execute.
		• **Nonblocking Controls:** Integrated into the user experience without interrupting the flow (e.g., an audience selector within a social media post creation interface).
		• **Decoupled Controls:** Not part of the primary UX flow, typically provided in a centralized location like a settings menu or privacy dashboard
## 5.5 Usability Testing and User Studies for Privacy
---
Usability testing is essential for confirming that privacy interfaces are usable and useful for users. This process helps assess user needs, evaluate design trade-offs, validate the final product against requirements, and diagnose the root causes of problems.

###### 5.5.2 What to Test
Usability testing in privacy focuses on whether the interface successfully addresses the user's needs and context, especially concerning the core steps of the Communication-Human Information Processing (C-HIP) model.

| Test Area                                                            | Description and Purpose                                                                                                                                                                                                                                                                                                                                          |
| -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Preferences, Expectations, Concerns, and Mental Models** (5.5.2.1) | These factors influence privacy decisions and the types of features users seek. Early exploratory studies—using surveys, interviews, or focus groups—identify privacy needs, concerns, and potential misconceptions (mental models) early in the design process.                                                                                                 |
| **Awareness and Attention** (5.5.2.2)                                | Tests ensure the privacy interface successfully gains the user's attention, overcoming the "first big hurdle" in the C-HIP model. Studies assess whether users notice notices or indicators while focused on a primary task, as the timing of presentation significantly impacts attention.                                                                      |
| **Discoverability** (5.5.2.3)                                        | Tests whether users can find relevant interfaces easily and efficiently. For example, studies evaluate if opt-out choices are better placed within account settings versus buried deep within a privacy policy.                                                                                                                                                  |
| **Comprehension** (5.5.2.4)                                          | Users must understand the wording, symbols, and choices provided. Testing is often iterative, ensuring users correctly interpret icons (e.g., distinguishing between icons conveying 'choice' versus 'privacy') or technical jargon.                                                                                                                             |
| **Utility** (5.5.2.5)                                                | This ensures the interface meets actual user needs and is useful. It evaluates if important information or necessary settings (e.g., a desire for a summary rating alongside detailed privacy information for an IoT device) have been omitted.                                                                                                                  |
| **Behavior** (5.5.2.6)                                               | This investigates actual user action and execution of choices. It identifies failures related to: **The Gulf of Evaluation** (user misunderstanding the current state or consequence of a setting) and **The Gulf of Execution** (user failing to take the correct sequence of actions to achieve their goal, like forgetting to click a final "submit" button). |

###### 5.5.3: How to Test
UX professionals utilize several techniques for testing, varying in cost, complexity, and the type of data they produce.

| Testing Method                                | Description                                                                                                                                                                                                                                                                                           |
| --------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Formative Evaluations** (5.5.3.1)           | Used to gain insights into which aspects of a prototype need improvement. These are small-scale, iterative studies focused on gathering **rich qualitative insights**.                                                                                                                                |
| **Summative Evaluations** (5.5.3.1)           | Used to compare a product or design against a benchmark (e.g., an older version or competitor) to validate performance. These are larger studies focused on gathering **quantitative data** (e.g., speed of task completion, error rate).                                                             |
| **Small-Scale User Testing** (5.5.3.2)        | Provides a high return for early formative evaluations. Can be conducted remotely or in a lab, often asking users to "think aloud" for real-time commentary. This approach provides strong qualitative data but generally cannot be used to make statistical claims about the entire user population. |
| **Online Panels and Crowdsourcing** (5.5.3.3) | Used to recruit large numbers of participants efficiently for online studies. Platforms like Prolific or Amazon Mechanical Turk provide workers who perform tasks for pay. This requires careful screening to ensure the sample is appropriate.                                                       |
| **A/B Testing** (5.5.3.4)                     | Compares two versions (A and B) of a product or interface in a live environment to measure which performs better based on a chosen metric. In privacy, this can measure the impact of interface changes on user engagement with settings or opt-out rates.                                            |




