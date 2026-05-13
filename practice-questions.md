# AI-900 Practice Questions

> 81 scenario-based multiple choice questions covering all 5 domains.
> Weighted proportionally to exam weights. Includes multi-select and "minimize effort" question types.

---

## Domain 1: AI Workloads and Considerations (Questions 1–15)

### Question 1
Your company wants to build an AI solution that analyzes customer support emails to determine whether customers are happy or unhappy with the service. Which AI workload type does this scenario represent?

- A) Computer Vision
- B) Natural Language Processing
- C) Document Processing
- D) Generative AI

<details>
<summary>Answer</summary>

**B) Natural Language Processing**

Analyzing the emotional tone (sentiment) of text is a Natural Language Processing (NLP) workload â€” specifically sentiment analysis.

- A is wrong: Computer Vision processes images and video, not text.
- C is wrong: Document Processing extracts structured data from forms/invoices, not sentiment.
- D is wrong: Generative AI creates new content â€” this scenario is analyzing existing content.
</details>

---

### Question 2
A healthcare company is deploying an AI system that recommends treatment plans. During testing, the team discovers the model performs significantly better for one demographic group than another. Which Responsible AI principle is being violated?

- A) Transparency
- B) Accountability
- C) Fairness
- D) Reliability & Safety

<details>
<summary>Answer</summary>

**C) Fairness**

Fairness requires that AI systems treat all people equitably. If the model performs differently across demographic groups, it exhibits bias, which violates the Fairness principle.

- A is wrong: Transparency is about users understanding how the AI works.
- B is wrong: Accountability is about human oversight and governance.
- D is wrong: Reliability & Safety is about consistent, safe performance â€” not demographic bias.
</details>

---

### Question 3
Your organization has deployed an AI chatbot for customer service. The legal team requires that customers must always be informed when they are interacting with an AI system rather than a human. Which Responsible AI principle does this requirement address?

- A) Inclusiveness
- B) Privacy & Security
- C) Transparency
- D) Accountability

<details>
<summary>Answer</summary>

**C) Transparency**

Transparency requires that people understand when they are interacting with AI and how the AI system works. Disclosing that a chatbot is AI-powered â€” not a human â€” is a Transparency requirement.

- A is wrong: Inclusiveness is about making AI accessible to all people.
- B is wrong: Privacy & Security is about protecting personal data.
- D is wrong: Accountability is about human governance and responsibility for AI systems.
</details>

---

### Question 4
A logistics company needs to process thousands of shipping invoices daily, extracting vendor names, amounts, and dates from scanned PDF documents. Which AI workload type best fits this scenario?

- A) Computer Vision
- B) Natural Language Processing
- C) Document Processing
- D) Knowledge Mining

<details>
<summary>Answer</summary>

**C) Document Processing**

Extracting structured data (vendor names, amounts, dates) from scanned invoices is a Document Processing workload. Azure AI Document Intelligence (Form Recognizer) is purpose-built for this.

- A is wrong: While OCR is a Computer Vision capability, extracting structured fields from invoices is specifically Document Processing.
- B is wrong: NLP processes general language â€” not structured document fields.
- D is wrong: Knowledge Mining is about searching/indexing large document collections, not extracting specific fields from invoices.
</details>

---

### Question 5
An AI model used for loan approval decisions makes errors that occasionally deny qualified applicants. The company establishes a review board of humans who can override AI decisions and take responsibility for outcomes. Which Responsible AI principle is being applied?

- A) Fairness
- B) Reliability & Safety
- C) Transparency
- D) Accountability

<details>
<summary>Answer</summary>

**D) Accountability**

Accountability means people are responsible for AI systems. Establishing human oversight that can review and override AI decisions is the core of Accountability.

- A is wrong: Fairness is about equal treatment across groups.
- B is wrong: Reliability & Safety is about the AI working correctly, not human oversight.
- C is wrong: Transparency is about understanding how the AI works, not governance.
</details>

---

### Question 6
A hospital deploys an AI system to prioritize emergency room patients. During a system outage, the AI stops triaging patients entirely, creating a dangerous gap in care. Which Responsible AI principle does this failure most directly violate?

- A) Fairness
- B) Reliability & Safety
- C) Transparency
- D) Privacy & Security

<details>
<summary>Answer</summary>

**B) Reliability & Safety**

Reliability & Safety requires AI systems to perform consistently and safely, including handling failures gracefully. An AI system that completely fails during an outage â€” especially in healthcare â€” violates this principle.

- A is wrong: Fairness is about equal treatment across groups, not system uptime.
- C is wrong: Transparency is about users understanding how the AI works.
- D is wrong: Privacy & Security is about protecting data, not system reliability.
</details>

---

### Question 7
An AI recruitment tool stores candidates' resumes, personal addresses, and salary histories in an unencrypted database accessible to all company employees. Which Responsible AI principle is being violated?

- A) Fairness
- B) Transparency
- C) Privacy & Security
- D) Accountability

<details>
<summary>Answer</summary>

**C) Privacy & Security**

Privacy & Security requires that personal data is protected with proper access controls and encryption. Storing sensitive personal information in an unencrypted, widely accessible database directly violates this principle.

- A is wrong: Fairness is about unbiased outcomes across groups.
- B is wrong: Transparency is about understanding how the AI makes decisions.
- D is wrong: Accountability is about human oversight and governance of AI decisions.
</details>

---

### Question 8
A bank's AI-powered customer service chatbot only supports English text input. Customers who speak other languages or who rely on screen readers cannot effectively interact with the system. Which Responsible AI principle should guide improvements?

- A) Fairness
- B) Inclusiveness
- C) Transparency
- D) Reliability & Safety

<details>
<summary>Answer</summary>

**B) Inclusiveness**

Inclusiveness means AI systems should be accessible to all people regardless of language, disability, or other factors. A chatbot that excludes non-English speakers and users with accessibility needs violates Inclusiveness.

- A is wrong: Fairness is about unbiased outcomes, not accessibility.
- C is wrong: Transparency is about understanding how the system works.
- D is wrong: Reliability is about consistent, safe performance.
</details>

---

### Question 9
A company wants to: (1) scan delivery receipts to extract totals and dates, and (2) generate personalized marketing emails for each customer. Which TWO AI workload types are required? (Select two)

- A) Computer Vision
- B) Document Processing
- C) Generative AI
- D) Knowledge Mining

<details>
<summary>Answer</summary>

**B) Document Processing and C) Generative AI**

Extracting structured data (totals, dates) from receipts is Document Processing. Creating personalized marketing emails is Generative AI. Two distinct workload types are needed.

- A is wrong: Computer Vision analyzes images generally but doesn't extract structured document fields.
- D is wrong: Knowledge Mining is about searching and indexing documents, not extracting receipt fields or generating content.
</details>

---

### Question 10
Your AI model occasionally generates outputs that reference real individuals' private information from its training data. You want to address this with the MINIMUM implementation effort. What should you do?

- A) Retrain the model from scratch on fully filtered data
- B) Add a system message instructing the model not to reveal personal data
- C) Implement comprehensive data anonymization in the training pipeline
- D) Build a custom content filtering layer

<details>
<summary>Answer</summary>

**B) Add a system message instructing the model not to reveal personal data**

A system message is the quickest, lowest-effort way to constrain model behavior at inference time. It requires no retraining, no pipeline changes, and no custom code.

- A is wrong: Retraining from scratch is the highest effort option.
- C is wrong: Anonymizing training data requires significant pipeline work.
- D is wrong: Building a custom filter requires development effort. Azure OpenAI already has built-in filters, and a system message is simpler.
</details>

