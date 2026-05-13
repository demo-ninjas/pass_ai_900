# AI-900: Microsoft Azure AI Fundamentals — Exam Prep

> Interactive study app and comprehensive materials for passing the AI-900 certification exam.

## [**Launch the Study App →**](https://demo-ninjas.github.io/pass_ai_900/)

| Feature | What it does | Count |
|---------|-------------|-------|
| **Flashcards** | Click-to-flip cards with Got it / Again tracking, starred review mode | 146 cards |
| **Quiz** | Scenario-based MCQs with instant feedback, explanations, score history | 81 questions |
| **Mind Maps** | Interactive topic trees per domain (powered by markmap) | 5 maps |
| **Progress** | Mastery bars per domain, streak counter, quiz history | localStorage |
| **Cheat Sheets** | Collapsible reference tables with decision guides | 12 sections |

Just open `index.html` in any browser — works offline, no install needed.

---

## Exam Overview

| Detail | Value |
|--------|-------|
| **Exam** | AI-900: Microsoft Azure AI Fundamentals |
| **Certification** | Microsoft Certified: Azure AI Fundamentals |
| **Level** | Beginner |
| **Duration** | 45 minutes |
| **Passing Score** | 700 / 1000 |
| **Cost** | $99 USD |
| **Languages** | English, Japanese, Chinese (Simplified), Korean, German, French, Spanish, Portuguese (Brazil), Russian, Indonesian, Arabic, Chinese (Traditional), Italian |
| **Skills measured as of** | May 2, 2025 |
| **Retirement date** | June 30, 2026 (replaced by AI-901) |

> **Note**: AI-900 retires June 30, 2026 and will be replaced by AI-901. Take AI-900 before then or plan for AI-901.

## Exam Domains & Weights

| # | Domain | Weight |
|---|--------|--------|
| 1 | Describe Artificial Intelligence workloads and considerations | 15–20% |
| 2 | Describe fundamental principles of machine learning on Azure | 15–20% |
| 3 | Describe features of computer vision workloads on Azure | 15–20% |
| 4 | Describe features of Natural Language Processing (NLP) workloads on Azure | 15–20% |
| 5 | Describe features of generative AI workloads on Azure | 20–25% |

## Key Links

- [Official Exam Page](https://learn.microsoft.com/en-us/credentials/certifications/exams/ai-900/)
- [Study Guide (Skills Measured)](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-900)
- [Certification Overview](https://learn.microsoft.com/en-us/credentials/certifications/azure-ai-fundamentals/)
- [Free Practice Assessment](https://learn.microsoft.com/credentials/certifications/exams/ai-900/practice/assessment?assessment-type=practice&assessmentId=26)
- [Schedule Exam (Pearson Vue)](https://learn.microsoft.com/en-us/credentials/certifications/schedule-through-pearson-vue?examUid=exam.AI-900)

### MS Learn Training Paths

| Path | Modules |
|------|---------|
| [AI concepts for developers and technology professionals](https://learn.microsoft.com/en-us/training/paths/ai-concepts/) | 6 |
| [Get started with AI applications and agents on Azure](https://learn.microsoft.com/en-us/training/paths/get-started-ai-apps-agents/) | 6 |

## Repository Contents

| File | Description |
|------|-------------|
| `README.md` | This file — exam overview and links |
| `study-guide.md` | Every exam objective with MS Learn module links |
| `study-tracker.md` | Day-by-day cram plan (READ → DRILL → RECALL) |
| `practice-questions.md` | 81 scenario-based multiple choice questions |
| `flashcards.md` | 146 Q&A flashcards across all 5 domains |
| `traps-and-distinctions.md` | Tricky confusions, parameter traps, and "why NOT the other answer" scenarios |
| `index.html` | Interactive study app (flashcards, quiz, mind maps, progress, cheat sheets) |
| `cheat-sheets/1-ai-workloads-and-considerations.md` | Domain 1 cheat sheet |
| `cheat-sheets/2-machine-learning-on-azure.md` | Domain 2 cheat sheet |
| `cheat-sheets/3-computer-vision-on-azure.md` | Domain 3 cheat sheet |
| `cheat-sheets/4-nlp-on-azure.md` | Domain 4 cheat sheet |
| `cheat-sheets/5-generative-ai-on-azure.md` | Domain 5 cheat sheet |

## Content Counts

| Content Type | Count | Details |
|-------------|-------|----------|
| Flashcards | 146 | D1: 25, D2: 33, D3: 25, D4: 28, D5: 35 |
| Practice Questions | 81 | D1: 15, D2: 15, D3: 14, D4: 14, D5: 23 |
| Cheat Sheets | 5 | One per domain (12 sections in app) |
| Mind Maps | 5 | One interactive map per domain |
| Traps & Distinctions | 7 sections | Service confusions, ML traps, CV traps, GenAI traps, Responsible AI traps, lifecycle traps, number traps |
| Study Tracker Days | 7 |

## How to Study

1. **Day 1**: AI concepts + Responsible AI (Domain 1)
2. **Day 2**: Machine Learning fundamentals + Azure ML (Domain 2)
3. **Day 3**: Computer Vision on Azure (Domain 3)
4. **Day 4**: NLP on Azure (Domain 4)
5. **Day 5**: Generative AI + Azure OpenAI + Azure AI Foundry (Domain 5)
6. **Day 6**: Full review, weak areas, practice exam
7. **Day 7**: Quick review + exam

Each day follows **READ → DRILL → RECALL**:
- **READ**: Study the cheat sheet + complete the linked MS Learn modules
- **DRILL**: Open `index.html` → Flashcards tab → filter to that day's domain → then Quiz tab
- **RECALL**: Close everything, write down what you remember, check gaps

See `study-tracker.md` for the detailed day-by-day plan.

## Repository Structure

```
ai900/
├── index.html                          ← Interactive study app (open in browser)
├── README.md                           ← This file
├── study-guide.md                      ← Exam objectives + MS Learn links
├── study-tracker.md                    ← 7-day cram plan
├── practice-questions.md               ← 33 scenario-based questions
├── flashcards.md                       ← 142 Q&A flashcards
├── traps-and-distinctions.md           ← Common exam traps
├── exam-prep-implementation-plan.md    ← Build plan for this repo
└── cheat-sheets/
    ├── 1-ai-workloads-and-considerations.md
    ├── 2-machine-learning-on-azure.md
    ├── 3-computer-vision-on-azure.md
    ├── 4-nlp-on-azure.md
    └── 5-generative-ai-on-azure.md
```

## Contributing

PRs welcome. If you find a factual error, outdated service name, or want to add questions, open an issue or submit a PR.
