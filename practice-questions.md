# AI-900 Practice Questions

> 33 scenario-based multiple choice questions covering all 5 domains.
> Weighted proportionally: D1 (15%), D2 (18%), D3 (18%), D4 (18%), D5 (30%).

---

## Domain 1: AI Workloads and Considerations (Questions 1–5)

### Question 1
Your company wants to build an AI solution that analyzes customer support emails to determine whether customers are happy or unhappy with the service. Which AI workload type does this scenario represent?

- A) Computer Vision
- B) Natural Language Processing
- C) Document Processing
- D) Generative AI

<details>
<summary>Answer</summary>

**B) Natural Language Processing**

Analyzing the emotional tone (sentiment) of text is a Natural Language Processing (NLP) workload — specifically sentiment analysis.

- A is wrong: Computer Vision processes images and video, not text.
- C is wrong: Document Processing extracts structured data from forms/invoices, not sentiment.
- D is wrong: Generative AI creates new content — this scenario is analyzing existing content.
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
- D is wrong: Reliability & Safety is about consistent, safe performance — not demographic bias.
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

Transparency requires that people understand when they are interacting with AI and how the AI system works. Disclosing that a chatbot is AI-powered — not a human — is a Transparency requirement.

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
- B is wrong: NLP processes general language — not structured document fields.
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

## Domain 2: Machine Learning on Azure (Questions 6–11)

### Question 6
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
- C is wrong: Clustering groups data without labels — this scenario has a specific target (price).
- D is wrong: Deep learning is a technique, not a task type. The task here is regression.
</details>

---

### Question 7
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
- B is wrong: Clustering finds groups in unlabeled data — this scenario has labeled outcomes (approved/denied).
- D is wrong: Anomaly detection identifies unusual patterns, not approve/deny decisions.
</details>

---

### Question 8
A marketing team has a large customer database but no predefined categories. They want to automatically group customers with similar purchasing behaviors to create targeted campaigns. Which machine learning technique should they use?

- A) Regression
- B) Classification
- C) Clustering
- D) Deep learning

<details>
<summary>Answer</summary>

**C) Clustering**

Clustering is an unsupervised learning technique that groups data points with similar characteristics — no predefined labels needed. Finding natural customer segments is a classic clustering use case.

- A is wrong: Regression predicts numeric values.
- B is wrong: Classification requires predefined labels/categories.
- D is wrong: Deep learning is a technique used for complex pattern recognition, not specifically for grouping.
</details>

---

### Question 9
In a machine learning dataset for predicting house prices, which of the following would be the label?

- A) Square footage
- B) Number of bedrooms
- C) Selling price
- D) Neighborhood

<details>
<summary>Answer</summary>

**C) Selling price**

The label is the value you're trying to predict — in this case, the selling price. Square footage, bedrooms, and neighborhood are features (inputs).

- A, B, D are wrong: These are all features (input variables used for prediction), not the label (target variable).
</details>

---

### Question 10
A data scientist wants to quickly try multiple algorithms and find the best-performing model without writing code. Which Azure Machine Learning capability should they use?

- A) Azure ML Designer
- B) Automated ML (AutoML)
- C) Azure ML Notebooks
- D) Azure ML Pipelines

<details>
<summary>Answer</summary>

**B) Automated ML (AutoML)**

AutoML automatically tries multiple algorithms and hyperparameters to find the best model. It requires no coding — you provide a dataset and target column, and AutoML does the rest.

- A is wrong: Designer is drag-and-drop visual ML but you still manually choose algorithms.
- C is wrong: Notebooks require writing code.
- D is wrong: Pipelines are for orchestrating ML workflows, not automatic algorithm selection.
</details>

---

### Question 11
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

## Domain 3: Computer Vision on Azure (Questions 12–17)

### Question 12
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

### Question 13
A company needs to digitize thousands of old printed documents by extracting the text content from scanned images. Which Azure service capability should they use?