---

### Question 11
An AI image generator creates realistic images of people. The development team adds a visible watermark reading "AI-Generated" to all outputs. Which Responsible AI principle does this primarily address?

- A) Accountability
- B) Inclusiveness
- C) Transparency
- D) Fairness

<details>
<summary>Answer</summary>

**C) Transparency**

Labeling AI-generated content ensures users can distinguish AI output from real content. This is a Transparency measure â€” it helps people understand that they are viewing AI-generated material.

- A is wrong: Accountability is about human oversight of AI decisions.
- B is wrong: Inclusiveness is about accessibility for all users.
- D is wrong: Fairness is about unbiased outcomes across groups.
</details>

---

### Question 12
A retail company wants to analyze security camera footage to count how many customers visit each store section per hour. Which AI workload type is this?

- A) Document Processing
- B) Natural Language Processing
- C) Computer Vision
- D) Generative AI

<details>
<summary>Answer</summary>

**C) Computer Vision**

Analyzing video footage to count and track people is a Computer Vision workload â€” specifically spatial analysis or object detection applied to video streams.

- A is wrong: Document Processing extracts data from forms and invoices.
- B is wrong: NLP processes text and language, not video.
- D is wrong: Generative AI creates new content.
</details>

---

### Question 13
An AI hiring tool favors candidates from specific universities and doesn't explain to candidates why they were rejected. Which TWO Responsible AI principles are being violated? (Select two)

- A) Fairness
- B) Privacy & Security
- C) Transparency
- D) Inclusiveness

<details>
<summary>Answer</summary>

**A) Fairness and C) Transparency**

Favoring candidates from specific universities creates biased outcomes â†’ Fairness violation. Not explaining rejection reasons means candidates don't understand the AI's decisions â†’ Transparency violation.

- B is wrong: Privacy & Security concerns data protection, which isn't described in this scenario.
- D is wrong: Inclusiveness concerns accessibility, not bias in hiring criteria or explanation of decisions.
</details>

---

### Question 14
A retail company has thousands of printed invoices and wants to extract vendor names and totals with minimum custom development. Which approach should they use?

- A) Build a custom computer vision model to read invoices
- B) Use Azure AI Document Intelligence pre-built invoice model
- C) Train an NLP model on invoice text
- D) Use Generative AI to read each invoice

<details>
<summary>Answer</summary>

**B) Use Azure AI Document Intelligence pre-built invoice model**

The pre-built invoice model in Azure AI Document Intelligence is purpose-built to extract structured fields (vendor, total, dates, line items) from invoices with zero custom training â€” minimum effort.

- A is wrong: Building a custom CV model requires significant training data and development effort.
- C is wrong: NLP models process natural language, not structured document extraction.
- D is wrong: While possible, using GenAI for structured extraction is more complex and expensive than the purpose-built tool.
</details>

---

### Question 15
An autonomous delivery robot causes minor property damage due to a navigation error in its AI system. According to Responsible AI principles, who is responsible?

- A) The AI system itself
- B) The end user who deployed the robot
- C) The organization that developed and deployed the AI
- D) No one â€” AI errors are unavoidable

<details>
<summary>Answer</summary>

**C) The organization that developed and deployed the AI**

Accountability means PEOPLE and ORGANIZATIONS are responsible for AI systems, not the AI itself. The organization that built and deployed the AI must have governance and take responsibility for outcomes.

- A is wrong: AI systems cannot be held accountable â€” only people can.
- B is wrong: While users have some responsibility, the developing organization bears primary accountability.
- D is wrong: Accountability explicitly rejects the idea that no one is responsible for AI outcomes.
</details>

---

---

## Domain 2: Machine Learning on Azure (Questions 16–30)

### Question 16
A real estate company wants to predict the selling price of homes based on features like square footage, number of bedrooms, and neighborhood. Which machine learning technique should they use?

- A) Classification
- B) Regression
- C) Clustering
- D) Deep learning

<details>
<summary>Answer</summary>

**B) Regression**

Predicting a numeric value (selling price) from input features is a regression task. Regression predicts continuous numbers.

- A is wrong: Classification predicts categories (e.g., "luxury" vs "budget"), not numeric values.
- C is wrong: Clustering groups data without labels â€” this scenario has a specific target (price).
- D is wrong: Deep learning is a technique, not a task type. The task here is regression.
</details>

---

### Question 17
A bank wants to determine whether loan applications should be approved or denied based on credit score, income, and employment history. Which machine learning technique is most appropriate?

- A) Regression
- B) Clustering
- C) Classification
- D) Anomaly detection

<details>
<summary>Answer</summary>

**C) Classification**

Predicting a discrete category (approved or denied) is a binary classification task. The model learns from labeled examples of past decisions.

- A is wrong: Regression predicts numbers, not categories.
- B is wrong: Clustering finds groups in unlabeled data â€” this scenario has labeled outcomes (approved/denied).
- D is wrong: Anomaly detection identifies unusual patterns, not approve/deny decisions.
</details>

---

### Question 18
A marketing team has a large customer database but no predefined categories. They want to automatically group customers with similar purchasing behaviors to create targeted campaigns. Which machine learning technique should they use?

- A) Regression
- B) Classification
- C) Clustering
- D) Deep learning

<details>
<summary>Answer</summary>

**C) Clustering**

Clustering is an unsupervised learning technique that groups data points with similar characteristics â€” no predefined labels needed. Finding natural customer segments is a classic clustering use case.

- A is wrong: Regression predicts numeric values.
- B is wrong: Classification requires predefined labels/categories.
- D is wrong: Deep learning is a technique used for complex pattern recognition, not specifically for grouping.
</details>

---

### Question 19
In a machine learning dataset for predicting house prices, which of the following would be the label?

- A) Square footage
- B) Number of bedrooms
- C) Selling price
- D) Neighborhood

<details>
<summary>Answer</summary>

**C) Selling price**

The label is the value you're trying to predict â€” in this case, the selling price. Square footage, bedrooms, and neighborhood are features (inputs).

- A, B, D are wrong: These are all features (input variables used for prediction), not the label (target variable).
</details>

---

### Question 20
A data scientist wants to quickly try multiple algorithms and find the best-performing model without writing code. Which Azure Machine Learning capability should they use?

- A) Azure ML Designer
- B) Automated ML (AutoML)
- C) Azure ML Notebooks
- D) Azure ML Pipelines

<details>
<summary>Answer</summary>

**B) Automated ML (AutoML)**

AutoML automatically tries multiple algorithms and hyperparameters to find the best model. It requires no coding â€” you provide a dataset and target column, and AutoML does the rest.

- A is wrong: Designer is drag-and-drop visual ML but you still manually choose algorithms.
- C is wrong: Notebooks require writing code.
- D is wrong: Pipelines are for orchestrating ML workflows, not automatic algorithm selection.
</details>

---

### Question 21
Which architecture underpins modern large language models like GPT and enables them to process all parts of input text simultaneously rather than sequentially?

- A) Convolutional Neural Network (CNN)
- B) Recurrent Neural Network (RNN)
- C) Transformer
- D) Decision Tree

<details>
<summary>Answer</summary>

**C) Transformer**

The Transformer architecture uses self-attention mechanisms to process all tokens simultaneously (in parallel), making it much faster to train than sequential architectures. GPT stands for Generative Pre-trained Transformer.

- A is wrong: CNNs are used for image processing, not language models.
- B is wrong: RNNs process sequences one step at a time (sequential), which is slower.
- D is wrong: Decision trees are a traditional ML algorithm, not a deep learning architecture.
</details>

