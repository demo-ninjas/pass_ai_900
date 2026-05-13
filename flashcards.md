# AI-900 Flashcards

> 146 Q&A flashcards across all 5 domains.
> **Instructions**: Cover the Answer column. Say your answer out loud. Then check.
> Star â­ any card you get wrong â€” review starred cards at the end of each session.

---

## Domain 1: AI Workloads and Considerations (Cards 1–25)

| # | Question | Answer |
|---|----------|--------|
| 1 | What are the 5 common AI workload types? | Computer Vision, NLP, Document Processing, Generative AI, Knowledge Mining |
| 2 | Which AI workload: "Detect defective parts on an assembly line from camera images"? | Computer Vision (object detection) |
| 3 | Which AI workload: "Determine if customer reviews are positive or negative"? | NLP (sentiment analysis) |
| 4 | Which AI workload: "Extract line items from scanned invoices"? | Document Processing |
| 5 | Which AI workload: "Generate marketing copy for a product"? | Generative AI |
| 6 | Which AI workload: "Search across thousands of PDF documents to find relevant information"? | Knowledge Mining |
| 7 | Which AI workload: "Convert a recorded meeting to text"? | NLP (speech recognition / speech-to-text) |
| 8 | Which AI workload: "Read handwritten text from a form"? | Document Processing (or Computer Vision â€” OCR) |
| 9 | Name all 6 Responsible AI principles. | Fairness, Reliability & Safety, Privacy & Security, Inclusiveness, Transparency, Accountability |
| 10 | Which Responsible AI principle: "The model produces biased results against a demographic group"? | Fairness |
| 11 | Which Responsible AI principle: "Users don't know they're interacting with an AI"? | Transparency |
| 12 | Which Responsible AI principle: "No human reviews or oversees the AI's decisions"? | Accountability |
| 13 | Which Responsible AI principle: "The AI system crashes under unexpected input"? | Reliability & Safety |
| 14 | Which Responsible AI principle: "User personal data is stored without consent"? | Privacy & Security |
| 15 | Which Responsible AI principle: "The AI voice assistant doesn't work for users with speech disabilities"? | Inclusiveness |
| 16 | Does Fairness mean treating everyone identically? | No. It means the model doesn't produce biased OUTCOMES for different groups. |
| 17 | Who is accountable for AI system decisions â€” the AI or people? | People. Humans must oversee AI and ensure governance. |
| 18 | Does Transparency mean open-sourcing the model? | No. It means users understand how the system makes decisions and its limitations. |
| 19 | What is the difference between Computer Vision and Document Processing? | CV analyzes images/video generally. Document Processing extracts STRUCTURED data from forms/invoices. |
| 20 | What is Knowledge Mining? | Extracting insights from large volumes of unstructured data â€” indexing and searching documents (e.g., Azure AI Search). |
| 21 | Name an Azure tool for Responsible AI assessment. | Responsible AI dashboard in Azure Machine Learning. |
| 22 | Which AI workload: "Identify the breed of a dog in a photo"? | Computer Vision (image classification) |
| 23 | Which AI workload: "Translate an email from Spanish to English"? | NLP (translation) |
| 24 | Which AI workload: "Create a new image from a text description"? | Generative AI (image generation) |
| 25 | Which AI workload: "Extract the vendor name and total from a receipt"? | Document Processing |

---

## Domain 2: Machine Learning on Azure (Cards 26–58)

