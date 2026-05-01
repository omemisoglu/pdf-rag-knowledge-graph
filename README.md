# 📄 PDF to Knowledge Graph Extractor

> **Free LLM-powered information extraction from academic papers using Google Gemini**


## 🙏 Acknowledgements & Inspiration

This project is inspired by and builds upon the excellent work in the LLM and Knowledge Graph community.

### Original Reference & Evolution

This project evolved from the **Structured RAG** implementation by [thu-vu92](https://github.com/thu-vu92). The original repository provided a foundational approach to:
- PDF document loading and chunking with LangChain
- Vector database creation using Chroma
- Basic RAG pipeline implementation

**Original Source:** [thu-vu92/structured-rag-pdf/data_extraction_llms.ipynb](https://github.com/thu-vu92/structured-rag-pdf/blob/main/data_extraction_llms.ipynb)

### Key Differences & Extensions in This Project

| Aspect | Original (thu-vu92) | This Project |
|--------|---------------------|--------------|
| **LLM Provider** | OpenAI GPT-4o-mini (paid) | Google Gemini (free) |
| **Embeddings** | OpenAI `text-embedding-ada-002` | Google `gemini-embedding-001` |
| **Output Format** | Basic text responses | Structured Pydantic models |
| **Knowledge Graph** | Not included | Subject-Predicate-Object triplet extraction |
| **Cost** | Requires API credits | **100% free** |

### What I Added / Changed

1. **Switched to Google Gemini** - Making it accessible with free tier
2. **Triplet extraction** - Converting text to knowledge graph format


## 🎯 What does this project do?

This notebook extracts **structured knowledge** from PDF documents using:

- **Google Gemini** (free tier!) for LLM-powered extraction
- **RAG (Retrieval-Augmented Generation)** for semantic search
- **Structured output** with Pydantic models
- **Knowledge Graph triplets** (Subject-Predicate-Object)

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📥 **PDF Loading** | Load any academic PDF |
| 🔍 **Semantic Search** | ChromaDB with Gemini embeddings |
| 🧠 **Structured Extraction** | Title, authors, summary, year |
| 🔗 **Triplet Extraction** | Subject → Predicate → Object |
| 💰 **100% Free** | Uses Google Gemini (no OpenAI costs) |

## 🛠️ Tech Stack

- **LLM**: Google Gemini (`gemini-flash-latest`)
- **Embeddings**: `gemini-embedding-001`
- **Vector DB**: Chroma
- **Framework**: LangChain
- **Output**: Triplet Output in Console

## 🚀 Quick Start

### 1. Get a Google Gemini API Key

- Go to [Google AI Studio](https://aistudio.google.com/)
- Click "Get API Key"
- Copy your key

### 2. Setup

#### Open .ipynb file in Colab

#### Set up environment variables
Create file called ".env" at project directory and add your GOOGLE_API_KEY=[YOUR_KEY]

#### Switching Between LLMs
```python
# For Open AI (pay to use)
llm = ChatOpenAI(model="gpt-4o-mini", api_key=OPENAI_API_KEY)

# For Gemini (free with limited request rate)
llm = ChatGoogleGenerativeAI(model="gemini-flash-latest", api_key=GOOGLE_API_KEY)
```