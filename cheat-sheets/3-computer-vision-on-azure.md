# Domain 3: Computer Vision Workloads on Azure (15–20%)

---

## 3.1 Common Computer Vision Solution Types

### Four Key Computer Vision Tasks

| Task | What It Does | Output | Example |
|------|-------------|--------|---------|
| **Image Classification** | Assigns a **label/category** to an entire image | Single label (or probabilities) | "This image contains a cat" |
| **Object Detection** | Identifies objects AND their **locations** (bounding boxes) in an image | Objects + bounding box coordinates | "There is a car at position (x,y,w,h) and a person at position (x2,y2,w2,h2)" |
| **OCR (Optical Character Recognition)** | Extracts **printed or handwritten text** from images/documents | Text strings | Read text from a scanned receipt, extract text from a street sign |
| **Facial Detection & Analysis** | Detects **faces** in images and analyzes attributes | Face locations + attributes (age, emotion, glasses, etc.) | Detect faces in a photo, determine if person is wearing glasses |

### Image Classification vs Object Detection — Critical Distinction

| Factor | Image Classification | Object Detection |
|--------|---------------------|-----------------|
| Question it answers | "What IS this image?" | "What objects are IN this image and WHERE?" |
| Output | Category label + confidence score | Object labels + bounding boxes + confidence scores |
| Number of objects | Classifies the whole image (usually one label) | Can detect multiple objects per image |
| Location info | No | Yes (bounding box coordinates) |
| Use case | "Is this a cat or a dog?" | "Find all cats and dogs in this photo and mark where they are" |

### OCR Details
- Extracts **printed and handwritten text** from images
- Supports multiple languages
- Works on: photos, scanned documents, PDFs, images with embedded text
- **Azure AI Vision** provides OCR capabilities (Read API)
- **Azure AI Document Intelligence** (formerly Form Recognizer) provides specialized document processing:
  - Pre-built models for: invoices, receipts, business cards, ID documents, tax forms
  - Custom models for your specific document formats
  - Extracts structured data (key-value pairs, tables)

### OCR vs Document Intelligence

| Factor | Azure AI Vision (OCR/Read API) | Azure AI Document Intelligence |
|--------|-------------------------------|-------------------------------|
| Purpose | General text extraction from images | Structured data extraction from documents |
| Output | Raw text | Key-value pairs, tables, structured data |
| Best for | Photos with text, signs, screenshots | Invoices, receipts, forms, IDs |
| Pre-built models | No (general purpose) | Yes (invoices, receipts, IDs, etc.) |

### Facial Detection & Analysis
- **Detect faces**: Find face locations in an image (bounding boxes)
- **Analyze face attributes**: Age estimation, emotion, head pose, glasses, blur, exposure, noise, occlusion
- **Face verification**: Determine if two faces belong to the same person (1:1 matching)
- **Face identification**: Identify who a person is from a group (1:many matching)

### Responsible AI for Face Service

| Allowed | Restricted / Requires Approval |
|---------|-------------------------------|
| Face detection (location in image) | Face identification (who is this person?) |
| Face attribute analysis | Real-time facial recognition in surveillance |
| Face verification (is this the same person?) | Inferring emotional states |
| Blur, head pose, glasses detection | |

- Microsoft **retired** facial recognition capabilities that infer emotional states
- Face identification and verification against a group require an **application and approval** through a Limited Access policy
- This is a Responsible AI restriction — expect exam questions about this

---

## 3.2 Azure Services for Computer Vision

### Azure AI Vision Service
- Formerly known as **Computer Vision** (part of Azure Cognitive Services, now Azure AI Services)
- Provides:

| Capability | Description |
|-----------|-------------|
| **Image Analysis** | Describe images, detect objects, read text, generate tags, detect brands |
| **OCR (Read API)** | Extract printed and handwritten text from images and documents |
| **Spatial Analysis** | Analyze people movement in video feeds (count people, detect proximity) |
| **Image captioning** | Generate human-readable descriptions of images |
| **Dense captioning** | Generate captions for multiple regions of interest in an image |
| **Object detection** | Detect common objects with bounding boxes |
| **Smart cropping** | Automatically crop images to focus on the important subject |
| **Custom models** | Train custom image classification or object detection models |

### Azure AI Face Service
- Specialized service for **face detection and analysis**

| Capability | Description |
|-----------|-------------|
| **Face detection** | Detect faces and return bounding box coordinates |
| **Face attributes** | Return age, head pose, glasses, blur, exposure, noise, accessories, quality |
| **Face verification** | Compare two faces to determine if they are the same person (1:1) |
| **Face identification** | Identify a person from a known group of people (1:many) — requires approval |
| **Face grouping** | Group similar faces together |

### When to Use Which Service

| Scenario | Service |
|----------|---------|
| "Describe what's in a photo" | Azure AI Vision (Image Analysis) |
| "Read text from a scanned document" | Azure AI Vision (OCR / Read API) |
| "Extract invoice line items into structured data" | Azure AI Document Intelligence |
| "Detect if a person is wearing glasses" | Azure AI Face |
| "Verify a user's identity by comparing a selfie to their ID photo" | Azure AI Face (verification) |
| "Count people entering a building from a video feed" | Azure AI Vision (Spatial Analysis) |
| "Detect products on a retail shelf" | Azure AI Vision (Object Detection) or custom model |
| "Classify images of clothing by type" | Azure AI Vision (custom Image Classification) |
| "Generate alt-text for images on a website" | Azure AI Vision (Image Captioning) |

---

## Numbers to Remember

| Fact | Value |
|------|-------|
| Computer vision task types on exam | 4 (Image Classification, Object Detection, OCR, Facial Detection/Analysis) |
| Azure AI services for vision | 3 (AI Vision, AI Face, AI Document Intelligence) |
| Face attributes returned | Age, head pose, glasses, blur, exposure, noise, accessories, quality |
| Face verification | 1:1 comparison |
| Face identification | 1:many comparison (requires approval) |
| Emotional state detection | Retired by Microsoft (Responsible AI) |

---

## Key Decision Tables

### Computer Vision Task Decision

| If the scenario involves... | → Task |
|----------------------------|--------|
| "What category is this entire image?" | Image Classification |
| "What objects are in the image and where?" | Object Detection |
| "Extract text from an image or document" | OCR |
| "Detect or analyze human faces" | Facial Detection/Analysis |

### Azure Vision Service Decision

| If you need to... | → Service |
|-------------------|---------|
| General image analysis, tags, descriptions, OCR | Azure AI Vision |
| Face detection, verification, identification | Azure AI Face |
| Extract structured data from forms/invoices/receipts | Azure AI Document Intelligence |
| Build a custom image classifier | Azure AI Vision (Custom models) |