| # | Question | Answer |
|---|----------|--------|
| 26 | What are the 3 core ML techniques for the exam? | Regression, Classification, Clustering |
| 27 | What does Regression predict? | A continuous NUMERIC value (how much, how many). |
| 28 | What does Classification predict? | A discrete CATEGORY (which one, yes/no). |
| 29 | What does Clustering do? | Groups similar data points together WITHOUT predefined labels. |
| 30 | Is Regression supervised or unsupervised? | Supervised (requires labeled data). |
| 31 | Is Classification supervised or unsupervised? | Supervised (requires labeled data). |
| 32 | Is Clustering supervised or unsupervised? | Unsupervised (no labels needed). |
| 33 | Scenario: "Predict the selling price of a house" â€” which ML technique? | Regression (predicting a number). |
| 34 | Scenario: "Predict whether a loan will default" â€” which ML technique? | Classification (binary: yes/no). |
| 35 | Scenario: "Group customers by similar purchasing behavior" â€” which ML technique? | Clustering (finding natural groups, no labels). |
| 36 | Scenario: "Predict how many units of a product will sell next month" â€” which technique? | Regression (predicting a number). |
| 37 | Scenario: "Determine whether an email is spam or not spam" â€” which technique? | Classification (binary). |
| 38 | Scenario: "Predict a student's test score" â€” which technique? | Regression (score is a number). |
| 39 | Scenario: "Predict whether a student will pass or fail" â€” which technique? | Classification (pass/fail = categories). |
| 40 | Scenario: "Segment website visitors into groups based on behavior" â€” technique? | Clustering (no predefined groups). |
| 41 | What is a FEATURE in machine learning? | An input variable used for prediction (e.g., square footage, age, income). |
| 42 | What is a LABEL in machine learning? | The output variable being predicted (e.g., price, spam/not-spam). |
| 43 | Does clustering use labels? | No. Clustering is unsupervised â€” it uses only features. |
| 44 | What is the TRAINING dataset used for? | Teaching the model â€” it learns patterns from this data. |
| 45 | What is the VALIDATION dataset used for? | Tuning the model during training and checking for overfitting. |
| 46 | What is the TEST dataset used for? | Evaluating the final model on completely unseen data. |
| 47 | What is OVERFITTING? | Model memorizes training data but performs poorly on new data. |
| 48 | What is UNDERFITTING? | Model is too simple to capture patterns â€” poor performance on all data. |
| 49 | What is Deep Learning? | A subset of ML using artificial neural networks with multiple layers. Excels at unstructured data (images, text, audio). |
| 50 | Deep learning vs traditional ML: which needs more data and compute? | Deep learning requires MORE data and MORE compute. |
| 51 | What is the Transformer architecture? | Architecture using self-attention to process all input simultaneously. Foundation of LLMs (GPT, BERT). |
| 52 | What does GPT stand for? | Generative Pre-trained Transformer. |
| 53 | What is Automated ML (AutoML)? | Azure ML feature that automatically tries multiple algorithms and hyperparameters to find the best model. No coding needed. |
| 54 | What 3 task types does AutoML support? | Classification, Regression, Time-series forecasting. |
| 55 | What is Azure ML Designer? | Drag-and-drop visual interface for building ML pipelines without code. |
| 56 | What data and compute services does Azure ML provide? | Datastores (Blob, Data Lake, SQL connections), data assets (versioned references), compute instances (dev), compute clusters (scalable training), serverless compute (on-demand). |
| 57 | What is the Azure ML model registry? | Central repo to register, version, and track trained models. Supports model lineage, tagging, and staging before deployment. |
| 58 | How do you deploy models in Azure Machine Learning? | Managed online endpoints (real-time REST APIs, autoscaling, blue/green), batch endpoints (large-scale offline inference), or deploy to Kubernetes. |

---

## Domain 3: Computer Vision on Azure (Cards 59–83)

| # | Question | Answer |
|---|----------|--------|
| 59 | What are the 4 computer vision task types on the exam? | Image Classification, Object Detection, OCR, Facial Detection/Analysis. |
| 60 | What does Image Classification do? | Assigns a category label to an ENTIRE image ("this is a cat"). |
| 61 | What does Object Detection do? | Identifies objects AND their LOCATIONS (bounding boxes) in an image. |
| 62 | What does OCR do? | Extracts printed or handwritten text from images. |
| 63 | What does Facial Detection do? | Detects face LOCATIONS in images; can analyze attributes (glasses, head pose). |
| 64 | Key difference: Image Classification vs Object Detection? | Classification = one label for whole image. Object Detection = multiple objects + WHERE each one is (bounding boxes). |
| 65 | Scenario: "Count the number of cars in a parking lot photo" â€” which CV task? | Object Detection (needs to find each car and its location). |
| 66 | Scenario: "Determine if a photo contains a cat or a dog" â€” which CV task? | Image Classification (one label for the whole image). |
| 67 | Scenario: "Read the text on a street sign" â€” which CV task? | OCR. |
| 68 | Scenario: "Determine if a person in a photo is wearing glasses" â€” which CV task? | Facial Detection/Analysis. |
| 69 | What are the 3 Azure services for computer vision? | Azure AI Vision, Azure AI Face, Azure AI Document Intelligence. |
| 70 | What does Azure AI Vision provide? | Image analysis, captions, tags, OCR (Read API), object detection, spatial analysis, smart cropping. |
| 71 | What does Azure AI Face provide? | Face detection, face attributes, face verification (1:1), face identification (1:many). |
| 72 | What does Azure AI Document Intelligence provide? | Extract structured data from documents: key-value pairs, tables, line items. Pre-built models for invoices, receipts, IDs. |
| 73 | OCR vs Document Intelligence: when to use which? | OCR = raw text extraction from any image. Document Intelligence = STRUCTURED field extraction from forms/invoices. |
| 74 | Face Verification vs Face Identification? | Verification = compare 2 faces, same person? (1:1). Identification = who is this person from a group? (1:many). |
| 75 | What facial capability did Microsoft RETIRE for Responsible AI? | Inferring emotional states from facial expressions. |
| 76 | Does Azure AI Face still detect if someone wears glasses? | Yes â€” attribute analysis (glasses, head pose, blur) is still available. |
| 77 | Does face identification require special approval? | Yes â€” requires Limited Access approval from Microsoft. |
| 78 | What is Image Captioning in Azure AI Vision? | Generates human-readable text descriptions of images (useful for alt text/accessibility). |
| 79 | What is Spatial Analysis in Azure AI Vision? | Analyzes people movement in video feeds â€” count people, detect proximity, track movement. |
| 80 | Scenario: "Generate alt-text for website images" â€” which service? | Azure AI Vision (Image Captioning). |
| 81 | Scenario: "Extract vendor name, date, total from scanned invoices" â€” which service? | Azure AI Document Intelligence. |
| 82 | Scenario: "Verify a user's identity by comparing selfie to badge photo" â€” service? | Azure AI Face (face verification, 1:1). |
| 83 | Scenario: "Count people entering a store from video" â€” which service? | Azure AI Vision (Spatial Analysis). |

