# SmartQA System

SmartQA System — a full-stack pipeline for building, querying, and interacting with question & answer corpora. The system is designed to support automated corpus generation, hybrid retrieval, and multiple web interfaces. 

Unlike traditional black-box chatbots, SmartQA can operate as a no-cost, lightweight alternative in budget or energy-constrained environments. Since all responses are based in an inspectable Q&A corpus, it is usable in critical use cases where hallucinations are a deal-breaker

---

## 📁 Documentation Overview

This repo includes documentation for three key components:

### 1. 📚 [Corpus Generation Pipeline](docs/CorpusGenerationDocs.md)

Automates the creation of a Q&A corpus from web content using the Google Gemini model.

- **Stage 1**: Scrape pages using URL lists and HTML boundaries.
- **Stage 2**: Generate relevant questions based on the scraped content.
- **Stage 3**: Use Gemini to generate answers to those questions.

📖 **[Read more →](docs/CorpusGenerationDocs.md)**
#### Note

- This project was initiated during my internship at CommitGlobal.  
The repository includes a QA corpus generated from their website [Dopomoha](https://dopomoha.ro/en), along with the generation parameters used in the processing for reference.

---

### 2. 🔍 [Retrieval Pipeline](docs/RetrievalDocs.md)

Retrieves the most relevant Q&A pairs using a hybrid search engine:

- Combines **dense**, **sparse**, and **ColBERT** representations.
- Reranks results using a **cross-encoder**.
- Supports both **FastAPI web server** and **CLI mode**.

📖 **[Read more →](docs/RetrievalDocs.md)**

---

### 3. 🖥️ [Frontend Interface](docs/FrontendDocs.md)

Two user-friendly ways to interact with the system:

- **Smart FAQ**: Query multiple answers with review flow.
- **Chat Interface**: Conversational mode with top-1 answer responses.

📖 **[Read more →](docs/FrontendDocs.md)**

---

## Quick Start with Docker Compose

You can run the entire system using Docker Compose from the project root (where `docker-compose.yml` is located):

```bash
docker-compose up --build