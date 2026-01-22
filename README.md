# Multimodal Retrieval-Augmented Generation (RAG) System
        
        A sophisticated Multimodal RAG pipeline designed to ingest, index, and query complex PDF documents containing both textual data and visual information (charts, graphs, and financial tables). This system utilizes advanced vision-language models and dual-embedding strategies to provide context-aware responses to both text and image-based queries.


# 🚀 Key Features
Multimodal Ingestion: Extracts text via standard parsing and interprets visual data (bar charts, plots) using OCR and CLIP/BLIP vision transformers.

## Dual-Encoder Pipeline:

### Text:
Sentence-BERT/OpenAI embeddings for semantic paragraph indexing.

### Visual:
CLIP-based embeddings to store image features in a unified vector space.

### Intelligent Retrieval: 
Hybrid similarity search that ranks both text and image chunks based on natural language queries or uploaded reference images.

### Advanced Prompt Engineering: 
Implements Chain-of-Thought (CoT), Few-shot, and Zero-shot prompting to enhance reasoning over financial and technical data.

### ChatGPT-like Interface:
A responsive Gradio/Web UI featuring text input, image uploads, and source-document referencing.


## ⚙️ Installation & Setup

### 1. Prerequisites
Hardware: NVIDIA T4 GPU (or better) is highly recommended for CLIP and LLM inference.

Environment: Python 3.10+ or Google Colab.

### 2. Dependencies
Bash
pip install -q langchain chromadb sentence-transformers pypdf \
    unstructured[pdf] openai clip-by-openai gradio


## 🛠️ Technical Workflow

### 1. Multimodal Preprocessing
The system parses PDFs to separate textual paragraphs from visual assets. Images such as financial bar charts are processed through a vision model to generate text-based captions and metadata, ensuring they are searchable via natural language.

### 2. Unified Vector Store
Extracted chunks are converted into dense embeddings and stored in ChromaDB. Each entry is tagged with metadata, allowing the system to return the exact page number and document name during retrieval.

### 3. Generation & Reasoning
When a query is received, the system retrieves the most relevant multimodal chunks. An LLM (e.g., Zephyr-7B or GPT-4) then synthesizes the answer using Chain-of-Thought prompting to explain the reasoning behind complex data interpretations (like comparing values across two different charts).    


## 📊 Evaluation & Metrics

The system performance is evaluated using the following quantitative metrics:

| Metric | Goal |
| :--- | :--- |
| **Retrieval Hit Rate** | Measure accuracy of top-$k$ relevant chunks. |
| **Cosine Similarity** | Quantify semantic alignment between query and context. |
| **BLEU / ROUGE** | Evaluate the linguistic quality of generated responses. |
| **Response Time** | Target < 3 seconds for real-time interaction. |


## 🎯 Conclusion

This project moves beyond standard text-only RAG by treating visual data as a first-class citizen. By combining vision transformers with high-fidelity language models, the system provides a comprehensive tool for analyzing data-rich documents, ensuring that no information—whether in a paragraph or a plot—is left behind.


## 🎓 Author

M Abdurrahman Khan National University of Computer and Emerging Sciences (FAST), Pakistan

Contact: {i221148}@nu.edu.pk
        
