#CIPT #IAPP 

## Table of Contents
---
Chapter 8 - AI and Machine Learning
	*Zhiwei Steven Wu*
	[[#8.2 Basics of Machine Learning]]
		[[#8.2.1 Neural Networks and Deep Learning]]
		[[#8.2.2 The Era of Generative AI]]
		[[#8.2.3 Behind the Scenes of ML Systems]]
		[[#8.2.4 Privacy Risks in Modern ML]]


## 8.2 Basics of Machine Learning
---
Machine learning (ML) is a broad discipline that enables computers to learn from patterns in data and their interactions with the world without direct programmer intervention. The three main paradigms of ML are:

1. **Supervised Learning:** The most developed paradigm, where an algorithm learns from a dataset labeled with the correct answers or desired outputs. The training process produces a predictive model that maps observable features to a predicted outcome, such as predicting a patient's risk for a disease based on their history.

2. **Unsupervised Learning:** Deals with unlabeled data and aims to explore and discover the inherent structure or patterns within the data, such as using clustering to organize data into similar groups.

3. **Reinforcement Learning:** Involves agents making increasingly informed decisions by interacting with an environment through trial and error. For example, a recommendation system learns which items to present to a user based on rewards (ratings or click-through rates).

###### 8.2.1 Neural Networks and Deep Learning
Deep learning is an advanced approach to machine learning that uses multilayered neural networks to perform complex tasks more effectively. It transforms and integrates all three learning paradigms: supervised, unsupervised, and reinforcement learning.

**The Technology**
The foundation of the neural network model is the **Perceptron**, introduced in 1957. A Perceptron can solve simple supervised learning problems where data is linearly separable (meaning it can be divided by a straight line or plane).

However, to handle complex, nonlinear problems like image recognition or language understanding, multilayer neural networks are required. Deep learning is specifically defined as having more than one hidden layer between the input and output layers. These multiple hidden layers work to extract and learn features from the input data, with each layer forming a progressively more complex representation.

**The Rise of Deep Learning**
The rise of deep learning since the mid-2000s was driven by three key factors:
1. **Massive Datasets:** Deep neural networks require far more data than traditional ML methods (like decision trees) to achieve superior performance without overfitting.
2. **Computational Power:** The development of powerful graphical processing units (GPUs) made it feasible to perform the necessary computations to train large deep neural network models.
3. **Architectural Advances:** Research introduced advanced designs, such as new activation functions (like the Rectified Linear Unit or ReLU) and attention mechanisms, which were crucial for generative AI breakthroughs.

Deep learning transformed reinforcement learning, famously enabling the AlphaGo Zero program to master the game of Go entirely through self-play.

###### 8.2.2 The Era of Generative AI
The emergence of generative AI is a major advancement in machine learning (ML), utilizing deep neural networks trained on massive datasets of text, images, code, and audio. These advanced models can produce narratives, code, images, and other content on command, transforming areas from content creation to personalized assistants.

Generative AI is underpinned by a combination of supervised, unsupervised, and reinforcement learning principles, leveraging sophisticated deep learning models like transformer-based architectures.

**How it is Trained:**
• **Next-Word Prediction (Supervised/Unsupervised):** Large Language Models (LLMs) essentially learn probability distributions over sequences of words. By processing vast amounts of text, LLMs predict the most likely next word, allowing them to generate paragraphs or stories.

• **Reinforcement Learning with Human Feedback (RLHF):** This method refines the model's performance by rewarding or penalizing output based on human trainers' feedback, ensuring generated text is more coherent, helpful, and contextually appropriate.

• **Foundation Models and Fine-Tuning:** Generative AI relies on "foundation models" pretrained on broad datasets. These models can be quickly adapted to new domains using a small amount of data through a technique called "fine-tuning".

###### 8.2.3 Behind the Scenes of ML Systems
**The Role of Data**
Data serves as the essential fuel for machine learning (ML) models, enabling them to learn patterns and make predictions. Complex models, such as deep neural networks, require massive data volumes to learn effectively and avoid overfitting. The quality and diversity of the data are often more critical than the sheer quantity for achieving reliable performance and reducing inherent bias. Training large ML systems is highly resource-intensive; for instance, the training of GPT-3 involved an investment of at least $12 million.

 **The Roles of Professionals**
Developing and maintaining ML systems requires several specialized roles:
	• **Data Engineers** build and manage the infrastructure necessary to gather, store, and process high volumes of data.
	• **Data Scientists** create, test, and refine the ML models, focusing primarily on maximizing predictive accuracy.
	• **Software Engineers** build and maintain the overarching infrastructure, emphasizing system reliability, safety, and privacy.
	• **Prompt Engineers** specialize in designing the specific instructions (prompts) used to generate desired outputs from large generative AI models.
	• **Responsible AI Teams** focus on the ethical implications of the technology and ensure compliance with legal and ethical standards, especially regarding privacy and bias.

###### 8.2.4 Privacy Risks in Modern ML
The application of Machine Learning (ML) can introduce several forms of privacy harms, drawing from Solove’s taxonomy.

**Confidentiality Harms**
ML applications rely on personal data (e.g., medical history, location, online behavior), raising concerns about the inadvertent disclosure of sensitive information. This harm relates to a "breach of confidentiality"—the disclosure of private information without consent.
	• **Memorization:** An extreme form of overfitting, memorization occurs when large models (like deep neural networks) learn noise and idiosyncrasies of the training data instead of general patterns. This allows individual training examples, such as private communications or personal details, to be extracted from the released ML model, as seen in examples with GPT-2.
	• **Leakage from Model Interaction:** When using generative AI models, users risk leaking private information to the platforms hosting the model, especially when interacting with models that simulate companionship and encourage the sharing of intimate details.

**Appropriation Harms**
ML can lead to appropriation risk—the use of an individual's personal information in ways not originally intended.
	• **Deepfakes:** Generative AI creates fake yet highly realistic images, video, or audio (deepfakes) that can impose a person's face or voice onto another body or narrative, causing serious privacy harm.
	• **Data Misuse:** Platforms may collect data to improve user experience but then share or sell it to third parties without consent, allowing the data to be repurposed for targeted advertising or consequential decisions.

**Decisional Interference**
This is the intrusion into an individual’s decision-making process regarding their private affairs.
	• **Bias and Discrimination:** ML models used for consequential decisions (e.g., health care, hiring, finance) can perpetuate existing unfair biases present in the training data, limiting an individual’s access to resources or opportunities. For example, a model trained on medical costs disproportionately underestimated the health needs of Black patients due to racial disparities in health spending.

**Intrusion**
Intrusion refers to invasive acts that disturb one's tranquility or solitude.
	• **Advanced Scams:** Modern ML, especially generative AI, enables highly believable and adaptable scams, making unwanted messaging and telemarketing significantly more potent tools for manipulation.

**Mitigations and Solutions**
Addressing these risks is a core part of "responsible AI" efforts, which involve:
	• **Privacy-Preserving Machine Learning (PPML):** Methods like **differential privacy** are used to ensure that any individual's data has a negligible effect on the trained model, preventing memorization attacks, though this may reduce model utility.
	• **Federated Learning:** Algorithms are trained locally across multiple devices without sharing raw data externally, reducing privacy risks.
	• **Fairness Research:** Algorithmic solutions address bias and discrimination in ML, recognizing inherent trade-offs between different fairness criteria.
	• **Regulatory Guidance:** The EU AI Act requires assessments to score the risk of decisional interference and surveillance in high-risk ML applications.