- A) Azure AI Face
- B) Azure AI Vision — Image Analysis
- C) Azure AI Vision — OCR (Read API)
- D) Azure AI Language

<details>
<summary>Answer</summary>

**C) Azure AI Vision — OCR (Read API)**

The Read API in Azure AI Vision extracts printed and handwritten text from images and scanned documents. This is the OCR capability designed for text extraction.

- A is wrong: AI Face detects and analyzes faces.
- B is wrong: Image Analysis describes images and detects objects, not optimized for text extraction.
- D is wrong: AI Language analyzes text that's already in text format — it doesn't extract text from images.
</details>

---

### Question 14
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

### Question 15
A security company wants to verify that the person at a door matches a photo on their employee badge. Which Azure AI capability should they use?

- A) Azure AI Vision — Image Classification
- B) Azure AI Face — Face Verification
- C) Azure AI Face — Face Detection
- D) Azure AI Vision — Object Detection

<details>
<summary>Answer</summary>

**B) Azure AI Face — Face Verification**

Face verification compares two faces to determine if they are the same person (1:1 matching). This is exactly what's needed to compare a live face to a badge photo.

- A is wrong: Image classification labels entire images, not face comparison.
- C is wrong: Face detection only finds where faces are in an image — it doesn't compare them.
- D is wrong: Object detection identifies objects, not face identity.
</details>

---

### Question 16
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

### Question 17
You need to generate human-readable descriptions of images for a website's accessibility features (alt text). Which Azure AI capability should you use?

- A) Azure AI Vision — OCR
- B) Azure AI Vision — Image Captioning
- C) Azure AI Face
- D) Azure AI Language — Summarization

<details>
<summary>Answer</summary>

**B) Azure AI Vision — Image Captioning**

Image captioning generates natural language descriptions of images — exactly what's needed for alt text on websites.

- A is wrong: OCR extracts text FROM images, not describes images.
- C is wrong: AI Face analyzes faces, not general image content.
- D is wrong: AI Language summarizes text documents, not images.
</details>

---

## Domain 4: NLP on Azure (Questions 18–23)

### Question 18
A company wants to analyze customer reviews to determine the overall sentiment and also identify which specific aspects (food, service, ambiance) customers feel positive or negative about. Which Azure AI capability provides this?

- A) Key phrase extraction
- B) Entity recognition
- C) Sentiment analysis with opinion mining
- D) Text summarization

<details>
<summary>Answer</summary>

**C) Sentiment analysis with opinion mining**

Opinion mining (aspect-based sentiment analysis) identifies sentiments linked to specific aspects. "The food was great but the service was slow" → food: positive, service: negative.

- A is wrong: Key phrase extraction identifies important topics but not sentiment.
- B is wrong: Entity recognition identifies named entities, not sentiment.
- D is wrong: Summarization shortens text but doesn't analyze sentiment per aspect.
</details>

---

### Question 19
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

### Question 20
A multinational company needs to convert spoken Japanese in a meeting to spoken English in real time. Which Azure service should they use?

- A) Azure AI Translator
- B) Azure AI Language
- C) Azure AI Speech — Speech Translation
- D) Azure AI Speech — Speech-to-Text

<details>
<summary>Answer</summary>

**C) Azure AI Speech — Speech Translation**

Speech translation in Azure AI Speech converts spoken audio in one language to spoken audio in another language in real time. This is speech-to-speech translation.

- A is wrong: Azure AI Translator handles text translation, not spoken audio.
- B is wrong: AI Language processes text, not speech.
- D is wrong: Speech-to-Text converts audio to text in the same language — it doesn't translate.
</details>

---

### Question 21
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

### Question 22
An application needs to understand user voice commands like "turn on the living room lights" and "set thermostat to 72 degrees." It must identify the user's intent and extract relevant entities (room, device, temperature). Which feature should you use?

- A) Azure AI Language — Question Answering
- B) Azure AI Language — Conversational Language Understanding (CLU)
- C) Azure AI Speech — Speech-to-Text
- D) Azure AI Language — Key Phrase Extraction

