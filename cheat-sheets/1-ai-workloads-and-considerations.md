# Domain 1: Describe AI Workloads and Considerations (15–20%)

---

## 1.1 Common AI Workloads

### AI Workload Types

| Workload | What It Does | Examples |
|----------|-------------|---------|
| **Computer Vision** | Interpret and analyze images/video | Image classification, object detection, facial recognition, OCR |
| **Natural Language Processing (NLP)** | Understand and generate human language | Sentiment analysis, key phrase extraction, translation, speech recognition |
| **Document Processing** | Extract information from documents | Form/receipt recognition, invoice processing, ID extraction |
| **Generative AI** | Create new content (text, images, code) | Chatbots, content creation, code generation, image generation |
| **Knowledge Mining** | Extract insights from large volumes of unstructured data | Azure AI Search (formerly Cognitive Search) — index and search documents |

### When to Choose Each Workload

| Scenario | Workload |
|----------|----------|
| "Detect defective products on a manufacturing line" | Computer Vision (object detection) |
| "Extract text from scanned invoices" | Document Processing (OCR) |
| "Determine if customer reviews are positive or negative" | NLP (sentiment analysis) |
| "Generate product descriptions automatically" | Generative AI |
| "Find specific topics across thousands of PDF documents" | Knowledge Mining |
| "Identify people in security camera footage" | Computer Vision (facial detection) |
| "Translate customer support emails to English" | NLP (translation) |
| "Create a chatbot to answer employee HR questions" | Generative AI (conversational) |
| "Read handwritten notes from a form" | Document Processing (OCR) |
| "Convert a spoken meeting recording to text" | NLP (speech-to-text) |

---

## 1.2 Responsible AI Principles

Microsoft's 6 guiding principles for Responsible AI:

| Principle | Description | Key Question |
|-----------|-------------|-------------|
| **Fairness** | AI systems should treat all people fairly. Avoid bias against groups based on gender, ethnicity, age, etc. | "Does this model give different quality results for different demographic groups?" |
| **Reliability & Safety** | AI systems should perform reliably and safely. They should work correctly under expected conditions and handle unexpected situations safely. | "What happens if the AI makes an error? Could it cause harm?" |
| **Privacy & Security** | AI systems should be secure and respect privacy. Data used for training and inference must be protected. | "Is personal data protected? Are there proper access controls?" |
| **Inclusiveness** | AI systems should empower everyone and engage all people. Designed to be accessible regardless of disability, language, or background. | "Can people with disabilities use this AI system effectively?" |
| **Transparency** | AI systems should be understandable. People should know how the AI works, its limitations, and when they're interacting with AI. | "Do users understand how decisions are made?" |
| **Accountability** | People should be accountable for AI systems. Humans must oversee AI and ensure governance frameworks are in place. | "Who is responsible when the AI makes a mistake?" |

### Responsible AI — Exam-Critical Facts

- **Fairness ≠ treating everyone identically** — it means ensuring the model doesn't produce biased outcomes for different groups
- **Transparency** includes explaining model decisions (interpretability/explainability)
- **Accountability** means humans are always in the loop — AI doesn't replace human oversight
- **Reliability & Safety** includes testing the AI under a wide range of conditions, including edge cases
- **All 6 principles apply to ALL AI workloads**, not just generative AI
- Microsoft provides tools: **Responsible AI dashboard** in Azure ML, **content filters** in Azure OpenAI

### Responsible AI Traps

| Trap | Correct Understanding |
|------|----------------------|
| "Fairness means the AI should give everyone the same answer" | Fairness means the AI should not produce biased outcomes against specific groups |
| "Transparency means open-sourcing the model" | Transparency means users understand how the system makes decisions and its limitations |
| "The AI system is accountable for its decisions" | PEOPLE are accountable — there must be human governance and oversight |
| "Privacy means not collecting any data" | Privacy means data is protected, used appropriately, and users have control |

---

## Numbers to Remember

| Fact | Value |
|------|-------|
| Responsible AI principles | 6 (Fairness, Reliability & Safety, Privacy & Security, Inclusiveness, Transparency, Accountability) |
| AI-900 passing score | 700 / 1000 |
| AI workload types tested | 5 (Computer Vision, NLP, Document Processing, Generative AI, Knowledge Mining) |

---

## Key Decision Tables

### "Which AI Workload?" Decision

| If the scenario involves... | → Workload |
|----------------------------|-----------|
| Images, video, cameras | Computer Vision |
| Text analysis, language understanding, speech | NLP |
| Extracting data from forms, receipts, invoices | Document Processing |
| Creating new content (text, images, code) | Generative AI |
| Searching/indexing large document sets | Knowledge Mining |

### Responsible AI Principle Matcher

| If the question mentions... | → Principle |
|----------------------------|-----------|
| Bias, demographic groups, equal treatment | Fairness |
| Errors, edge cases, safety, testing | Reliability & Safety |
| Data protection, personal data, GDPR | Privacy & Security |
| Accessibility, disabilities, all people | Inclusiveness |
| Explainability, understanding, disclosure | Transparency |
| Oversight, governance, human review | Accountability |
