<div align="center">

# Archon — The Intelligent Architect

**A RAG-powered intelligent document assistant built for the CortexX Hackathon 2026.**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-HuggingFace-yellow?style=for-the-badge&logo=huggingface)](https://Prince-Alca-Archon.hf.space)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](https://github.com/princeemmanuelalca-art/Archon/blob/main/LICENSE)
[![Python](https://img.shields.io/badge/Python-Flask-green?style=for-the-badge&logo=python)](https://github.com/princeemmanuelalca-art/Archon)
[![LLM](https://img.shields.io/badge/LLM-Groq%20llama--3.1--8b-orange?style=for-the-badge)](https://groq.com)

</div>

---

## What is Archon?

Archon is an intelligent document assistant that lets you upload your own knowledge base and query it using natural language. It combines semantic vector search with a large language model to return grounded, contextually accurate answers — not hallucinations.

Built with Flask, ChromaDB, sentence-transformers, and Groq's `llama-3.1-8b-instant`, and deployed on HuggingFace Spaces via Docker.

---

## Features

| Feature | Detail |
|---|---|
| Document Ingestion | Upload PDFs, TXTs, or paste raw text |
| Semantic Search | ChromaDB + sentence-transformers vector embeddings |
| LLM Answering | Groq — `llama-3.1-8b-instant` |
| Conversation Memory | Multi-session memory across queries |
| UI | Material Design — "The Intelligent Architect" theme |

---

## Quick Start (Local)

**Prerequisites:** Python 3.x, pip, a [Groq API key](https://console.groq.com)

```bash
git clone https://github.com/princeemmanuelalca-art/Archon.git
cd Archon
cp .env.example .env
# Edit .env and set your GROQ_API_KEY
pip install -r requirements.txt
python app.py
```

Open `http://localhost:7860` in your browser.

---

## Docker

```bash
docker build -t archon .
docker run -p 7860:7860 --env-file .env archon
```

---

## Deployment (HuggingFace Spaces)

The app is containerized and deployed via Docker on HuggingFace Spaces.

1. Fork or push this repo to your HuggingFace Space.
2. Go to **Space → Settings → Secrets**.
3. Add `GROQ_API_KEY` as a secret.
4. The Space will build and deploy automatically using the included `Dockerfile`.

Live instance: [Prince-Alca-Archon.hf.space](https://Prince-Alca-Archon.hf.space)

---

## Project Structure

```
Archon/
├── app.py                  # Flask entry point
├── rag_system.py           # RAG core (ChromaDB + LLM)
├── templates/
│   └── index.html          # Full frontend UI
├── utils/
│   ├── config.py           # LLM provider config
│   └── llm_interface.py    # Groq API handler
├── data/                   # Document storage
├── static/                 # Static assets (CSS/JS)
├── requirements.txt
├── Dockerfile
└── .env.example
```

---

## Stack

| Layer | Technology |
|---|---|
| Backend | Flask (Python) |
| LLM | Groq — `llama-3.1-8b-instant` |
| Vector DB | ChromaDB |
| Embeddings | sentence-transformers |
| Hosting | HuggingFace Spaces (Docker) |

**Language breakdown (from repo):** Python 35.4% · HTML 30.7% · CSS 17.0% · JavaScript 16.0%

---

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `GROQ_API_KEY` | Yes | API key from [console.groq.com](https://console.groq.com) |

See `.env.example` for the full template.

---

## License

MIT — see [LICENSE](https://github.com/princeemmanuelalca-art/Archon/blob/main/LICENSE).