<details>
<summary>Answer</summary>

**B) Azure AI Language — Conversational Language Understanding (CLU)**

CLU is designed to understand user intents (e.g., "TurnOn", "SetTemperature") and extract entities (e.g., room="living room", device="lights", temperature="72") from conversational input.

- A is wrong: Question Answering answers from a knowledge base, not understands intents/entities.
- C is wrong: Speech-to-Text converts audio to text but doesn't understand intents.
- D is wrong: Key phrase extraction finds important terms but doesn't identify intents or structured entities.
</details>

---

### Question 23
Which of the following is a pre-built capability of Azure AI Language that works immediately without any custom training data?

- A) Conversational language understanding (CLU)
- B) Custom text classification
- C) Question answering
- D) Sentiment analysis

<details>
<summary>Answer</summary>

**D) Sentiment analysis**

Sentiment analysis is a pre-built feature of Azure AI Language — it works out of the box with no training data needed. You send text, it returns sentiment scores.

- A is wrong: CLU requires custom training data to define intents and entities.
- B is wrong: Custom text classification requires training with your own labeled data.
- C is wrong: Question answering requires you to provide FAQ/document content as a knowledge base.
</details>

---

## Domain 5: Generative AI on Azure (Questions 24–33)

### Question 24
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

### Question 25
A developer is testing different prompts with a GPT model and wants to provide the model with 3 example input-output pairs to guide its responses. What is this prompt engineering technique called?

- A) Zero-shot learning
- B) Few-shot learning
- C) Fine-tuning
- D) Chain of thought

<details>
<summary>Answer</summary>

**B) Few-shot learning**

Few-shot learning is a prompt engineering technique where you include a few examples (typically 2–5) in the prompt to demonstrate the desired behavior to the model.

- A is wrong: Zero-shot means no examples are provided — just instructions.
- C is wrong: Fine-tuning involves additional training with data, not adding examples to prompts.
- D is wrong: Chain of thought asks the model to show its reasoning steps, not provide examples.
</details>

---

### Question 26
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

### Question 27
You are using Azure OpenAI to build a code generation tool. You want the model to produce consistent, deterministic output with minimal creativity. What temperature setting should you use?

- A) 0 (or close to 0)
- B) 0.5
- C) 0.8
- D) 1.0

<details>
<summary>Answer</summary>

**A) 0 (or close to 0)**

A temperature of 0 makes the model's output as deterministic as possible — it always picks the most likely next token. This is ideal for code generation where consistency and correctness matter more than creativity.

- B, C, D are wrong: Higher temperatures increase randomness and creativity, which is undesirable for code generation where you want reliable, consistent output.
</details>

---

### Question 28
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

### Question 29
Azure OpenAI Service includes built-in content filtering that blocks harmful content. Which four categories does the content filter evaluate?

- A) Violence, hate, sexual, self-harm
- B) Spam, phishing, malware, profanity
- C) Bias, privacy, copyright, misinformation
- D) Harassment, threats, discrimination, fraud

<details>
<summary>Answer</summary>

**A) Violence, hate, sexual, self-harm**

Azure OpenAI's built-in content filters evaluate content across four categories: violence, hate, sexual content, and self-harm — both in prompts (input) and completions (output).

- B is wrong: These are email/security categories, not Azure OpenAI content filter categories.
- C is wrong: These are Responsible AI concerns but not the specific content filter categories.
- D is wrong: These are general abuse categories, not the specific Azure OpenAI filter categories.
</details>

---

### Question 30
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

### Question 31
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
- C is wrong: Clustering is unsupervised and groups data — this scenario has labeled data and needs classification.
- D is wrong: Regression predicts numbers, not diagnostic categories.
</details>

---

### Question 32
A company wants to build a search feature where users type a natural language question and the system finds the most semantically similar documents — even if the exact words don't match. Which Azure OpenAI model type should they use?

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

### Question 33
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
