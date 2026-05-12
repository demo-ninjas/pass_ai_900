# Domain 4: Natural Language Processing (NLP) on Azure (15–20%)

---

## 4.1 Common NLP Workload Scenarios

### NLP Capabilities Overview

| Capability | What It Does | Example |
|-----------|-------------|---------|
| **Key Phrase Extraction** | Identifies the main concepts/topics in text | Input: "The food was delicious and the staff were friendly" → Key phrases: "food", "staff", "delicious", "friendly" |
| **Entity Recognition** | Identifies and categorizes entities (people, places, organizations, dates, quantities) in text | Input: "Microsoft was founded by Bill Gates in 1975" → Entities: Microsoft (Organization), Bill Gates (Person), 1975 (Date) |
| **Sentiment Analysis** | Determines the emotional tone of text (positive, negative, neutral, mixed) | Input: "The hotel was great but the food was terrible" → Sentence 1: positive, Sentence 2: negative, Overall: mixed |
| **Language Modeling** | Understanding and generating human language; foundation of NLP tasks | Conversational AI, question answering, text summarization |
| **Speech Recognition (STT)** | Converts spoken audio to text (Speech-to-Text) | Transcribe a meeting recording into text |
| **Speech Synthesis (TTS)** | Converts text to spoken audio (Text-to-Speech) | Read a news article aloud, voice for a virtual assistant |
| **Translation** | Translates text or speech between languages | Translate a support email from French to English |

### Key Phrase Extraction vs Entity Recognition — Critical Distinction

| Factor | Key Phrase Extraction | Entity Recognition |
|--------|----------------------|-------------------|
| What it finds | Important topics/concepts | Named entities (specific nouns with categories) |
| Categorizes results? | No (just a list of phrases) | Yes (Person, Organization, Location, Date, etc.) |
| Example input | "Azure AI provides powerful cloud-based services" | "Azure AI provides powerful cloud-based services" |
| Example output | ["Azure AI", "powerful cloud-based services"] | Azure AI (Product), cloud-based (Technology) |

### Sentiment Analysis Details
- Returns scores per sentence and overall:
  - **Positive** (0–1 score)
  - **Negative** (0–1 score)  
  - **Neutral** (0–1 score)
- **Opinion mining** (aspect-based sentiment): Links sentiments to specific aspects
  - "The room was clean but the food was cold" → room: positive, food: negative
- Language: part of **Azure AI Language** service

### Speech Recognition & Synthesis

| Direction | Name | Azure Service |
|-----------|------|--------------|
| Audio → Text | Speech-to-Text (STT) / Speech Recognition | Azure AI Speech |
| Text → Audio | Text-to-Speech (TTS) / Speech Synthesis | Azure AI Speech |
| Audio (Language A) → Audio (Language B) | Speech Translation | Azure AI Speech |

### Translation Capabilities

| Type | What It Does | Azure Service |
|------|-------------|--------------|
| **Text Translation** | Translate text between languages | Azure AI Translator |
| **Document Translation** | Translate entire documents preserving formatting | Azure AI Translator |
| **Speech Translation** | Real-time speech-to-speech translation | Azure AI Speech (speech translation feature) |
| **Custom Translation** | Train translation models with your own terminology | Azure AI Translator (Custom Translator) |

---

## 4.2 Azure NLP Services

### Azure AI Language Service
- Unified service for text analytics and language understanding
- Provides **pre-built** features (no training needed) and **custom** features (train with your data):

| Feature | Type | Description |
|---------|------|-------------|
| **Sentiment analysis** | Pre-built | Detect positive/negative/neutral sentiment |
| **Key phrase extraction** | Pre-built | Extract main concepts from text |
| **Entity recognition (NER)** | Pre-built | Identify named entities (people, places, orgs, dates) |
| **Entity linking** | Pre-built | Link entities to Wikipedia articles for disambiguation |
| **Language detection** | Pre-built | Detect the language of input text |
| **Text summarization** | Pre-built | Summarize documents or conversations |
| **Question answering** | Custom | Build a knowledge base from FAQs, manuals → answer user questions |
| **Conversational language understanding (CLU)** | Custom | Train models to understand user intents and extract entities from conversational input |
| **Custom text classification** | Custom | Classify text into your own custom categories |
| **Custom entity recognition** | Custom | Extract your own custom entity types |