---

### Question 22
A data scientist splits a dataset into three parts: training, validation, and test sets. Which set is used to tune hyperparameters and check for overfitting DURING the training process?

- A) Training set
- B) Validation set
- C) Test set
- D) Production set

<details>
<summary>Answer</summary>

**B) Validation set**

The validation set is used during training to tune hyperparameters and monitor for overfitting. The training set teaches the model, and the test set evaluates the final model on completely unseen data.

- A is wrong: The training set is used to teach the model, not to tune hyperparameters.
- C is wrong: The test set is reserved for final evaluation AFTER training is complete.
- D is wrong: There is no "production set" in the standard ML data split.
</details>

---

### Question 23
You need to train a machine learning model on a large dataset in Azure ML. The compute should automatically scale up during training and scale down to zero when idle to minimize cost. What should you use?

- A) Compute instance
- B) Compute cluster
- C) Azure Virtual Machine
- D) Azure App Service

<details>
<summary>Answer</summary>

**B) Compute cluster**

Azure ML compute clusters auto-scale from a minimum (even 0 nodes) to a maximum during training, then scale back down â€” ideal for cost-effective, scalable training workloads.

- A is wrong: Compute instances are single VMs for development/notebooks â€” they don't auto-scale to zero.
- C is wrong: Azure VMs require manual management and don't auto-scale as part of Azure ML.
- D is wrong: App Service is for hosting web applications, not ML training.
</details>

---

### Question 24
After training a model in Azure ML, you need to deploy it as a real-time REST API with automatic scaling and built-in monitoring. What should you use?

- A) Compute cluster
- B) Batch endpoint
- C) Managed online endpoint
- D) Azure ML Designer

<details>
<summary>Answer</summary>

**C) Managed online endpoint**

Managed online endpoints in Azure ML provide real-time inference via REST APIs with autoscaling, built-in monitoring, and blue/green deployment â€” all fully managed by Azure.

- A is wrong: Compute clusters are for training, not real-time inference serving.
- B is wrong: Batch endpoints process large volumes of data offline, not real-time requests.
- D is wrong: Designer is for building ML pipelines, not deploying real-time endpoints.
</details>

---

### Question 25
A telecom company wants to predict the NUMBER of customers who will cancel their subscription next month. Which machine learning technique should they use?

- A) Classification
- B) Regression
- C) Clustering
- D) Anomaly detection

<details>
<summary>Answer</summary>

**B) Regression**

Predicting a NUMBER (how many customers) is a regression task because the output is a continuous numeric value. This is a common exam trap â€” "predict the number who will churn" is regression, while "predict WHETHER a customer will churn" is classification.

- A is wrong: Classification predicts categories (yes/no), not a count.
- C is wrong: Clustering groups data without labels.
- D is wrong: Anomaly detection identifies unusual patterns, not predicts counts.
</details>

---

### Question 26
Which TWO machine learning techniques require labeled training data? (Select two)

- A) Regression
- B) Clustering
- C) Classification
- D) Dimensionality reduction

<details>
<summary>Answer</summary>

**A) Regression and C) Classification**

Both regression and classification are supervised learning techniques that require labeled data â€” a dataset with known input-output pairs to learn from.

- B is wrong: Clustering is unsupervised â€” it finds groups without predefined labels.
- D is wrong: Dimensionality reduction is typically unsupervised.
</details>

---

### Question 27
A small company wants to build a classification model but has no data science team and no coding experience. Which Azure ML capability requires the LEAST effort to build and evaluate a model?

- A) Azure ML Notebooks with custom Python code
- B) Automated ML (AutoML)
- C) Azure ML Designer
- D) Custom deep learning with PyTorch

<details>
<summary>Answer</summary>

**B) Automated ML (AutoML)**

AutoML automatically tries multiple algorithms, tunes hyperparameters, and finds the best model â€” all without writing code. You just provide a dataset and select the target column.

- A is wrong: Notebooks require writing code â€” not suitable for non-coders.
- C is wrong: Designer is no-code but requires manually choosing and connecting algorithms.
- D is wrong: Custom deep learning with PyTorch requires significant coding expertise.
</details>

---

### Question 28
Your team has trained five versions of a fraud detection model. You need to track which version is deployed in production, compare accuracy metrics between versions, and quickly roll back if a new version underperforms. Which Azure ML feature supports this?

- A) Compute clusters
- B) Model registry
- C) Azure ML Designer
- D) Datastores

<details>
<summary>Answer</summary>

**B) Model registry**

The Azure ML model registry is a central repository for registering, versioning, and tracking models. It supports comparing versions, storing metadata/metrics, and managing which version is deployed.

- A is wrong: Compute clusters provide compute for training, not model version management.
- C is wrong: Designer is for building ML pipelines, not tracking model versions.
- D is wrong: Datastores connect to data storage, not model management.
</details>

---

### Question 29
You have a small structured dataset of 1,000 rows with well-defined numeric and categorical features. You need to predict whether customers will churn (yes/no). Which approach is most appropriate?

- A) Deep learning with a large neural network
- B) Traditional ML classification (e.g., logistic regression, decision tree)
- C) Generative AI with GPT
- D) Clustering

<details>
<summary>Answer</summary>

**B) Traditional ML classification**

For small, structured datasets with well-defined features, traditional ML algorithms (logistic regression, decision trees, random forests) are the best fit. They require less data and compute than deep learning.

- A is wrong: Deep learning needs large datasets and more compute â€” overkill for 1,000 structured rows.
- C is wrong: GPT is for text generation, not structured classification tasks.
- D is wrong: Clustering is unsupervised and doesn't predict a specific label.
</details>

---

### Question 30
A data scientist has trained a model and wants to deploy it with the LEAST infrastructure management. The model must serve real-time predictions via an API. What should they use?

- A) Deploy on a self-managed Kubernetes cluster
- B) Use an Azure ML managed online endpoint
- C) Host on an Azure VM with a Flask web server
- D) Use Azure Functions with custom container

<details>
<summary>Answer</summary>

**B) Use an Azure ML managed online endpoint**

Managed online endpoints are fully managed by Azure â€” autoscaling, monitoring, blue/green deployment, and infrastructure management are all handled for you. This requires the least operational effort.

- A is wrong: Self-managed Kubernetes requires significant infrastructure management.
- C is wrong: Hosting on a VM with Flask requires managing the VM, web server, scaling, and monitoring manually.
- D is wrong: Azure Functions requires more custom setup for ML model serving than managed endpoints.
</details>

---

---

## Domain 3: Computer Vision on Azure (Questions 31–44)

### Question 31
A retail company wants to count the number of products on a shelf and identify where each product is located in an image. Which computer vision task should they use?

- A) Image classification
- B) Object detection
- C) OCR
- D) Facial detection

<details>
<summary>Answer</summary>

**B) Object detection**

Object detection identifies objects AND their locations (bounding boxes) in an image. This is needed to count products and know where each one is.

- A is wrong: Image classification labels the entire image but doesn't locate individual objects.
- C is wrong: OCR extracts text from images.
- D is wrong: Facial detection finds faces, not products.
</details>

---

### Question 32
A company needs to digitize thousands of old printed documents by extracting the text content from scanned images. Which Azure service capability should they use?

- A) Azure AI Face
- B) Azure AI Vision â€” Image Analysis
- C) Azure AI Vision â€” OCR (Read API)
- D) Azure AI Language

<details>
<summary>Answer</summary>

**C) Azure AI Vision â€” OCR (Read API)**

