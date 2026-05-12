# Domain 2: Fundamental Principles of Machine Learning on Azure (15–20%)

---

## 2.1 Common Machine Learning Techniques

### The Three Core ML Types

| Technique | What It Predicts | Output Type | Example |
|-----------|-----------------|-------------|---------|
| **Regression** | A **numeric value** (continuous) | Number | Predict house price, predict temperature, predict sales revenue |
| **Classification** | A **category/label** (discrete) | Category (True/False, or multi-class) | Is this email spam? (binary). What animal is this? (multi-class) |
| **Clustering** | **Group membership** (no labels) | Cluster assignment | Group customers by purchasing behavior, group news articles by topic |

### Critical Differences

| Factor | Regression | Classification | Clustering |
|--------|-----------|---------------|------------|
| Learns from | Labeled data (features + numeric label) | Labeled data (features + category label) | **Unlabeled data** (features only) |
| Learning type | Supervised | Supervised | **Unsupervised** |
| Output | Continuous number | Discrete category | Group/cluster ID |
| Question it answers | "How much?" / "How many?" | "Which category?" / "Is it X or Y?" | "What groups exist?" |

### When to Choose Each Technique

| Scenario | Technique | Why |
|----------|----------|-----|
| "Predict next month's sales revenue" | Regression | Predicting a numeric value |
| "Determine if a transaction is fraudulent" | Classification (binary) | Yes/no category |
| "Predict the price of a used car" | Regression | Predicting a numeric value |
| "Categorize support tickets by department" | Classification (multi-class) | Multiple categories |
| "Group customers with similar buying patterns" | Clustering | No predefined labels, finding natural groups |
| "Determine if an X-ray shows pneumonia" | Classification (binary) | Yes/no medical diagnosis |
| "Segment website visitors by behavior" | Clustering | Discover natural groups in data |
| "Predict how many units of a product will sell" | Regression | Predicting a continuous number |
| "Identify the species of a flower based on measurements" | Classification (multi-class) | Predefined species categories |

### Deep Learning
- Subset of machine learning using **artificial neural networks** with multiple layers
- Inspired by the structure of the human brain
- Excels at: image recognition, speech recognition, NLP, complex pattern recognition
- Requires **more data** and **more compute** than traditional ML
- Uses techniques like CNNs (Convolutional Neural Networks) for images, RNNs (Recurrent Neural Networks) for sequences

### Traditional ML vs Deep Learning

| Factor | Traditional ML | Deep Learning |
|--------|---------------|--------------|
| Data needed | Less | More (large datasets) |
| Compute needed | Less | More (GPUs/TPUs) |
| Feature engineering | Manual (you select features) | Automatic (learns features) |
| Interpretability | Higher (easier to explain) | Lower (black box) |
| Best for | Structured/tabular data | Unstructured data (images, text, audio) |

### Transformer Architecture
- Foundation architecture for modern AI language models (GPT, BERT, etc.)
- Uses **self-attention mechanism** — processes all parts of input simultaneously (not sequentially)
- Enables **parallelization** — much faster training than older architectures (RNNs)
- Powers: Large Language Models (LLMs), machine translation, text summarization, question answering
- GPT = **Generative Pre-trained Transformer**
- Key innovation: can understand **context** and **relationships** between all words in a text at once

---

## 2.2 Core Machine Learning Concepts

### Features and Labels

| Term | Definition | Example |
|------|-----------|---------|
| **Feature** | Input variable used for prediction (the data the model sees) | House: square footage, number of bedrooms, location, age |
| **Label** | Output variable being predicted (the answer) | House: sale price |

- Features = the **columns** in your training data (minus the label)
- Label = the **column** you're trying to predict
- **Clustering has no label** — it discovers structure in features alone

### Training and Validation Datasets

