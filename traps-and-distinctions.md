# AI-900 Traps and Distinctions

> The stuff that separates pass from fail. Every trap here is something the exam loves to test.
> Format: **Scenario → Correct Answer → Why NOT the other answer**

---

## 1. "Sounds the Same" Service Confusions

### Azure AI Vision vs Azure AI Face vs Azure AI Document Intelligence

| Service | What It Does | Key Distinguisher |
|---------|-------------|-------------------|
| **Azure AI Vision** | General image analysis: tags, captions, OCR, object detection, spatial analysis | Works on ANY image — not face-specific |
| **Azure AI Face** | Face detection, face attributes, face verification (1:1), face identification (1:many) | ONLY works on faces |
| **Azure AI Document Intelligence** | Extract structured data from documents (key-value pairs, tables, line items) | Returns STRUCTURED fields, not raw text |

**Trap**: "Extract text from a scanned document" → Azure AI Vision (OCR/Read API)
**Trap**: "Extract invoice line items into a database" → Azure AI Document Intelligence
**Trap**: "Determine if two photos show the same person" → Azure AI Face (verification)

### Azure AI Language vs Azure AI Speech vs Azure AI Translator

| Service | Input | Output | Key Distinguisher |
|---------|-------|--------|-------------------|
| **Azure AI Language** | Text | Text (analysis results) | Analyzes EXISTING text (sentiment, entities, key phrases) |
| **Azure AI Speech** | Audio ↔ Text | Text or Audio | Converts between audio and text |
| **Azure AI Translator** | Text | Text (different language) | Translates WRITTEN text between languages |

**Trap**: "Transcribe a meeting recording" → Azure AI Speech (STT), NOT Azure AI Language
**Trap**: "Translate a written document from French to English" → Azure AI Translator, NOT Azure AI Speech
**Trap**: "Translate a live spoken conversation" → Azure AI Speech (Speech Translation), NOT Azure AI Translator
**Trap**: "Determine if a review is positive" → Azure AI Language (Sentiment), NOT Azure AI Speech

### Key Phrase Extraction vs Entity Recognition

| Feature | Key Phrase Extraction | Entity Recognition (NER) |
|---------|----------------------|--------------------------|
| Returns | Important topics/concepts | Named entities with CATEGORIES |
| Categorizes? | **No** — just a flat list | **Yes** — Person, Org, Location, Date, etc. |
| Example output | ["cloud computing", "Azure services"] | "Microsoft" (Organization), "Seattle" (Location) |

**Trap**: "Identify all company names mentioned in an article" → Entity Recognition (NER), NOT key phrase extraction
**Trap**: "Find the main topics discussed in a document" → Key Phrase Extraction, NOT entity recognition

### Question Answering vs Conversational Language Understanding (CLU)

| Feature | Question Answering | CLU |
|---------|-------------------|-----|
| Purpose | Answer questions from a knowledge base (FAQs, manuals) | Understand user intents and extract entities from commands |
| Input | User question + knowledge base | User utterance + trained model |
| Output | Answer from the knowledge base | Intent + entities |
| Training | Provide FAQ documents/URLs | Define intents, entities, and example utterances |

**Trap**: "Build a bot that answers FAQs from your company handbook" → Question Answering
**Trap**: "Build a bot that understands commands like 'book a flight to Paris on Friday'" → CLU (intent: BookFlight, entities: destination=Paris, date=Friday)

### Azure OpenAI Service vs Azure AI Foundry

| Service | What It Is | Key Distinguisher |
|---------|-----------|-------------------|
| **Azure OpenAI Service** | Managed API for deploying OpenAI models (GPT, DALL-E, Whisper) | The MODEL hosting service |
| **Azure AI Foundry** | Unified PORTAL for building AI apps (model catalog, playground, prompt flow, evaluation) | The DEVELOPMENT platform |