The Read API in Azure AI Vision extracts printed and handwritten text from images and scanned documents. This is the OCR capability designed for text extraction.

- A is wrong: AI Face detects and analyzes faces.
- B is wrong: Image Analysis describes images and detects objects, not optimized for text extraction.
- D is wrong: AI Language analyzes text that's already in text format â€” it doesn't extract text from images.
</details>

---

### Question 33
A company wants to automatically extract vendor names, dates, and line items from scanned purchase invoices and store the data in a structured format. Which service should they use?

- A) Azure AI Vision
- B) Azure AI Language
- C) Azure AI Document Intelligence
- D) Azure OpenAI Service

<details>
<summary>Answer</summary>

**C) Azure AI Document Intelligence**

Azure AI Document Intelligence (formerly Form Recognizer) has pre-built models specifically for invoices, receipts, and other documents. It extracts structured key-value pairs, tables, and line items.

- A is wrong: AI Vision can read text (OCR) but doesn't extract structured invoice fields.
- B is wrong: AI Language processes natural language text, not structured document fields.
- D is wrong: OpenAI is for generative AI tasks, not structured document extraction.
</details>

---

### Question 34
A security company wants to verify that the person at a door matches a photo on their employee badge. Which Azure AI capability should they use?

- A) Azure AI Vision â€” Image Classification
- B) Azure AI Face â€” Face Verification
- C) Azure AI Face â€” Face Detection
- D) Azure AI Vision â€” Object Detection

<details>
<summary>Answer</summary>

**B) Azure AI Face â€” Face Verification**

Face verification compares two faces to determine if they are the same person (1:1 matching). This is exactly what's needed to compare a live face to a badge photo.

- A is wrong: Image classification labels entire images, not face comparison.
- C is wrong: Face detection only finds where faces are in an image â€” it doesn't compare them.
- D is wrong: Object detection identifies objects, not face identity.
</details>

---

### Question 35
Microsoft retired certain capabilities from the Azure AI Face service due to Responsible AI concerns. Which capability was restricted?

- A) Face detection (locating faces in images)
- B) Facial attribute analysis (glasses, head pose)
- C) Inferring emotional states from facial expressions
- D) Face verification (comparing two faces)

<details>
<summary>Answer</summary>

**C) Inferring emotional states from facial expressions**

Microsoft retired the ability to infer emotional states (happy, sad, angry, etc.) from facial expressions as part of their Responsible AI commitments. This technology was deemed unreliable and potentially harmful.

- A is wrong: Face detection is still available.
- B is wrong: Facial attribute analysis (glasses, head pose, blur, etc.) is still available.
- D is wrong: Face verification is still available (with Limited Access approval for identification).
</details>

---

### Question 36
You need to generate human-readable descriptions of images for a website's accessibility features (alt text). Which Azure AI capability should you use?

- A) Azure AI Vision â€” OCR
- B) Azure AI Vision â€” Image Captioning
- C) Azure AI Face
- D) Azure AI Language â€” Summarization

<details>
<summary>Answer</summary>

**B) Azure AI Vision â€” Image Captioning**

Image captioning generates natural language descriptions of images â€” exactly what's needed for alt text on websites.

- A is wrong: OCR extracts text FROM images, not describes images.
- C is wrong: AI Face analyzes faces, not general image content.
- D is wrong: AI Language summarizes text documents, not images.
</details>

---

### Question 37
A wildlife conservation group wants to identify which species of bird appears in each trail camera photo. Each photo contains exactly one bird. Which computer vision task should they use?

- A) Object detection
- B) Image classification
- C) OCR
- D) Facial analysis

<details>
<summary>Answer</summary>

**B) Image classification**

Image classification assigns a single category label to an entire image â€” exactly what's needed to classify each photo as a specific bird species.

- A is wrong: Object detection finds multiple objects AND their locations â€” unnecessary when there's one bird per image and you only need the species.
- C is wrong: OCR extracts text from images.
- D is wrong: Facial analysis detects and analyzes human faces.
</details>

---

### Question 38
A warehouse needs to identify all items visible on a conveyor belt and determine the exact pixel position of each item for a robotic arm to pick them. Which computer vision task is required?

- A) Image classification
- B) Object detection
- C) OCR
- D) Semantic segmentation

<details>
<summary>Answer</summary>

**B) Object detection**

Object detection identifies each object AND its location (bounding box coordinates). This is essential when a robotic system needs to know WHERE each item is, not just what's in the image.

- A is wrong: Image classification labels the whole image but doesn't provide item locations.
- C is wrong: OCR extracts text, not physical object positions.
- D is wrong: While semantic segmentation provides pixel-level detail, object detection with bounding boxes is the standard exam answer for locating objects.
</details>

---

### Question 39
A law firm needs to extract raw text from thousands of scanned historical documents. The documents have varied layouts with no consistent structure â€” they just need the plain text content. Which approach is most appropriate?

- A) Azure AI Document Intelligence custom model
- B) Azure AI Vision â€” OCR (Read API)
- C) Azure AI Face
- D) Azure AI Language

<details>
<summary>Answer</summary>

**B) Azure AI Vision â€” OCR (Read API)**

The Read API in Azure AI Vision extracts raw text from images and scanned documents â€” ideal when you need the plain text content without structured field extraction.

- A is wrong: Document Intelligence is for extracting STRUCTURED data (key-value pairs, tables) from forms. Overkill for plain text extraction from varied layouts.
- C is wrong: AI Face detects faces, not text.
- D is wrong: AI Language processes existing text â€” it can't extract text from images.
</details>

---

### Question 40
Which TWO capabilities are provided by Azure AI Vision? (Select two)

- A) Face verification (1:1 matching)
- B) Image captioning
- C) Key phrase extraction
- D) Optical character recognition (OCR)

<details>
<summary>Answer</summary>

**B) Image captioning and D) Optical character recognition (OCR)**

Azure AI Vision provides image captioning (generating text descriptions of images) and OCR via the Read API (extracting text from images).

- A is wrong: Face verification is provided by Azure AI Face, not Azure AI Vision.
- C is wrong: Key phrase extraction is an Azure AI Language capability, not Vision.
</details>

---

### Question 41
A developer needs to generate alt-text descriptions for 10,000 product images on an e-commerce website. They want to minimize custom development. Which approach requires the LEAST effort?

- A) Train a custom image classification model
- B) Use Azure AI Vision image captioning API
- C) Manually write descriptions for each image
- D) Use Azure OpenAI GPT-4 with vision for each image

<details>
<summary>Answer</summary>

**B) Use Azure AI Vision image captioning API**

The image captioning API generates human-readable descriptions of images automatically with no training required. Just call the API for each image â€” minimal development effort.

- A is wrong: Training a custom model requires labeled training data and development work.
- C is wrong: Manual writing for 10,000 images is extremely labor-intensive.
- D is wrong: While GPT-4 with vision can describe images, it's more complex to set up, more expensive, and not purpose-built for this task.
</details>

---

### Question 42
A retail chain wants to use camera footage to determine if customers are happy or sad while shopping, to measure store experience. Can Azure AI Face provide this capability?

- A) Yes â€” the Face service includes emotion detection
- B) No â€” Microsoft retired emotion detection from faces due to Responsible AI concerns
- C) Yes â€” but only with Limited Access approval
- D) No â€” the Face service cannot process video feeds

<details>
<summary>Answer</summary>

**B) No â€” Microsoft retired emotion detection from faces due to Responsible AI concerns**

Microsoft retired the ability to infer emotional states from facial expressions as part of their Responsible AI commitments. The technology was deemed unreliable and potentially harmful.

