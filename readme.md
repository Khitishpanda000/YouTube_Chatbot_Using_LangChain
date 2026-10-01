# YouTube Transcript RAG (Retrieval-Augmented Generation) Chain

A semantic search and question-answering pipeline that builds a **Retrieval-Augmented Generation (RAG) chain** over YouTube video transcripts. The project utilizes **LangChain** to orchestrate the pipeline, **FAISS** for vector index tracking, and a hosted **Llama-3.1-8B-Instruct** model via Hugging Face Endpoints to guarantee context-constrained answers.

## Core Features
* **Transcript Extraction**: Automates text capture directly from targeted YouTube video IDs.
* **Semantic Indexing**: Fragments extensive continuous text transcripts into overlapping data chunks using recursive character rules.
* **Vector Store Storage**: Creates and stores sentence embeddings locally using the lightweight `all-MiniLM-L6-v2` transformer model.
* **LCEL Pipeline implementation**: Chains data streaming together using LangChain Expression Language (LCEL) constructs (`RunnableParallel`, `RunnablePassthrough`).

## Tech Stack & Dependencies
* **Orchestration**: `langchain`, `langchain-community`, `langchain-core`
* **Embeddings & LLM**: `langchain-huggingface`, `sentence-transformers`
* **Vector Index**: `faiss-cpu`
* **Data Extraction**: `youtube-transcript-api`

## 📋 Installation & Environment Setup

1. **Install dependencies**:
   ```bash
   pip install youtube-transcript-api langchain-text-splitters langchain-community langchain-huggingface faiss-cpu python-dotenv
   ```

2. **Configure Environment Tokens**:
   Ensure you export your Hugging Face Hub token to access the hosted Llama endpoint:
   ```python
   import os
   os.environ["HUGGINGFACEHUB_API_TOKEN"] = "your_huggingface_api_token"
   ```

## ⚙️ RAG Architecture Workflow