**Trap**: "Deploy a GPT-4 model with private endpoint" → Azure OpenAI Service
**Trap**: "Browse models from OpenAI, Meta, and Mistral" → Azure AI Foundry Model Catalog
**Trap**: "Build a multi-step LLM pipeline" → Azure AI Foundry (Prompt Flow)

---

## 2. ML Technique Traps

### Regression vs Classification — The #1 Exam Trap

| If the answer is... | It's... | Example |
|--------------------|---------|---------|
| A **number** (how much, how many) | **Regression** | Predict price ($450,000), temperature (72°F), sales (1,500 units) |
| A **category** (which one, yes/no) | **Classification** | Spam or not spam, cat or dog, approve or deny |

**Trap**: "Predict the NUMBER of customers who will churn" → Regression (it's a number!)
**Trap**: "Predict WHETHER a customer will churn" → Classification (it's yes/no!)
**Trap**: "Predict a student's test SCORE" → Regression (numeric)
**Trap**: "Predict whether a student will PASS or FAIL" → Classification (category)

### Supervised vs Unsupervised

| Factor | Supervised | Unsupervised |
|--------|-----------|-------------|
| Has labels? | **Yes** | **No** |
| Techniques | Regression, Classification | Clustering |
| Goal | Predict a KNOWN outcome | Discover UNKNOWN patterns |

**Trap**: "We have historical data with known outcomes" → Supervised (regression or classification)
**Trap**: "We want to find natural groupings in data with no predefined categories" → Unsupervised (clustering)

### Features vs Labels

**Trap**: The exam will give you a dataset and ask "which column is the label?"
- **Label** = what you're trying to predict (the answer column)
- **Features** = everything else (the input columns)
- **Clustering has NO label** — it only uses features

### Training vs Validation vs Test Sets

**Trap**: "Which dataset is used to prevent overfitting during training?" → Validation set
**Trap**: "Which dataset evaluates the FINAL model on unseen data?" → Test set
**Trap**: "Which dataset does the model learn patterns from?" → Training set

---

## 3. Computer Vision Traps

### Image Classification vs Object Detection

**The distinction the exam LOVES**:
- **Classification**: "This image contains a dog" (one label for the whole image)
- **Object detection**: "There is a dog at (10,20,50,60) and a cat at (100,150,50,50)" (labels + bounding boxes)

**Trap**: "Identify WHAT is in an image" → Classification
**Trap**: "Identify what is in an image AND WHERE each object is located" → Object detection
**Trap**: "Count the number of cars in a parking lot image" → Object detection (needs to find each car individually)

### OCR vs Document Intelligence

**Trap**: "Read text from a photo of a street sign" → Azure AI Vision OCR (general text extraction)
**Trap**: "Extract vendor name, date, and total from a scanned invoice" → Azure AI Document Intelligence (structured extraction)

**Key rule**: If the output needs to be STRUCTURED (key-value pairs, table rows), use Document Intelligence. If you just need raw text, use OCR.

### Face Service Responsible AI Restrictions

**Trap**: "Can Azure AI Face detect emotions?" → **No** — Microsoft retired emotional state detection
**Trap**: "Can Azure AI Face detect if someone is wearing glasses?" → **Yes** — this is still available
**Trap**: "Can anyone use face identification?" → **No** — requires Limited Access approval

| Still Available | Retired / Restricted |
|----------------|---------------------|
| Face detection (bounding boxes) | Emotion detection |
| Face attributes (glasses, head pose, blur) | Face identification without approval |
| Face verification (1:1 with approval) | Age/gender estimation for minors |

---

## 4. Generative AI Traps

### Temperature Trap

**Trap**: "You want MORE creative output" → Higher temperature (closer to 1)
**Trap**: "You want MORE consistent/factual output" → Lower temperature (closer to 0)
**Trap**: "You want deterministic code generation" → Temperature = 0

**Do NOT confuse**: Temperature does NOT control quality — it controls randomness.

### Hallucination Traps

**Trap**: "Model generates confident but incorrect answers" → This is called a **hallucination**
**Trap**: "How to reduce hallucinations?" → **RAG** (Retrieval-Augmented Generation) — ground responses in real data
**Trap**: "Increase temperature to reduce hallucinations" → WRONG — lower temperature helps, but RAG is the primary solution

### Zero-Shot vs Few-Shot

**Trap**: "Provide examples in the prompt" → Few-shot
**Trap**: "Just give instructions, no examples" → Zero-shot
**These are prompt engineering techniques**, NOT model training techniques

### System Message vs Fine-Tuning

| Technique | What It Does | When to Use |
|-----------|-------------|-------------|
| **System message** | Sets behavior/persona at inference time | Quick behavioral constraints ("only answer about Azure") |
| **Fine-tuning** | Additional training on custom data | Deep domain knowledge, specialized vocabulary |

**Trap**: "Set the model to only answer Azure questions" → System message (not fine-tuning)
**Trap**: "Train the model to understand your company's proprietary terminology" → Fine-tuning (or RAG)

### Azure OpenAI Data Privacy

**Trap**: "Does Azure OpenAI use your data to train models?" → **No**. Your prompts/completions are NOT used for model training.
**Trap**: "Does public OpenAI use your data?" → It may, unless you opt out.
**Trap**: This is the #1 reason enterprises choose Azure OpenAI over public OpenAI.

### Content Filters

**Trap**: "What are the 4 content filter categories?" → Violence, Hate, Sexual, Self-harm
**Trap**: "Are content filters applied to input, output, or both?" → **Both** (prompts AND completions)
**Trap**: "Can you disable content filters?" → Only with Microsoft approval through a Limited Access application

---

## 5. Responsible AI Traps

### The 6 Principles — Exam Expects You to Match Scenarios

| Scenario on Exam | → Principle |
|-----------------|-----------|
| "Model gives different results for different ethnic groups" | **Fairness** |
| "AI system crashes under unexpected input" | **Reliability & Safety** |
| "User data is stored without consent" | **Privacy & Security** |
| "AI voice assistant doesn't support users with speech disabilities" | **Inclusiveness** |
| "Users don't know they're talking to an AI" | **Transparency** |
| "No human reviews the AI's decisions" | **Accountability** |

### Common Principle Confusions

**Trap**: Fairness ≠ "treating everyone identically." It means no biased outcomes against specific groups.
**Trap**: Accountability ≠ "the AI is accountable." HUMANS are accountable — AI is a tool.
**Trap**: Transparency ≠ "open-source the model." It means users understand how decisions are made and the system's limitations.
**Trap**: Privacy ≠ "don't collect data." It means data is protected, used appropriately, and users have control.

---

## 6. Lifecycle / Immutability Traps

| What | Immutable After Creation? | Notes |
|------|--------------------------|-------|
| Azure AI Service resource name | Yes | Cannot rename — must recreate |
| Azure AI Service region | Yes | Cannot move — must recreate |
| Azure OpenAI model deployment name | Yes | Cannot rename — must delete and redeploy |
| Content filter configuration | No | Can modify severity thresholds |
| System message | No | Can change anytime |
| Temperature/top-p settings | No | Can change anytime |
| Training data for custom models | No | Can retrain with new data |

---

## 7. Number Traps

| Fact | Wrong Answer That Sounds Right | Correct Answer |
|------|-------------------------------|----------------|
| Responsible AI principles | 5 (people forget one) | **6** (Fairness, Reliability & Safety, Privacy & Security, Inclusiveness, Transparency, Accountability) |
| Content filter categories | 3 | **4** (Violence, Hate, Sexual, Self-harm) |
| ML technique types tested | 2 (people forget clustering) | **3** (Regression, Classification, Clustering) |
| Temperature range | 0 to 100 | **0 to 1** (or 0 to 2 in some APIs) |
| Face verification matching | 1:many | **1:1** (face identification is 1:many) |
| Zero-shot examples | 1 | **0** (that's what "zero" means) |
