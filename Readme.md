# AI-Assistant

**AI-Assistant** is an AI-native, generative assistant designed to deliver high-quality, context-aware responses through a modular, extensible framework. Built on Streamlit, LangChain, and Groq’s high-performance LLaMA backend, AI-Assistant combines web search, Retrieval-Augmented Generation (RAG), and conversation memory to power intelligent workflows for developers, researchers, and anyone working with custom data.


---

## Overview

AI-Assistant is not just another chatbot—it’s an adaptable blueprint for building AI-first applications that reason over diverse knowledge sources. Whether extracting insights from a PDF, parsing live websites, embedding GitHub repositories, or running real-time web search, AI-Assistant provides a unified pipeline that integrates file loaders, vector stores, embeddings, agent tools, and memory.

---

## Key Features

### 1. Web Search Agent

- Powered by LangChain’s SerpAPI integration and Groq’s LLaMA 4 backend.
- Execute live web searches to deliver timely, accurate responses beyond static context.

### 2. File-Based RAG

- Upload PDFs, text files, or supply live web URLs.
- Embedded using HuggingFace Transformers and indexed in FAISS.
- Query via ConversationalRetrievalChain for source-grounded answers.

### 3. GitHub Repository RAG

- Clone public GitHub repositories on the fly.
- Index repository files, embed using HuggingFace models, and enable semantic code/document Q&A.

### 4. Persistent Memory Embedding

- Chat with pre-embedded indexes through a dedicated RAG pipeline.

### 5. Contextual Memory

- Built-in conversation buffer memory with up to 10-message history.
- Maintains conversational context for follow-ups, clarifications, and iterative querying.

### 6. Multi-Mode Toggle

- Switch seamlessly between:
  - File-RAG: PDF, text file, or live URL.
  - Web Search Agent: real-time search using SerpAPI.
  - Direct LLM chat for general questions.

### 7. Modular, Extensible Architecture

- Each module (RAG, agent tools, loaders, memory) is isolated and independently configurable.
- Designed to enable rapid experimentation, easy integration of new vector stores, embedding models, or agent workflows.

---

## Tech Stack

| Component              | Technology                                  |
|------------------------|---------------------------------------------|
| App UI                 | Streamlit                                   |
| LLM Inference          | Groq (Meta LLaMA 4)                         |
| Framework              | LangChain                                   |
| Vector Store           | FAISS, Pinecone (persistent mode)           |
| Embeddings             | HuggingFace Transformers, Cohere            |
| Memory                 | ConversationBufferMemory                    |
| Web Search             | SerpAPI                                     |
| File Loaders           | LangChain Community Loaders, GitLoader      |
| Deployment             | Streamlit Cloud                             |

---

## Installation

```bash
git clone https://github.com/YOUR_USERNAME/AI-Assistant
cd AI-Assistant

# Optional: create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
````

---

## Environment Variables

Create a `.streamlit/secrets.toml` (for Streamlit Cloud) or a local `.env` file:

```toml
GROQ_API_KEY = "your_groq_api_key"
SERPAPI_API_KEY = "your_serpapi_api_key"
```

---

## Running the App

```bash
streamlit run app_2.py
```

Access the app at `http://localhost:8501` or use your Streamlit Cloud deployment URL.

---

## Roadmap & Vision
AI-Assistant’s mission is to evolve into a fully autonomous, memory-aware, multi-agent AI development framework that adapts intelligently to diverse workflows and data sources. The next phases will focus on a multi-pronged expansion of its capabilities:

**LangGraph Orchestration**
Leverage LangGraph to enable fine-grained workflow control, branching logic, and truly stateful multi-agent tasks that adapt dynamically based on user input, retrieved context, or external triggers.

**RAGAnything**
Expand the Retrieval-Augmented Generation pipeline into a truly multimodal knowledge system—supporting not only text files, PDFs, and code repositories, but a wide spectrum of complex, real-world data sources, including:

-Video transcripts

-Spreadsheets and tabular datasets (CSV, XLSX)

-Markdown wikis and Notion exports

-HTML dumps, raw JSON and XML APIs

-Audio transcription pipelines

-Presentation slide decks (PPTX, Google Slides)

-Scientific datasets, research papers, and domain-specific archives

This “RAGAnything” vision transforms AI-Assistant into a universal knowledge interface capable of reasoning over any file type or information source.

**Memory-Aware Chat**
Integrate chunked or graph-based long-term vector memory. This will preserve relevant conversation context across extended sessions, projects, or research sprints—enabling more coherent, context-rich dialogues over time.

**End-to-End Code Generation**
Build robust, prompt-driven code generation capabilities: automatically produce functions, classes, or even entire modules grounded in the knowledge retrieved via RAG pipelines. This moves AI-Assistant closer to becoming a practical, autonomous coding co-pilot.

**n8n Workflow Connectors**
Enable direct integration with external APIs, databases, or no-code automation pipelines using n8n. This lets conversations dynamically trigger real-world actions, automate updates, or orchestrate multi-step data flows without leaving the chat.

**Role Switching & Personas**
Implement role-based agent personas. Users can switch between specialized modes—such as developer assistant, student tutor, research analyst—each optimized for domain-specific reasoning, prompt styles, and tool access.

**Future Expansion: Multimodal Generation & Voice Integration**
Looking further ahead, AI-Assistant aims to break out of purely text-based interactions by introducing:

**Image Generation**: Integration of generative image models (OpenAI DALL·E, Stable Diffusion, or equivalent) for on-demand visual outputs, concept illustrations, and diagram creation directly within the chat loop.

**Voice Features**: Addition of text-to-speech (TTS) and speech-to-text (STT) capabilities to enable fully voice-enabled interaction—bridging the gap between traditional chat and real-time spoken AI assistance.

These advanced multimodal and voice features require significant compute and external API costs. To keep AI-Assistant accessible and evolving, these expansions are planned but dependent on available funding and community support.

**How You Can Contribute:**
If you want to help accelerate the rollout of these capabilities, you’re welcome to provide your own OpenAI API keys (or equivalent) for image or voice tasks. This helps offset infrastructure costs and ensures that advanced features can be delivered at scale for everyone.

Together, these advancements will turn AI-Assistant into a truly autonomous, RAG-anything, multimodal AI orchestration engine—capable of intelligently reasoning over any knowledge source, maintaining rich state, generating code, producing visuals, and integrating seamlessly into real-world pipelines for software engineering, research, and intelligent automation.