- A is wrong: Emotion detection was retired and is no longer available.
- C is wrong: This capability was fully retired, not gated behind Limited Access.
- D is wrong: The Face service CAN process video (for face detection, attributes), but emotion detection specifically was retired.
</details>

---

### Question 43
A stadium manager needs to monitor crowd density in real time and receive alerts when specific areas become dangerously overcrowded. Which Azure AI Vision capability should they use?

- A) Object detection
- B) Image classification
- C) Spatial analysis
- D) OCR

<details>
<summary>Answer</summary>

**C) Spatial analysis**

Spatial analysis in Azure AI Vision analyzes video feeds to track people movement, count individuals in zones, detect crowding, and monitor proximity â€” exactly what's needed for crowd density monitoring.

- A is wrong: Object detection identifies objects in still images, not real-time crowd monitoring in video.
- B is wrong: Image classification labels entire images.
- D is wrong: OCR extracts text from images.
</details>

---

### Question 44
A building security system needs to determine if an unknown person entering the lobby matches ANY employee in a database of 5,000 registered faces. Which Azure AI Face capability is required?

- A) Face detection
- B) Face verification
- C) Face identification
- D) Face attributes analysis

<details>
<summary>Answer</summary>

**C) Face identification**

Face identification is a 1:many comparison â€” it checks one face against a database of known faces to find a match. This is needed when you don't know who the person is and want to find them in a large database.

- A is wrong: Face detection only locates faces in an image, it doesn't compare or match them.
- B is wrong: Face verification is 1:1 â€” comparing two specific faces to see if they match. You'd need to already know who to compare against.
- D is wrong: Face attributes analysis detects glasses, head pose, etc. â€” not identity.
</details>

---

---

## Domain 4: NLP on Azure (Questions 45–58)

### Question 45
A company wants to analyze customer reviews to determine the overall sentiment and also identify which specific aspects (food, service, ambiance) customers feel positive or negative about. Which Azure AI capability provides this?

- A) Key phrase extraction
- B) Entity recognition
- C) Sentiment analysis with opinion mining
- D) Text summarization

<details>
<summary>Answer</summary>

**C) Sentiment analysis with opinion mining**

Opinion mining (aspect-based sentiment analysis) identifies sentiments linked to specific aspects. "The food was great but the service was slow" â†’ food: positive, service: negative.

- A is wrong: Key phrase extraction identifies important topics but not sentiment.
- B is wrong: Entity recognition identifies named entities, not sentiment.
- D is wrong: Summarization shortens text but doesn't analyze sentiment per aspect.
</details>

---

### Question 46
A news aggregation service needs to automatically identify all mentions of people, organizations, and locations in news articles. Which Azure AI Language capability should they use?

- A) Sentiment analysis
- B) Key phrase extraction
- C) Named entity recognition (NER)
- D) Language detection

<details>
<summary>Answer</summary>

**C) Named entity recognition (NER)**

NER identifies and categorizes entities in text into types like Person, Organization, Location, Date, etc. This is exactly what's needed to find people, orgs, and locations in articles.

- A is wrong: Sentiment analysis determines emotional tone, not entity identification.
- B is wrong: Key phrase extraction finds important topics but doesn't categorize them as Person/Organization/Location.
- D is wrong: Language detection identifies the language of text, not entities within it.
</details>

---

### Question 47
A multinational company needs to convert spoken Japanese in a meeting to spoken English in real time. Which Azure service should they use?

- A) Azure AI Translator
- B) Azure AI Language
- C) Azure AI Speech â€” Speech Translation
- D) Azure AI Speech â€” Speech-to-Text

<details>
<summary>Answer</summary>

**C) Azure AI Speech â€” Speech Translation**

Speech translation in Azure AI Speech converts spoken audio in one language to spoken audio in another language in real time. This is speech-to-speech translation.

- A is wrong: Azure AI Translator handles text translation, not spoken audio.
- B is wrong: AI Language processes text, not speech.
- D is wrong: Speech-to-Text converts audio to text in the same language â€” it doesn't translate.
</details>

---

### Question 48
A company wants to build a customer support bot that answers common questions using their existing FAQ documents and product manuals. Which Azure AI Language feature should they use?

- A) Sentiment analysis
- B) Conversational language understanding (CLU)
- C) Question answering
- D) Text summarization

<details>
<summary>Answer</summary>

**C) Question answering**

The Question Answering feature in Azure AI Language lets you build a knowledge base from FAQ documents and manuals, then answer user questions based on that content.

- A is wrong: Sentiment analysis determines emotional tone, not answers questions.
- B is wrong: CLU understands intents and entities in conversation, but doesn't create a knowledge base from documents.
- D is wrong: Summarization shortens text, not answers specific questions.
</details>

---

### Question 49
An application needs to understand user voice commands like "turn on the living room lights" and "set thermostat to 72 degrees." It must identify the user's intent and extract relevant entities (room, device, temperature). Which feature should you use?

- A) Azure AI Language â€” Question Answering
- B) Azure AI Language â€” Conversational Language Understanding (CLU)
- C) Azure AI Speech â€” Speech-to-Text
- D) Azure AI Language â€” Key Phrase Extraction

<details>
<summary>Answer</summary>

**B) Azure AI Language â€” Conversational Language Understanding (CLU)**

CLU is designed to understand user intents (e.g., "TurnOn", "SetTemperature") and extract entities (e.g., room="living room", device="lights", temperature="72") from conversational input.

- A is wrong: Question Answering answers from a knowledge base, not understands intents/entities.
- C is wrong: Speech-to-Text converts audio to text but doesn't understand intents.
- D is wrong: Key phrase extraction finds important terms but doesn't identify intents or structured entities.
</details>

---

### Question 50
Which of the following is a pre-built capability of Azure AI Language that works immediately without any custom training data?

- A) Conversational language understanding (CLU)
- B) Custom text classification
- C) Question answering
- D) Sentiment analysis

<details>
<summary>Answer</summary>

**D) Sentiment analysis**

Sentiment analysis is a pre-built feature of Azure AI Language â€” it works out of the box with no training data needed. You send text, it returns sentiment scores.

- A is wrong: CLU requires custom training data to define intents and entities.
- B is wrong: Custom text classification requires training with your own labeled data.
- C is wrong: Question answering requires you to provide FAQ/document content as a knowledge base.
</details>

---

### Question 51
A company wants to quickly understand the main topics discussed across thousands of customer feedback forms without reading each one. They need a flat list of important topics per form. Which NLP capability should they use?

- A) Sentiment analysis
- B) Key phrase extraction
- C) Named entity recognition (NER)
- D) Text summarization

<details>
<summary>Answer</summary>

**B) Key phrase extraction**

Key phrase extraction identifies the main concepts and topics in text, returning a flat list of important phrases. This is exactly what's needed to understand topics across many documents quickly.

- A is wrong: Sentiment analysis determines emotional tone (positive/negative), not topics.
- C is wrong: NER identifies named entities WITH categories (Person, Org, Location) â€” key phrases are broader topic concepts.
- D is wrong: Text summarization creates a shorter version of the text, not a flat list of topics.
</details>

---

### Question 52
Which NLP capability involves predicting the next word in a sequence and serves as the foundation for modern text generation systems like chatbots and auto-complete?

- A) Key phrase extraction
- B) Sentiment analysis
- C) Language modeling
- D) Named entity recognition

<details>
<summary>Answer</summary>

**C) Language modeling**

Language modeling is the NLP task of predicting the next word or token in a sequence. It is the core capability that underpins modern LLMs (like GPT), enabling text generation, chatbots, auto-complete, and code generation.

