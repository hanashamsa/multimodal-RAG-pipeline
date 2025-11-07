# Multimodal RAG Pipeline — FastAPI + Inngest + Qdrant + OpenAI

A modular **Retrieval-Augmented Generation (RAG)** system built with **FastAPI**, **Inngest**, **Qdrant**, and **OpenAI’s API**.  
It ingests PDF documents, stores embeddings in a vector database, and serves AI-powered contextual question-answering — all event-driven.

---

##  Features

-  **Event-driven architecture** using [Inngest](https://www.inngest.com/)
-  **PDF ingestion & chunking**
-  **Vector embedding & search** via [Qdrant](https://qdrant.tech/)
-  **Context-aware AI responses** using OpenAI GPT models
-  **FastAPI** backend for serving and orchestration
-  Environment-based configuration with `.env` file

---

##  Tech Stack

| Component | Description |
|------------|-------------|
| **FastAPI** | RESTful backend framework |
| **Inngest** | Workflow and event management |
| **Qdrant** | Vector database for embeddings |
| **OpenAI** | Text embeddings and LLM completions |
| **Docker** | Containerization for Qdrant |
| **Python 3.10+** | Core runtime |

---

##  Setup Instructions

### 1️ Clone this repository
```bash
git clone https://github.com/<your-username>/multimodal-rag.git
cd multimodal-rag
````

###  Create and activate a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```


### Setup environment variables

Create a `.env` file in the project root:

```bash
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxx
```

###  Run Qdrant in Docker

```bash
sudo docker run -d \
  --name qdrantRAGDb \
  -p 6333:6333 \
  -v "$(pwd)/qdrant_storage:/qdrant/storage" \
  qdrant/qdrant
```

### Run the FastAPI app

```bash
uv run uvicorn main:app --reload
```

The app will be live at:
 [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

##  Project Structure

```
Multimodal_RAG/
├── main.py                # FastAPI + Inngest orchestration
├── data_loader.py         # PDF loading, chunking, and embedding
├── vector_db.py           # Qdrant client wrapper
├── custom_types.py        # Pydantic models for typed RAG data
├── .env                   # Environment variables (not tracked)
├── requirements.txt
└── README.md
```

---


---

##  Future Enhancements

* Multimodal support (text + image embeddings)
* Embedding model selection via config
*  Frontend dashboard for managing sources
*  Vector storage performance metrics

---

##  Author

**Muhammed Hanas V H**


---

##  License

MIT License © 2025 Vh Hanas

```
