# EPC Intelligence Core

> **AI-powered Spec Compliance Agent + Commissioning QA Copilot for data centre EPC projects**

Built with **FastAPI · ChromaDB · Groq (Llama-3.3-70b) · LangChain · Sentence-Transformers**

---

## What It Does

EPC Intelligence automates two of the most error-prone workflows in data centre EPC projects:

| Agent | What It Does |
|---|---|
| 🔍 **Spec Compliance Agent** | Compares vendor submittals against indexed standards (TIA-942-B, BIS IS 3043, Uptime Tier) and raises NCRs (Non-Conformance Reports) with clause references, severity levels, and remediation advice |
| 🔧 **Commissioning QA Copilot** | Generates step-by-step commissioning test procedures for UPS, Generators, Cooling, Fire Suppression, and BMS systems and records pass/fail results |
| 📋 **RFI RAG Agent** | Answers technical RFI questions using RAG over indexed project documents |
| 📅 **Schedule Risk Agent** | Analyses project schedules and flags delay risks |

---

## Tech Stack

| Layer | Technology |
|---|---|
| API | FastAPI + Uvicorn |
| LLM | Groq — `llama-3.3-70b-versatile` |
| Embeddings | `sentence-transformers/all-MiniLM-L6-v2` |
| Vector DB | ChromaDB (persistent) |
| ORM / DB | SQLAlchemy + SQLite |
| PDF Parsing | PyMuPDF + pdfplumber + pytesseract OCR |
| Orchestration | LangChain + LangGraph |
| Package Manager | `uv` |

---

## Project Structure

```
EPC Intelligence/
├── main.py                        # Entrypoint (re-exports FastAPI app)
├── backend/
│   ├── main.py                    # FastAPI app, lifespan, routers
│   ├── config.py                  # Pydantic settings (loads .env)
│   ├── agents/
│   │   ├── spec_compliance_agent.py   # Compliance check + NCR generation
│   │   ├── commissioning_agent.py     # Commissioning test procedures
│   │   ├── rfi_rag_agent.py           # RFI question answering
│   │   ├── schedule_risk_agent.py     # Schedule delay analysis
│   │   └── orchestrator.py            # Multi-agent orchestrator
│   ├── api/
│   │   ├── routes_documents.py    # Upload, ingest, debug endpoints
│   │   ├── routes_compliance.py   # Compliance check + NCR endpoints
│   │   ├── routes_commissioning.py# Commissioning session endpoints
│   │   └── routes_rfi.py          # RFI endpoints
│   ├── rag/
│   │   ├── document_ingestion.py  # PDF → chunks pipeline
│   │   ├── vector_store.py        # ChromaDB interface
│   │   ├── retriever.py           # Safe similarity search
│   │   └── standards_loader.py    # Index standards PDFs
│   └── db/
│       ├── models.py              # SQLAlchemy ORM models
│       ├── ncr_store.py           # NCR CRUD
│       └── test_record_store.py   # Commissioning record CRUD
├── data/
│   ├── standards/                 # Place spec PDFs here (TIA-942, BIS, etc.)
│   ├── uploads/                   # Uploaded vendor submittals
│   ├── chroma_db/                 # ChromaDB vector index (auto-created)
│   └── test_records/              # Commissioning test records
├── render.yaml                    # Render deployment blueprint
├── requirements.txt               # Pinned dependencies
├── pyproject.toml                 # Project metadata + dependencies
└── .env.example                   # Environment variable template
```

---

## Quick Start (Local)

### 1. Clone & install

```bash
git clone https://github.com/itshaurya055-glitch/EPC_Intelligence.git
cd EPC_Intelligence

# Install uv if you don't have it
pip install uv

# Install all dependencies
uv sync
```

### 2. Configure environment

```bash
cp .env.example .env
```

Edit `.env` and set your **Groq API key**:
```env
GROQ_API_KEY=gsk_your_key_here
```

Get a free key at [console.groq.com](https://console.groq.com)

### 3. Run

```bash
uv run uvicorn main:app --reload --port 8000
```

Open **[http://localhost:8000](http://localhost:8000)**

| URL | Description |
|---|---|
| `http://localhost:8000/` | Dashboard UI |
| `http://localhost:8000/docs` | Swagger — interactive API docs |
| `http://localhost:8000/api/health` | Health check |

---

## Key API Endpoints

### Documents
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/documents/ingest` | Upload + vectorize a PDF |
| `GET` | `/api/documents/list?project_id=N` | List project documents |
| `GET` | `/api/documents/debug?project_id=N&filename=X` | Inspect ChromaDB metadata |

### Compliance
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/compliance/check` | Run compliance check on a document |
| `POST` | `/api/compliance/check-stream` | Streaming compliance check (SSE) |
| `GET` | `/api/ncr/list?project_id=N` | List NCRs |
| `GET` | `/api/ncr/summary?project_id=N` | NCR summary by severity |

### Commissioning
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/commissioning/start` | Start a commissioning session |
| `POST` | `/api/commissioning/record` | Record a test step result |
| `GET` | `/api/commissioning/report/{session_id}` | Get full session report |

### Standards
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/standards/index` | Index all PDFs in `data/standards/` |
| `GET` | `/api/standards/status` | Check indexed standards |

---

## Indexing Standards

Place your specification PDFs (TIA-942-B, BIS IS 3043, Uptime Tier, etc.) in `data/standards/` then hit:

```bash
curl -X POST http://localhost:8000/api/standards/index
```

Or use the Swagger UI at `/docs`.

---

## Deploy to Render

This repo includes a `render.yaml` Blueprint for one-click deployment.

### Steps

1. **Push to GitHub** (already done)

2. **Go to [render.com](https://render.com)** → New → Blueprint → connect this repo

3. **Add Persistent Disk** in Render dashboard:
   - Mount Path: `/data`
   - Size: 1 GB

4. **Set environment variable** in Render dashboard:
   ```
   GROQ_API_KEY = gsk_your_key_here
   ```
   All other vars are pre-filled by `render.yaml`

5. **Deploy** — first build takes ~5–8 min (downloads PyTorch + SentenceTransformers)

> **Note:** Render free plan sleeps after 15 min idle. Upgrade to Starter ($7/mo) for always-on.

---

## Environment Variables

| Variable | Default | Description |
|---|---|---|
| `GROQ_API_KEY` | **required** | Groq API key |
| `GROQ_MODEL` | `llama-3.3-70b-versatile` | Groq model name |
| `CHROMA_DB_PATH` | `./data/chroma_db` | ChromaDB storage path |
| `UPLOAD_DIR` | `./data/uploads` | Uploaded PDF storage |
| `STANDARDS_DIR` | `./data/standards` | Standards PDF directory |
| `DATABASE_URL` | `sqlite:///./epc.db` | SQLAlchemy DB URL |
| `EMBEDDING_MODEL` | `all-MiniLM-L6-v2` | SentenceTransformer model |
| `CHUNK_SIZE` | `800` | RAG chunk size (chars) |
| `CHUNK_OVERLAP` | `100` | Chunk overlap (chars) |
| `TOP_K_RETRIEVAL` | `5` | Number of RAG results |

---

## Standards Supported

- **TIA-942-B** — Telecommunications Infrastructure Standard for Data Centers
- **BIS IS 3043** — Code of Practice for Earthing
- **BICSI 002** — Data Center Design and Implementation Best Practices
- **Uptime Institute Tier Standard** — Tier I–IV topology criteria

Add any PDF to `data/standards/` and re-index to extend coverage.

---

## License

MIT