- A is wrong: Key phrase extraction identifies important topics in text.
- B is wrong: Sentiment analysis determines emotional tone.
- D is wrong: NER identifies named entities in text.
</details>

---

### Question 53
A medical practice needs to automatically transcribe doctor-patient conversations into text notes during appointments. Which Azure AI capability should they use?

- A) Azure AI Language â€” Text Summarization
- B) Azure AI Speech â€” Speech-to-Text
- C) Azure AI Speech â€” Text-to-Speech
- D) Azure AI Translator

<details>
<summary>Answer</summary>

**B) Azure AI Speech â€” Speech-to-Text**

Speech-to-Text (STT) converts spoken audio into written text â€” exactly what's needed to transcribe conversations into text notes.

- A is wrong: Text Summarization shortens existing text but doesn't convert audio to text.
- C is wrong: Text-to-Speech converts text INTO audio â€” the opposite direction.
- D is wrong: Translator converts text between languages, not audio to text.
</details>

---

### Question 54
A public transit system wants to announce upcoming stops in a natural, human-sounding voice generated from schedule data text. Which Azure AI capability should they use?

- A) Speech-to-Text
- B) Speech Translation
- C) Text-to-Speech
- D) Language Detection

<details>
<summary>Answer</summary>

**C) Text-to-Speech**

Text-to-Speech (TTS) converts written text into spoken audio with natural-sounding voices â€” ideal for reading schedule information aloud as announcements.

- A is wrong: Speech-to-Text converts audio INTO text â€” the opposite direction.
- B is wrong: Speech Translation converts spoken audio between languages.
- D is wrong: Language Detection identifies what language text is written in.
</details>

---

### Question 55
Which TWO are pre-built features of Azure AI Language that work immediately without any custom training data? (Select two)

- A) Conversational Language Understanding (CLU)
- B) Named entity recognition (NER)
- C) Question Answering
- D) Language detection

<details>
<summary>Answer</summary>

**B) Named entity recognition (NER) and D) Language detection**

NER and language detection are pre-built features of Azure AI Language â€” they work out of the box with no training data or configuration needed.

- A is wrong: CLU requires custom training to define intents and entities for your scenario.
- C is wrong: Question Answering requires you to provide a knowledge base (FAQ documents/content).
</details>

---

### Question 56
A company receives customer support emails in multiple languages. They want to automatically route each email to the correct language-specific support team with minimum setup. Which pre-built Azure AI Language feature should they use?

- A) Sentiment analysis
- B) Key phrase extraction
- C) Language detection
- D) Custom text classification

<details>
<summary>Answer</summary>

**C) Language detection**

Language detection is a pre-built Azure AI Language feature that identifies the language of input text â€” exactly what's needed to route emails by language with zero training or setup.

- A is wrong: Sentiment analysis determines emotional tone, not language.
- B is wrong: Key phrase extraction finds topics, not language.
- D is wrong: Custom text classification requires training data and setup â€” not minimum effort.
</details>

---

### Question 57
A company needs to translate thousands of written product manuals from English into 10 other languages. The content is text-only with no audio. Which Azure service should they use?

- A) Azure AI Speech â€” Speech Translation
- B) Azure AI Language
- C) Azure AI Translator
- D) Azure OpenAI Service

<details>
<summary>Answer</summary>

**C) Azure AI Translator**

Azure AI Translator is purpose-built for translating written text between languages. It supports document translation for large-scale text translation tasks.

- A is wrong: Speech Translation is for spoken audio, not written text.
- B is wrong: Azure AI Language provides text analytics (sentiment, NER, etc.), not translation.
- D is wrong: While OpenAI models can translate, Azure AI Translator is the purpose-built and more cost-effective service for bulk text translation.
</details>

---

### Question 58
A news agency analyzes articles and gets results showing 'Microsoft' tagged as Organization, 'Seattle' as Location, and 'January 2025' as DateTime. Which NLP capability produced these categorized results?

- A) Key phrase extraction
- B) Named entity recognition (NER)
- C) Sentiment analysis
- D) Language modeling

<details>
<summary>Answer</summary>

**B) Named entity recognition (NER)**

NER identifies entities AND categorizes them into types like Organization, Location, DateTime, Person, etc. The categorized output described is exactly what NER produces.

- A is wrong: Key phrase extraction returns a flat list of topics WITHOUT categories.
- C is wrong: Sentiment analysis determines emotional tone, not entity types.
- D is wrong: Language modeling predicts next words in a sequence.
</details>

---

---

## Domain 5: Generative AI on Azure (Questions 59–81)

### Question 59
Your company needs to deploy GPT-4 with enterprise-grade security, ensure that prompts and responses are NOT used to train the model, and support private network connectivity. Which service should you use?

- A) OpenAI (openai.com)
- B) Azure OpenAI Service
- C) Azure AI Language
- D) Azure Machine Learning

<details>
<summary>Answer</summary>

**B) Azure OpenAI Service**

Azure OpenAI provides enterprise security, compliance (SOC 2, HIPAA), private endpoints, and guarantees that your data is NOT used to train models.

- A is wrong: Public OpenAI doesn't provide the same enterprise security, private networking, or data privacy guarantees.
- C is wrong: AI Language is for text analytics (NLP), not generative AI model hosting.
- D is wrong: Azure ML is for custom ML models, not hosting OpenAI models.
</details>

---

### Question 60
A developer is testing different prompts with a GPT model and wants to provide the model with 3 example input-output pairs to guide its responses. What is this prompt engineering technique called?

- A) Zero-shot learning
- B) Few-shot learning
- C) Fine-tuning
- D) Chain of thought

<details>
<summary>Answer</summary>

**B) Few-shot learning**

Few-shot learning is a prompt engineering technique where you include a few examples (typically 2â€“5) in the prompt to demonstrate the desired behavior to the model.

- A is wrong: Zero-shot means no examples are provided â€” just instructions.
- C is wrong: Fine-tuning involves additional training with data, not adding examples to prompts.
- D is wrong: Chain of thought asks the model to show its reasoning steps, not provide examples.
</details>

---

### Question 61
A chatbot built with Azure OpenAI keeps generating plausible-sounding but incorrect answers about company policies. What technique should you implement to reduce this problem?

- A) Increase the temperature setting
- B) Implement RAG (Retrieval-Augmented Generation)
- C) Use a smaller model
- D) Remove the system message

<details>
<summary>Answer</summary>

**B) Implement RAG (Retrieval-Augmented Generation)**

RAG retrieves relevant documents (like company policy documents) and includes them in the prompt, grounding the model's responses in factual data. This is the primary technique to reduce hallucinations.

- A is wrong: Higher temperature increases randomness and would likely make hallucinations worse.
- C is wrong: Smaller models may hallucinate more, and this doesn't address the root cause.
- D is wrong: Removing the system message removes behavioral guardrails, making the problem worse.
</details>

---

### Question 62
You are using Azure OpenAI to build a code generation tool. You want the model to produce consistent, deterministic output with minimal creativity. What temperature setting should you use?

- A) 0 (or close to 0)
- B) 0.5
- C) 0.8
- D) 1.0

<details>
<summary>Answer</summary>

**A) 0 (or close to 0)**

A temperature of 0 makes the model's output as deterministic as possible â€” it always picks the most likely next token. This is ideal for code generation where consistency and correctness matter more than creativity.

- B, C, D are wrong: Higher temperatures increase randomness and creativity, which is undesirable for code generation where you want reliable, consistent output.
</details>

---

