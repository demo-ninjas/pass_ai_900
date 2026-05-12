# Domain 5: Generative AI Workloads on Azure (20–25%)

> This is the **heaviest domain** on the exam. Know it well.

---

## 5.1 Features of Generative AI Solutions

### What is Generative AI?
- AI that can **create new content**: text, images, code, audio, video
- Based on **Large Language Models (LLMs)** trained on massive datasets
- Uses the **Transformer architecture** (self-attention mechanism)
- Generates content by predicting the next token (word/subword) in a sequence
- Output is **probabilistic** — not deterministic (same input can produce different outputs)

### Generative AI Models

| Model Family | What It Generates | Azure Service |
|-------------|------------------|--------------|
| **GPT** (Generative Pre-trained Transformer) | Text, code, reasoning | Azure OpenAI Service |
| **DALL-E** | Images from text descriptions | Azure OpenAI Service |
| **Whisper** | Text from audio (speech-to-text) | Azure OpenAI Service |
| **Embeddings models** | Vector representations of text (for search/similarity) | Azure OpenAI Service |

### GPT Model Versions (Know the Names)

| Model | Key Facts |
|-------|-----------|
| **GPT-3.5** | Good general-purpose model, lower cost |
| **GPT-4** | More capable, better reasoning, multimodal (can process images) |
| **GPT-4o** | Optimized version of GPT-4, faster and cheaper |
| **GPT-4o mini** | Smallest/cheapest GPT-4 class model |

### Common Generative AI Scenarios

| Scenario | Example |
|----------|---------|
| **Natural language generation** | Write emails, articles, product descriptions |
| **Code generation** | Generate Python code, explain code, debug code |
| **Image generation** | Create images from text descriptions (DALL-E) |
| **Summarization** | Summarize long documents or conversations |
| **Conversational AI** | Chatbots and virtual assistants |
| **Information extraction** | Extract structured data from unstructured text |
| **Translation** | Translate between languages |
| **Reasoning** | Multi-step problem solving, analysis |

### Responsible AI for Generative AI

| Concern | Mitigation |
|---------|-----------|
| **Harmful content generation** | Content filters (built into Azure OpenAI) that block violence, hate, sexual, self-harm content |
| **Hallucinations** (confident but wrong answers) | **Grounding** — connect the model to real data sources (RAG pattern) |
| **Bias in outputs** | Evaluate model outputs across diverse inputs; use system messages to set guidelines |
| **Data privacy** | Azure OpenAI does NOT use your data to train models. Data stays within your Azure tenant. |
| **Transparency** | Disclose to users when they're interacting with AI |
| **Misuse** | Rate limiting, abuse monitoring, usage policies |

### Key Generative AI Concepts

| Concept | Definition |
|---------|-----------|
| **Token** | A unit of text (word or subword). Models process and generate tokens. |
| **Prompt** | The input text you send to the model |
| **Completion** | The model's generated response |
| **Temperature** | Controls randomness: 0 = deterministic/focused, 1 = creative/random |
| **Top-p** | Controls diversity of output (nucleus sampling) |
| **Max tokens** | Limits the length of the model's response |
| **System message** | Instructions that set the model's behavior/persona (e.g., "You are a helpful assistant") |
| **Few-shot learning** | Including examples in the prompt to guide the model |
| **Zero-shot** | No examples provided — just the instruction |
| **Grounding** | Connecting the model to factual data to reduce hallucinations |
| **RAG (Retrieval-Augmented Generation)** | Retrieve relevant documents, then include them in the prompt for the model to reference |
| **Fine-tuning** | Additional training on your specific data to customize the model |
| **Embeddings** | Vector (numeric) representations of text — used for similarity search |

### Prompt Engineering Techniques

| Technique | Description | Example |
|-----------|-------------|---------|
| **System message** | Set the model's role and constraints | "You are a helpful Azure support agent. Only answer Azure-related questions." |
| **Few-shot examples** | Provide examples in the prompt | "Translate: Hello → Hola, Goodbye → Adiós, Thank you → " |
| **Chain of thought** | Ask the model to explain its reasoning step by step | "Solve this problem. Show your reasoning step by step." |
| **Temperature control** | Low temp for factual, high temp for creative | Temperature 0 for code, 0.7 for creative writing |
| **Clear instructions** | Be specific about format, length, style | "Summarize in 3 bullet points, maximum 20 words each" |

---

## 5.2 Generative AI Services in Azure

### Azure OpenAI Service
- Microsoft's managed service for OpenAI models
- **Key difference from public OpenAI**: Enterprise security, compliance, private networking, your data is NOT used to train models

| Feature | Description |
|---------|-------------|
| **Models available** | GPT-4o, GPT-4o mini, GPT-4, GPT-3.5, DALL-E, Whisper, Embeddings |
| **Deployment** | Deploy models to your own Azure resource |
| **Content filtering** | Built-in filters for harmful content (violence, hate, sexual, self-harm) |
| **Data privacy** | Your prompts and completions are NOT used to train OpenAI models |
| **Networking** | Supports private endpoints and VNets |
| **RBAC** | Role-based access control for who can use the service |
| **Monitoring** | Azure Monitor integration for usage tracking |
| **Playground** | Interactive testing environment in Azure AI Foundry |