| Dataset | Purpose | When Used |
|---------|---------|-----------|
| **Training set** | Used to teach the model — the model learns patterns from this data | During model training |
| **Validation set** | Used to tune the model and check performance during training | During training (to prevent overfitting) |
| **Test set** | Used to evaluate final model performance on unseen data | After training is complete |

- **Overfitting**: Model memorizes training data but fails on new data (high training accuracy, low validation accuracy)
- **Underfitting**: Model is too simple to capture patterns (low accuracy on both training and validation)
- A good model performs well on **both** training and validation/test data

---

## 2.3 Azure Machine Learning Capabilities

### Azure Machine Learning (Azure ML)
- **Cloud-based platform** for building, training, deploying, and managing ML models
- Supports the **full ML lifecycle**: data prep → training → evaluation → deployment → monitoring

### Key Azure ML Capabilities

| Capability | Description |
|-----------|-------------|
| **Automated ML (AutoML)** | Automatically tries multiple algorithms and hyperparameters to find the best model. No coding required. |
| **Azure ML Designer** | Drag-and-drop visual interface for building ML pipelines. No code needed. |
| **Notebooks** | Jupyter notebooks for writing custom training code (Python/R) |
| **Data labeling** | Tools to label data for supervised learning projects |
| **MLflow integration** | Track experiments, log metrics, manage models |
| **Responsible AI dashboard** | Assess fairness, interpretability, error analysis of models |

### Automated ML (AutoML)
- You provide: a **dataset** and a **target column** (label)
- AutoML automatically: tries multiple algorithms, tunes hyperparameters, selects the best model
- Supports: classification, regression, and time-series forecasting
- **No coding required** — accessible through Azure ML Studio UI
- Perfect for: business users, data scientists who want a quick baseline, comparing algorithms

### Compute Services for Azure ML

| Compute Type | Purpose |
|-------------|---------|
| **Compute instance** | Development VM for notebooks and experiments |
| **Compute cluster** | Scalable cluster for training jobs |
| **Inference cluster** | For deploying models (AKS-based) |
| **Attached compute** | Connect your own compute (VMs, Databricks, etc.) |

### Model Deployment in Azure ML
- Deploy models as **web services** (REST endpoints)
- Deployment targets: **Azure Container Instances (ACI)** for testing, **Azure Kubernetes Service (AKS)** for production
- **Managed online endpoints**: Azure ML handles infrastructure
- **Batch endpoints**: For scoring large datasets on a schedule
- Model **registry**: Version and track models

---

## Numbers to Remember

| Fact | Value |
|------|-------|
| Core ML techniques | 3 (Regression, Classification, Clustering) |
| Supervised learning types | 2 (Regression, Classification) |
| Unsupervised learning types | 1 (Clustering) on the exam |
| AutoML supported tasks | 3 (Classification, Regression, Time-series forecasting) |
| ML dataset splits | 3 (Training, Validation, Test) |
| Typical training split | ~70-80% training, 10-15% validation, 10-15% test |

---

## Key Decision Tables

### Which ML Technique?

| If you need to predict... | → Technique |
|--------------------------|-----------|
| A number (price, temperature, count) | Regression |
| A category (yes/no, type A/B/C) | Classification |
| Natural groupings in data (no labels) | Clustering |

### Azure ML: Which Tool?

| If you want to... | → Use |
|-------------------|------|
| Build ML with no code | Automated ML (AutoML) |
| Build ML visually with drag-and-drop | Azure ML Designer |
| Write custom Python/R training code | Notebooks |
| Quickly find the best algorithm | AutoML |
| Deploy a model for real-time scoring | Managed online endpoint |
| Score large datasets in batch | Batch endpoint |

### Supervised vs Unsupervised

| Factor | Supervised | Unsupervised |
|--------|-----------|-------------|
| Has labeled data? | Yes | No |
| Techniques | Regression, Classification | Clustering |
| Goal | Predict a known outcome | Discover hidden patterns |
| Example | "Predict if loan defaults" | "Group customers by behavior" |