### Question 63
Which Azure service provides a unified portal where you can browse models from multiple providers (OpenAI, Meta, Mistral), test prompts in a playground, build prompt flows, and deploy AI applications?

- A) Azure OpenAI Service
- B) Azure Machine Learning
- C) Azure AI Foundry
- D) Azure AI Services

<details>
<summary>Answer</summary>

**C) Azure AI Foundry**

Azure AI Foundry (formerly Azure AI Studio) is the unified portal for browsing model catalogs, testing in the playground, building prompt flows, evaluating models, and deploying AI applications.

- A is wrong: Azure OpenAI Service hosts OpenAI models specifically, but Azure AI Foundry is the broader portal.
- B is wrong: Azure ML focuses on custom ML model training and deployment, not multi-provider model browsing.
- D is wrong: Azure AI Services is the collective name for individual AI APIs, not a unified portal.
</details>

---

### Question 64
Azure OpenAI Service includes built-in content filtering that blocks harmful content. Which four categories does the content filter evaluate?

- A) Violence, hate, sexual, self-harm
- B) Spam, phishing, malware, profanity
- C) Bias, privacy, copyright, misinformation
- D) Harassment, threats, discrimination, fraud

<details>
<summary>Answer</summary>

**A) Violence, hate, sexual, self-harm**

Azure OpenAI's built-in content filters evaluate content across four categories: violence, hate, sexual content, and self-harm â€” both in prompts (input) and completions (output).

- B is wrong: These are email/security categories, not Azure OpenAI content filter categories.
- C is wrong: These are Responsible AI concerns but not the specific content filter categories.
- D is wrong: These are general abuse categories, not the specific Azure OpenAI filter categories.
</details>

---

### Question 65
A developer wants to set up a GPT model as a friendly customer service agent that only answers questions about Azure products and politely declines off-topic questions. Where should they configure this behavior?

- A) Temperature setting
- B) System message
- C) Few-shot examples
- D) Max tokens

<details>
<summary>Answer</summary>

**B) System message**

The system message sets the model's persona, role, and behavioral constraints. You would write something like: "You are a friendly Azure support agent. Only answer questions about Azure products. Politely decline off-topic questions."

- A is wrong: Temperature controls randomness/creativity, not persona or topic constraints.
- C is wrong: Few-shot examples demonstrate format/style but aren't ideal for defining ongoing behavioral rules.
- D is wrong: Max tokens limits response length, not content scope or persona.
</details>

---

### Question 66
A data scientist has a dataset of 10,000 labeled images of skin conditions and needs to build a diagnostic model. The images are complex and require the model to learn subtle visual patterns that are difficult to define manually. Which approach is most appropriate?

- A) Traditional machine learning with manual feature engineering
- B) Deep learning with a neural network
- C) Clustering
- D) Regression

<details>
<summary>Answer</summary>

**B) Deep learning with a neural network**

Deep learning excels at unstructured data like images where features are complex and hard to engineer manually. Neural networks automatically learn relevant features from the image data.

- A is wrong: Traditional ML requires manual feature engineering, which is impractical for complex image patterns.
- C is wrong: Clustering is unsupervised and groups data â€” this scenario has labeled data and needs classification.
- D is wrong: Regression predicts numbers, not diagnostic categories.
</details>

---

### Question 67
A company wants to build a search feature where users type a natural language question and the system finds the most semantically similar documents â€” even if the exact words don't match. Which Azure OpenAI model type should they use?

- A) GPT-4
- B) DALL-E
- C) Embeddings
- D) Whisper

<details>
<summary>Answer</summary>

**C) Embeddings**

Embeddings models convert text into vector (numeric) representations that capture semantic meaning. Documents with similar meaning will have similar vectors, enabling semantic search even without exact keyword matches.

- A is wrong: GPT-4 generates text responses but isn't designed for similarity search across documents.
- B is wrong: DALL-E generates images from text, not relevant to document search.
- D is wrong: Whisper converts speech to text, not related to document similarity.
</details>

---

### Question 68
Azure OpenAI's content filtering system evaluates content at multiple severity levels. Which of the following correctly lists the four severity levels from least to most severe?

- A) None, Low, Medium, High
- B) Safe, Low, Medium, High
- C) Info, Warning, Error, Critical
- D) Green, Yellow, Orange, Red

<details>
<summary>Answer</summary>

**B) Safe, Low, Medium, High**

Azure OpenAI content filters classify content across four severity levels: Safe, Low, Medium, and High. Administrators can configure which severity levels are allowed or blocked for each of the four content categories (violence, hate, sexual, self-harm).

- A is wrong: The lowest level is "Safe", not "None."
- C is wrong: These are generic logging levels, not Azure OpenAI content filter severity levels.
- D is wrong: These are not the content filter severity levels.
</details>

---

### Question 69
Your team needs to evaluate and compare open-source models from Meta (Llama), Mistral, and Microsoft (Phi) alongside OpenAI models before choosing one for a project. Where in Azure can you browse and deploy models from all these providers in one place?

- A) Azure OpenAI Service
- B) Azure Machine Learning Studio
- C) Azure AI Foundry Model Catalog
- D) Azure Marketplace

<details>
<summary>Answer</summary>

**C) Azure AI Foundry Model Catalog**

The Model Catalog in Azure AI Foundry lets you browse, compare, and deploy models from multiple providers including OpenAI, Meta (Llama), Mistral, Microsoft (Phi), and Hugging Face â€” all from a single portal.

- A is wrong: Azure OpenAI only provides OpenAI models, not models from Meta, Mistral, etc.
- B is wrong: Azure ML Studio focuses on custom ML model training, not a multi-provider model marketplace.
- D is wrong: Azure Marketplace is for general software/services, not a model comparison portal.
</details>

---

### Question 70
You want an Azure OpenAI model to answer questions accurately about your company's internal HR policies, which are updated weekly. Which approach is MOST appropriate?

- A) Fine-tune the model every week with the latest policies
- B) Use RAG (Retrieval-Augmented Generation) with the current policy documents
- C) Increase the temperature to improve response variety
- D) Use a larger model like GPT-4 instead of GPT-3.5

<details>
<summary>Answer</summary>

**B) Use RAG (Retrieval-Augmented Generation) with the current policy documents**

RAG retrieves relevant documents at query time and includes them in the prompt. Since policies change weekly, RAG ensures the model always references the latest version without retraining.

- A is wrong: Fine-tuning every week is expensive, slow, and operationally complex.
- C is wrong: Higher temperature increases randomness â€” it doesn't improve factual accuracy.
- D is wrong: A larger model doesn't solve the problem of having outdated or missing policy information.
</details>

---

### Question 71
You instruct a GPT model: "Classify the following email as Urgent, Normal, or Low priority." You provide NO example input-output pairs â€” just the instruction and the email to classify. What prompt engineering technique is this?

- A) Few-shot learning
- B) Fine-tuning
- C) Zero-shot learning
- D) Chain of thought

<details>
<summary>Answer</summary>

**C) Zero-shot learning**

Zero-shot learning means giving the model instructions with NO examples in the prompt. The model relies entirely on its pre-trained knowledge to perform the task.

- A is wrong: Few-shot learning includes example input-output pairs (typically 2â€“5).
- B is wrong: Fine-tuning is additional training of the model, not a prompting technique.
- D is wrong: Chain of thought asks the model to reason step by step.
</details>

---

### Question 72
Your Azure OpenAI deployment needs to allow healthcare professionals to discuss medical self-harm topics for clinical purposes, while still filtering other harmful content. What must you do?