---

## Domain 4: NLP on Azure (Cards 84–111)

| # | Question | Answer |
|---|----------|--------|
| 84 | What are the 7 NLP capabilities tested on the exam? | Key phrase extraction, entity recognition, sentiment analysis, language modeling, speech recognition, speech synthesis, translation. |
| 85 | What does Key Phrase Extraction do? | Identifies the main concepts/topics in text (returns a flat list of phrases). |
| 86 | What does Entity Recognition (NER) do? | Identifies and CATEGORIZES named entities (Person, Org, Location, Date) in text. |
| 87 | What does Sentiment Analysis do? | Determines emotional tone: positive, negative, neutral (per sentence and overall). |
| 88 | Key Phrase Extraction vs Entity Recognition? | Key phrases = important topics (no categories). NER = entities WITH categories (Person, Org, Location). |
| 89 | What is Opinion Mining? | Aspect-based sentiment: links sentiment to specific aspects ("food: positive, service: negative"). |
| 90 | What is Speech-to-Text (STT)? | Converts spoken audio into written text. |
| 91 | What is Text-to-Speech (TTS)? | Converts written text into spoken audio. |
| 92 | What is Speech Translation? | Translates spoken audio in one language to another language (speech-to-speech). |
| 93 | What is Azure AI Translator? | Translates WRITTEN text between languages (not audio). |
| 94 | "Translate a written document from French to English" â€” which service? | Azure AI Translator (text translation). |
| 95 | "Translate a live spoken conversation" â€” which service? | Azure AI Speech (speech translation). NOT Azure AI Translator. |
| 96 | What is Azure AI Language? | Service for text analytics: sentiment, key phrases, NER, entity linking, language detection, summarization, CLU, question answering. |
| 97 | What is Azure AI Speech? | Service for audio: STT, TTS, speech translation, speaker recognition, keyword recognition. |
| 98 | Name 6 pre-built features of Azure AI Language. | Sentiment analysis, key phrase extraction, NER, entity linking, language detection, text summarization. |
| 99 | Name 4 custom features of Azure AI Language. | Question Answering, CLU, custom text classification, custom entity recognition. |
| 100 | Pre-built vs Custom: which works without training data? | Pre-built features work immediately with no training data. |
| 101 | What is Question Answering in Azure AI Language? | Build a knowledge base from FAQs/documents â†’ answers user questions from that content. |
| 102 | What is CLU (Conversational Language Understanding)? | Train a model to understand user INTENTS and extract ENTITIES from conversational input. |
| 103 | Question Answering vs CLU? | QA = answers from a knowledge base. CLU = understands intents and entities in commands/conversation. |
| 104 | "Build a FAQ bot from company handbook" â€” which feature? | Question Answering. |
| 105 | "Understand 'book a flight to Paris on Friday'" â€” which feature? | CLU (intent: BookFlight, entities: destination=Paris, date=Friday). |
| 106 | "Analyze if product reviews are positive or negative" â€” service + feature? | Azure AI Language â€” Sentiment Analysis (pre-built). |
| 107 | "Detect what language an email is written in" â€” service + feature? | Azure AI Language â€” Language Detection (pre-built). |
| 108 | "Transcribe a call center recording" â€” service + feature? | Azure AI Speech â€” Speech-to-Text. |
| 109 | "Read articles aloud for visually impaired users" â€” service + feature? | Azure AI Speech â€” Text-to-Speech. |
| 110 | "Summarize a long support conversation" â€” service + feature? | Azure AI Language â€” Text Summarization (pre-built). |
| 111 | What is language modeling in NLP? | Predicting the next word/token in a sequence. Foundation for text generation, auto-complete, chatbots, and LLMs like GPT. |

