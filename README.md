# 🧬 Genomics Explorer

## 📖 Overview
Genomics Explorer is a **full-stack AI research tool** for exploring cancer genomics datasets.  
It combines **data ingestion**, **statistical analysis**, **visualization**, and **LLM-powered Q&A** to help researchers quickly identify mutation frequencies, survival trends, and gene expression patterns.  

---

## 🎯 MVP (Minimum Viable Product)
Focus cohort: **TCGA-LUAD (Lung Adenocarcinoma)** from [cBioPortal](https://www.cbioportal.org).

**Features:**
- 🔹 Data ingestion from cBioPortal API (mutations + clinical data)  
- 🔹 Backend endpoints:  
  - `/genes/top_mutated` → ranked list of top mutated genes  
  - `/survival/km?gene=TP53` → Kaplan–Meier survival analysis by gene mutation  
- 🔹 Frontend (React web app):  
  - Two tabs: **Top Mutations** and **Survival**  
  - Export results as **CSV/PNG**  
- 🔹 Compliance: disclaimer banner — *“Educational use only. Not medical advice.”*  

---

## 🚀 Roadmap
**Phase 2**  
- Add **GTEx normal tissue data** for tumor-vs-normal comparisons  
- Statistical testing (t-test, Wilcoxon, FDR correction)  

**Phase 3**  
- Add **LLM chat interface** → natural language queries (e.g., *“Show survival for TP53 in LUAD”*)  
- Add **pgvector embeddings** for gene & pathway knowledge  
- Add **query caching** for faster responses  

---

## 💡 Business Value
- Researchers currently spend hours writing scripts or using complex portals.  
- Genomics Explorer provides results in **minutes instead of hours**.  
- Potential to **reduce exploration time by 60%**, accelerating biomarker discovery and hypothesis generation.  

---

## 🛠️ Tech Stack
**Backend**: FastAPI · Pandas · Lifelines · Postgres + pgvector  
**Frontend**: React · Vite · TailwindCSS · Plotly.js  
**Data Sources**: TCGA via cBioPortal API · GTEx  
**AI Layer**: LLM tool-calling + Retrieval-Augmented Generation (RAG)  

---

## 📊 Example Queries
- *“Which genes are most mutated in lung adenocarcinoma?”*  
- *“Show survival analysis for TP53 mutations in LUAD.”*  
- *“Is EGFR over-expressed in tumors vs normal lung tissue?”*  

---

## ⚠️ Disclaimer
This project is for **educational and research purposes only**.  
It does **not** provide medical advice, diagnosis, or treatment.  

---

## 📂 Project Structure


genomics-explorer/
backend/ # FastAPI app + analysis endpoints
frontend/ # React + Plotly interface
data/ # Parquet datasets (mutations, clinical, expression)
db/ # Database schema & migrations
README.md # Project overview


---

## 🖥️ How to Run (MVP)
### Backend

cd backend
uvicorn app:app --reload


### Frontend

cd frontend
npm install
npm run dev

