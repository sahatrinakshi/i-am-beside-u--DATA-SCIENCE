# i-am-beside-u--DATA-SCIENCE
AI-powered Exam-Prep Agent that automatically generates MCQs from study material, classifies difficulty with a fine-tuned DistilBERT model, and offers an interactive quiz interface using a multi-agent, RAG-enhanced architecture
# Paper-Sleuth: Exam-Prep Question Generator + Quiz Master

**Author:** Saugata Malakar  
**University:** IIT Kharagpur  
**Department:** Civil Engineering

---

## 🚀 Project Overview
Paper-Sleuth is an **AI-powered exam preparation agent** that automatically:
* Extracts key concepts from notes or papers,
* Generates multiple-choice questions (MCQs) in the style of past exams,
* Classifies difficulty levels, and
* Presents an **interactive quiz interface** for self-testing.

The system combines **multi-agent reasoning**, **Retrieval-Augmented Generation (RAG)**, and a **fine-tuned DistilBERT classifier** for difficulty tagging.

---

## ✨ Key Features
- **Multi-Agent Pipeline**  
  *Planner* → extracts key concepts  
  *Generator* → creates MCQs with LoRA-tuned Falcon/GPT-J  
  *Evaluator* → DistilBERT difficulty classifier & quality filter  

- **Retrieval-Augmented Generation (RAG)**  
  Uses FAISS vector store to pull relevant context from uploaded lecture materials.

- **External Tools (MCP-style)**  
  Wikipedia search & calculator utilities accessible to the Generator Agent.

- **User Interface**  
  Streamlit web app: type a topic, generate a quiz, attempt MCQs and get instant scoring.

---

## 🧠 Models Used
| Model | Purpose | Reason |
|------|--------|-------|
| LoRA-tuned Falcon-7B / GPT-J | MCQ generation | Open-weights, supports parameter-efficient tuning for exam style |
| DistilBERT | Difficulty classification | Lightweight, fast inference |
| FAISS + HuggingFace Embeddings | Context retrieval | Efficient RAG for large lecture documents |

---

## 📂 Repository Structure
paper_sleuth_full_repo/
├─ agents/ # Planner, Generator, Evaluator agents
├─ rag/ # RAG indexing and search
├─ tools/ # External utilities (wiki_search, calculator)
├─ ui/ # Streamlit quiz interface
├─ data/ # Sample MCQ & difficulty datasets
├─ notebooks/ # Colab-ready notebook
├─ main_pipeline.py # Orchestrates the full workflow
├─ train_distilbert.py
└─ requirements.txt


---

## ⚡ Quick Start
1. **Clone repo & install dependencies**
```bash
git clone https://github.com/<your-username>/paper-sleuth.git
cd paper-sleuth_full_repo
pip install -r requirements.txt


Run the Streamlit UI

streamlit run ui/streamlit_app.py


(Optional) Fine-tune DistilBERT

python train_distilbert.py


Generate MCQs in Colab
Open notebooks/exam_prep_agent.ipynb and run all cells.