### Azure AI Language: Pre-built vs Custom

| Pre-built (works immediately) | Custom (requires your training data) |
|-------------------------------|--------------------------------------|
| Sentiment analysis | Question answering |
| Key phrase extraction | Conversational language understanding |
| Entity recognition | Custom text classification |
| Language detection | Custom entity recognition |
| Text summarization | |
| Entity linking | |

### Azure AI Speech Service
- Handles all speech-related AI tasks:

| Capability | Description |
|-----------|-------------|
| **Speech-to-Text** | Transcribe audio to text. Supports real-time and batch transcription. |
| **Text-to-Speech** | Generate spoken audio from text. Supports neural voices for natural-sounding speech. |
| **Speech Translation** | Real-time translation of speech across languages |
| **Speaker Recognition** | Identify or verify speakers by their voice |
| **Keyword Recognition** | Detect specific keywords/wake words in audio (e.g., "Hey Cortana") |
| **Intent Recognition** | Detect the intent of spoken input (integrates with CLU) |
| **Custom Neural Voice** | Create a custom voice font for your brand (requires approval) |

### When to Use Which Service

| Scenario | Service | Feature |
|----------|---------|---------|
| "Analyze if product reviews are positive or negative" | Azure AI Language | Sentiment analysis |
| "Extract company names from news articles" | Azure AI Language | Entity recognition |
| "Build a FAQ bot for a website" | Azure AI Language | Question answering |
| "Transcribe a call center recording" | Azure AI Speech | Speech-to-Text |
| "Read articles aloud for visually impaired users" | Azure AI Speech | Text-to-Speech |
| "Translate a document from Japanese to English" | Azure AI Translator | Text translation |
| "Understand user commands like 'turn on the lights'" | Azure AI Language | Conversational language understanding (CLU) |
| "Detect what language an email is written in" | Azure AI Language | Language detection |
| "Translate a live meeting across languages in real time" | Azure AI Speech | Speech translation |
| "Summarize a long support conversation" | Azure AI Language | Text summarization |

---

## Numbers to Remember

| Fact | Value |
|------|-------|
| NLP capabilities tested on exam | 7 (key phrase extraction, entity recognition, sentiment analysis, language modeling, speech recognition, speech synthesis, translation) |
| Azure AI Language: pre-built features | 6 (sentiment, key phrases, NER, entity linking, language detection, summarization) |
| Azure AI Language: custom features | 4 (question answering, CLU, custom classification, custom NER) |
| Sentiment analysis outputs | 3 (positive, negative, neutral) per sentence + overall |
| Azure AI Speech capabilities | 6 (STT, TTS, speech translation, speaker recognition, keyword recognition, intent recognition) |

---

## Key Decision Tables

### NLP Task → Azure Service

| Task | → Service |
|------|----------|
| Text analysis (sentiment, entities, key phrases) | Azure AI Language |
| Speech-to-text, text-to-speech | Azure AI Speech |
| Text translation, document translation | Azure AI Translator |
| Custom intent/entity understanding | Azure AI Language (CLU) |
| Build a knowledge base / FAQ bot | Azure AI Language (Question Answering) |
| Real-time speech translation | Azure AI Speech |

### Azure AI Language: Pre-built vs Custom Decision

| If you need to... | → Type |
|-------------------|--------|
| Analyze text with no training | Pre-built |
| Understand specific intents in your app | Custom (CLU) |
| Answer questions from your own documents | Custom (Question Answering) |
| Classify text into your own categories | Custom (Custom Text Classification) |
| Detect sentiment/key phrases/entities immediately | Pre-built |

### "Sounds the Same" Confusions

| Service A | Service B | How They Differ |
|-----------|-----------|----------------|
| Azure AI Language | Azure AI Speech | Language = text analysis. Speech = audio processing. |
| Entity Recognition | Key Phrase Extraction | NER categorizes entities (Person, Org). Key phrases are just important terms. |
| Question Answering | Conversational Language Understanding | QA = answers from a knowledge base. CLU = understands intents and entities in conversation. |
| Speech Translation | Azure AI Translator | Speech translation = spoken audio. Translator = written text. |
| Language Detection | Translation | Detection tells you WHAT language. Translation converts BETWEEN languages. |
