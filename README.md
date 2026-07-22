# Docuquery

<p align="center">
<img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge" />
  <img alt="Streamlit" src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge" />
  <img alt="LangChain" src="https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge" />
  <img alt="FAISS" src="https://img.shields.io/badge/FAISS-2B6CB0?style=for-the-badge" />
  <img alt="Hugging Face" src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge" />
  <img alt="NLP" src="https://img.shields.io/badge/NLP-4B5563?style=for-the-badge" />
</p>

<p align="center">
  <strong>A retrieval-augmented document question-answering system for extracting, indexing, and querying unstructured files.</strong>
</p>

Docuquery turns documents into an interactive knowledge base. It extracts text from PDFs and images, builds vector indexes, and presents a Streamlit interface where users can ask grounded questions over their own documents.

## Core Capabilities

- Extracts text from PDFs, images, and document inputs.
- Builds embedding-backed indexes for semantic retrieval.
- Answers user questions with context from indexed documents.
- Includes model download and extraction utilities for local setup.

## Technical Architecture

The application combines extraction utilities, embedding/indexing dependencies, and a Streamlit app. FAISS provides vector search while document loaders and OCR-related packages broaden input coverage.

## Architecture Diagram

```mermaid
%%{init: {"flowchart": {"nodeSpacing": 55, "rankSpacing": 70, "curve": "basis"}, "themeVariables": {"fontSize": "16px", "fontFamily": "Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, Segoe UI, sans-serif"}}}%%
flowchart TD
  Documents["PDFs, Images, and<br/>Documents"] --> Extractor["Text and OCR Extraction"]
  Extractor --> Chunks["Chunking and<br/>Preprocessing"]
  Chunks --> Embeddings["Embedding Generation"]
  Embeddings --> FAISS["FAISS Vector Index"]
  Question["User Question"] --> Retrieval["Semantic Retrieval"]
  FAISS --> Retrieval
  Retrieval --> Answer["Grounded Answer"]
  Answer --> Streamlit["Streamlit Interface"]

  classDef inputs fill:#FEF3C7,stroke:#D97706,color:#78350F,stroke-width:2.5px;
  classDef process fill:#DBEAFE,stroke:#2563EB,color:#1E3A8A,stroke-width:2.5px;
  classDef data fill:#DCFCE7,stroke:#16A34A,color:#14532D,stroke-width:2.5px;
  classDef agent fill:#F3E8FF,stroke:#9333EA,color:#581C87,stroke-width:2.5px;
  classDef output fill:#FFE4E6,stroke:#E11D48,color:#881337,stroke-width:2.5px;
  class Documents,Question inputs;
  class Extractor,Chunks,Embeddings,Retrieval,Streamlit process;
  class FAISS data;
  class Answer output;
  linkStyle default stroke:#64748B,stroke-width:2.5px;
```

## Technology Stack

- Streamlit for the interactive application.
- FAISS and sentence-transformer style embeddings for retrieval.
- LangChain components for retrieval workflows.
- PyMuPDF, pytesseract, pdf2image, and OpenCV for document extraction.
- Hugging Face tooling for local model assets.

## Repository Structure

- `app.py` - Streamlit application entry point.
- `extractor.py` - Document extraction utilities.
- `download_models.py` - Model asset setup helper.
- `requirements.txt` - Python dependencies.
- `image.png` - Project visual asset.
- `new.png` - Project visual asset.

## Getting Started

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

```bash
streamlit run app.py
```

## Professional Context

This project demonstrates retrieval-augmented application design, document processing, OCR workflows, and local knowledge-base interaction.