- A) Adjust the content filter severity threshold in the Azure Portal
- B) Request Limited Access approval from Microsoft to modify content filters
- C) Turn off all content filters in the deployment settings
- D) Use the public OpenAI API instead, which has no filters

<details>
<summary>Answer</summary>

**B) Request Limited Access approval from Microsoft to modify content filters**

Azure OpenAI content filters cannot be disabled or significantly modified without Microsoft approval through a Limited Access application. This ensures responsible use while allowing legitimate exceptions.

- A is wrong: You can adjust severity levels to some extent, but removing filters for sensitive categories like self-harm requires formal approval.
- C is wrong: Content filters cannot be simply turned off â€” this requires Microsoft approval.
- D is wrong: The public OpenAI API also has content moderation, and switching services doesn't address the requirement.
</details>

---

### Question 73
Which TWO features are unique advantages of Azure OpenAI Service compared to the public OpenAI API? (Select two)

- A) Access to GPT model family
- B) Private network connectivity via VNets and private endpoints
- C) Prompt engineering with system messages
- D) Customer data is NOT used for model training

<details>
<summary>Answer</summary>

**B) Private network connectivity and D) Customer data not used for training**

Azure OpenAI offers private endpoints/VNet integration and guarantees your data is never used to train models. These are enterprise features not available in the public API.

- A is wrong: Both Azure OpenAI and public OpenAI provide access to GPT models.
- C is wrong: Both services support system messages and prompt engineering.
</details>

---

### Question 74
A chatbot keeps generating incorrect information about your company's return policy. The correct policy is a short, one-page document. You want to fix this with the LEAST development effort. What's the quickest approach?

- A) Fine-tune the model on the return policy document
- B) Include the full return policy text in the system message
- C) Build a complete RAG pipeline with Azure AI Search and vector embeddings
- D) Retrain the model from scratch

<details>
<summary>Answer</summary>

**B) Include the full return policy text in the system message**

For a single short document, the quickest fix is to include it directly in the system message. No infrastructure, no retrieval pipeline, no training â€” just paste the text.

- A is wrong: Fine-tuning requires training data preparation and compute â€” much more effort.
- C is wrong: Building a full RAG pipeline with vector search is the right approach for LARGE document sets, but overkill for one short page.
- D is wrong: Retraining from scratch is the highest effort option.
</details>

---

### Question 75
A developer needs to generate realistic product images from text descriptions like "a red leather handbag on a marble counter" for an e-commerce catalog. Which Azure OpenAI model should they use?

- A) GPT-4
- B) DALL-E
- C) Whisper
- D) text-embedding-ada-002

<details>
<summary>Answer</summary>

**B) DALL-E**

DALL-E generates images from text descriptions â€” exactly what's needed to create product images from textual specifications.

- A is wrong: GPT-4 generates text and code, not images.
- C is wrong: Whisper converts speech to text (transcription).
- D is wrong: Embedding models create vector representations of text for similarity search, not images.
</details>

---

### Question 76
A legal firm wants a search system where lawyers type a question in plain English and the system finds the most semantically relevant case documents â€” even when exact keywords don't match. Which Azure OpenAI model type should power the search?

- A) GPT-4 for text generation
- B) DALL-E for image analysis
- C) Embeddings model for semantic search
- D) Whisper for transcription

<details>
<summary>Answer</summary>

**C) Embeddings model for semantic search**

Embeddings models convert text into numeric vectors that capture semantic meaning. Documents with similar meaning have similar vectors, enabling search by meaning rather than exact keyword matching.

- A is wrong: GPT-4 generates text responses but doesn't enable efficient similarity search across document collections.
- B is wrong: DALL-E generates images â€” not relevant to document search.
- D is wrong: Whisper converts speech to text â€” not relevant to document search.
</details>

---

### Question 77
Your company's compliance team asks how long Azure OpenAI retains prompt and completion data for abuse monitoring by default. What should you tell them?

- A) Data is never stored
- B) 7 days
- C) 30 days
- D) 90 days

<details>
<summary>Answer</summary>

**C) 30 days**

Azure OpenAI retains prompt and completion data for 30 days by default for abuse monitoring purposes. This can be reduced or removed by applying for an exemption through Microsoft.

- A is wrong: Data IS stored temporarily for abuse monitoring.
- B is wrong: The default retention period is 30 days, not 7.
- D is wrong: 90 days is longer than the actual 30-day default.
</details>

---

### Question 78
You want a GPT model to ALWAYS respond in valid JSON format and NEVER include explanatory text outside the JSON. Where should you configure this behavioral constraint?

- A) Temperature setting
- B) System message
- C) Max tokens parameter
- D) Top-p parameter

<details>
<summary>Answer</summary>

**B) System message**

The system message sets behavioral rules and output format constraints for the model. You would instruct: "Always respond in valid JSON format. Do not include any text outside the JSON object."

- A is wrong: Temperature controls randomness/creativity, not output format.
- C is wrong: Max tokens limits response length, not format.
- D is wrong: Top-p (nucleus sampling) controls which tokens to consider â€” not output format constraints.
</details>

---

### Question 79
A GPT model consistently gives wrong answers to multi-step math word problems. You cannot change the model or add example problems to the prompt. Which technique is most likely to improve accuracy?

- A) Set temperature to 1.0 for maximum creativity
- B) Add "Let's think step by step" to the prompt (chain of thought)
- C) Switch to a DALL-E model
- D) Increase the max tokens parameter

<details>
<summary>Answer</summary>

**B) Add "Let's think step by step" to the prompt (chain of thought)**

Chain of thought prompting asks the model to show its reasoning process step by step. This significantly improves accuracy on complex, multi-step reasoning tasks like math problems.

- A is wrong: Higher temperature increases randomness â€” it would make math answers LESS reliable.
- C is wrong: DALL-E generates images, not math solutions.
- D is wrong: Increasing max tokens allows longer responses but doesn't improve reasoning accuracy.
</details>

---

### Question 80
You are deploying an Azure OpenAI application and want to ensure harmful content is blocked in both user prompts and model responses. You want this with the LEAST configuration effort. What should you rely on?

- A) Build a custom content moderation pipeline from scratch
- B) Azure OpenAI's built-in content filters, which are enabled by default
- C) Manually review all inputs and outputs
- D) Use a third-party content moderation API

<details>
<summary>Answer</summary>

**B) Azure OpenAI's built-in content filters, which are enabled by default**

Azure OpenAI has built-in content filters that are automatically enabled on all deployments. They filter BOTH input (prompts) and output (completions) across four categories â€” violence, hate, sexual, self-harm â€” with zero configuration needed.

- A is wrong: Building custom moderation is maximum effort, not minimum.
- C is wrong: Manual review is not scalable and requires maximum human effort.
- D is wrong: Third-party APIs require integration work. The built-in filters require zero setup.
</details>

---

### Question 81
A startup is choosing between fine-tuning a GPT model on their support documentation versus using RAG (Retrieval-Augmented Generation). Their documentation changes frequently. Which factor MOST favors RAG over fine-tuning?

- A) RAG produces more creative responses
- B) RAG uses the latest documents at query time without retraining
- C) Fine-tuning is always free on Azure OpenAI
- D) RAG requires no documents at all

<details>
<summary>Answer</summary>

**B) RAG uses the latest documents at query time without retraining**

RAG retrieves current documents at query time, so when documentation changes, you just update the document store â€” no model retraining needed. Fine-tuning would require retraining every time documents change.

- A is wrong: RAG is actually more grounded/factual, not more creative.
- C is wrong: Fine-tuning has compute costs â€” it's not free.
- D is wrong: RAG requires a document store to retrieve from.
</details>