### Azure OpenAI vs Public OpenAI

| Factor | Azure OpenAI | Public OpenAI (openai.com) |
|--------|-------------|---------------------------|
| Data privacy | Your data is NOT used for training. Stays in your tenant. | Data may be used to improve models (unless opted out) |
| Compliance | Enterprise compliance (SOC 2, HIPAA, GDPR, etc.) | Limited enterprise compliance |
| Networking | Private endpoints, VNets | Public internet only |
| Content filtering | Built-in, configurable | Basic moderation API |
| SLA | Azure SLA | Best effort |
| Access control | Azure RBAC | API key only |
| For | Enterprises, regulated industries | Developers, startups, personal use |

### Azure AI Foundry (formerly Azure AI Studio)
- **Unified portal** for building, testing, and deploying AI applications
- Replaces the old Azure OpenAI Studio and Azure ML Studio experience
- Key capabilities:

| Capability | Description |
|-----------|-------------|
| **Model catalog** | Browse and deploy models from OpenAI, Meta (Llama), Mistral, Microsoft, Hugging Face, and more |
| **Prompt flow** | Visual tool for building LLM workflows (chains of prompts, tools, and data) |
| **Playground** | Test models interactively with different prompts and parameters |
| **Evaluation** | Measure model performance with built-in metrics |
| **Content safety** | Configure content filters and test them |
| **Fine-tuning** | Customize models with your data |
| **RAG (on your data)** | Connect models to your data sources (Azure AI Search, Blob Storage, etc.) |
| **Deployment** | Deploy models as endpoints for your applications |

### Azure AI Foundry Model Catalog
- Browse hundreds of models from multiple providers:
  - **OpenAI**: GPT-4o, GPT-4, GPT-3.5, DALL-E, Whisper
  - **Microsoft**: Phi models (small language models)
  - **Meta**: Llama models
  - **Mistral**: Mistral and Mixtral models
  - **Hugging Face**: Various open-source models
- Filter by: task type, license, provider, collection
- Deploy models directly from the catalog
- Compare model capabilities and pricing

### When to Use What

| Scenario | Service |
|----------|---------|
| "Deploy GPT-4 with enterprise security and compliance" | Azure OpenAI Service |
| "Browse and compare models from multiple providers" | Azure AI Foundry Model Catalog |
| "Build a RAG-based chatbot that answers from company documents" | Azure AI Foundry (with Azure AI Search + Azure OpenAI) |
| "Test different prompts and parameters interactively" | Azure AI Foundry Playground |
| "Create a multi-step AI workflow with prompts and tools" | Azure AI Foundry Prompt Flow |
| "Customize GPT to know your company's terminology" | Azure OpenAI (Fine-tuning) or RAG |
| "Generate images from text descriptions" | Azure OpenAI (DALL-E) |
| "Transcribe audio to text using AI" | Azure OpenAI (Whisper) or Azure AI Speech |

---

## Numbers to Remember

| Fact | Value |
|------|-------|
| Temperature range | 0 (deterministic) to 1 (max randomness) |
| Content filter categories | 4 (violence, hate, sexual, self-harm) |
| Content filter severity levels | 4 (safe, low, medium, high) |
| Azure OpenAI data retention for abuse monitoring | 30 days (can be reduced/removed with approval) |
| GPT stands for | Generative Pre-trained Transformer |
| LLM stands for | Large Language Model |
| RAG stands for | Retrieval-Augmented Generation |
| Prompt engineering: zero-shot | 0 examples in prompt |
| Prompt engineering: few-shot | 2–5 examples in prompt |

---

## Key Decision Tables

### "Which Generative AI Service?"

| Need | → Service |
|------|----------|
| Enterprise-grade GPT access | Azure OpenAI Service |
| Compare models from multiple providers | Azure AI Foundry Model Catalog |
| Build AI applications visually | Azure AI Foundry |
| Test prompts interactively | Azure AI Foundry Playground |
| Build multi-step LLM pipelines | Azure AI Foundry Prompt Flow |

### "How to Reduce Hallucinations?"

| Technique | How It Helps |
|-----------|-------------|
| RAG (Retrieval-Augmented Generation) | Grounds responses in real, retrieved documents |
| System message | Instructs model to only answer from provided data |
| Lower temperature | Makes output more deterministic and factual |
| Fine-tuning | Trains model on domain-specific accurate data |
| Content filters | Blocks harmful or inappropriate content |

### "Temperature Setting Decision"

| Use Case | Temperature |
|----------|-----------|
| Factual Q&A, code generation | Low (0 – 0.3) |
| General assistant | Medium (0.5 – 0.7) |
| Creative writing, brainstorming | High (0.7 – 1.0) |

### Public OpenAI vs Azure OpenAI Decision

| If you need... | → Choose |
|---------------|----------|
| Enterprise compliance (HIPAA, SOC 2) | Azure OpenAI |
| Private networking / VNet integration | Azure OpenAI |
| Guarantee data isn't used for training | Azure OpenAI |
| Quick prototyping, personal projects | Public OpenAI |
| Azure RBAC and identity management | Azure OpenAI |