---

## Domain 5: Generative AI on Azure (Cards 112–146)

| # | Question | Answer |
|---|----------|--------|
| 112 | What is Generative AI? | AI that creates NEW content (text, images, code, audio) â€” typically powered by Large Language Models (LLMs). |
| 113 | What are LLMs? | Large Language Models â€” AI models trained on massive text datasets that can understand and generate human language. |
| 114 | What architecture underpins modern LLMs? | Transformer architecture (self-attention mechanism, parallel processing). |
| 115 | What does the GPT model family generate? | Text, code, reasoning (natural language generation). |
| 116 | What does DALL-E generate? | Images from text descriptions. |
| 117 | What does Whisper do? | Speech-to-text (transcription). |
| 118 | What are Embeddings models? | Models that create vector (numeric) representations of text â€” used for similarity search. |
| 119 | What is a TOKEN in generative AI? | A unit of text (word or subword) that models process. |
| 120 | What is a PROMPT? | The input text you send to a generative AI model. |
| 121 | What is a COMPLETION? | The model's generated response to a prompt. |
| 122 | What does TEMPERATURE control? | Randomness/creativity. 0 = deterministic/focused. 1 = creative/random. |
| 123 | Temperature for code generation? | Low (0 to 0.3) â€” you want consistent, reliable output. |
| 124 | Temperature for creative writing? | High (0.7 to 1.0) â€” you want diverse, creative output. |
| 125 | What is a SYSTEM MESSAGE? | Instructions that set the model's behavior, persona, and constraints (e.g., "You are a helpful Azure support agent"). |
| 126 | What is ZERO-SHOT learning? | Giving the model instructions with NO examples in the prompt. |
| 127 | What is FEW-SHOT learning? | Giving the model a FEW examples (2â€“5) in the prompt to demonstrate desired behavior. |
| 128 | What is RAG (Retrieval-Augmented Generation)? | Retrieve relevant documents, include them in the prompt â€” grounds the model in real data to reduce hallucinations. |
| 129 | What is a HALLUCINATION in AI? | When a model generates confident but factually incorrect information. |
| 130 | Primary technique to reduce hallucinations? | RAG â€” ground responses in retrieved factual documents. |
| 131 | What is FINE-TUNING? | Additional training of a model on your specific data to customize its behavior. |
| 132 | System message vs Fine-tuning? | System message = quick behavioral rules at inference. Fine-tuning = deep customization through additional training. |
| 133 | What is Azure OpenAI Service? | Microsoft's managed service for deploying OpenAI models with enterprise security and compliance. |
| 134 | Azure OpenAI vs public OpenAI: data privacy? | Azure OpenAI: your data is NOT used for training. Public OpenAI: data may be used unless opted out. |
| 135 | Azure OpenAI vs public OpenAI: networking? | Azure OpenAI: supports private endpoints/VNets. Public OpenAI: public internet only. |
| 136 | What is Azure AI Foundry? | Unified portal for building AI apps: model catalog, playground, prompt flow, evaluation, deployment. |
| 137 | What is the Azure AI Foundry Model Catalog? | Browse and deploy models from multiple providers: OpenAI, Meta (Llama), Mistral, Microsoft (Phi), Hugging Face. |
| 138 | What are the 4 content filter categories in Azure OpenAI? | Violence, Hate, Sexual, Self-harm. |
| 139 | Are Azure OpenAI content filters applied to input, output, or both? | BOTH â€” prompts (input) AND completions (output) are filtered. |
| 140 | What are the 4 content filter severity levels in Azure OpenAI? | Safe, Low, Medium, High. |
| 141 | Can you disable Azure OpenAI content filters? | Only with Microsoft approval through a Limited Access application. |
| 142 | What is Chain of Thought prompting? | Ask the model to explain its reasoning step by step â€” improves accuracy on complex, multi-step tasks. |
| 143 | When should you use Embeddings models? | When you need semantic search, finding similar documents, or comparing text by meaning (not keyword matching). |
| 144 | Can you rename an Azure AI resource after creation? | No â€” resource name and region are immutable. You must delete and recreate. |
| 145 | How long does Azure OpenAI retain data for abuse monitoring? | 30 days by default. Can be reduced or removed with Microsoft approval. |
| 146 | GPT-4 vs GPT-4o: what's the key difference? | GPT-4o is optimized â€” faster and cheaper with similar capabilities. GPT-4o mini is the smallest/cheapest. |
