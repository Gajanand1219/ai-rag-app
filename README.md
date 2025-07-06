# ⚛️ AI-Powered Physics Q&A Assistant (RAG Application)

This is a **Retrieval-Augmented Generation (RAG)** application built to answer **Physics-related questions** from your **own textbook or content** using state-of-the-art tools. It's designed as a simple CLI (command-line interface) assistant that performs fast, accurate question answering on large unstructured text.

---
![Screenshot 2025-07-06 224958](https://github.com/user-attachments/assets/49863088-a648-4d86-a264-700d0557bbdb)

![Screenshot 2025-07-06 224845](https://github.com/user-attachments/assets/e6d6b7be-d769-4c43-88a9-3c7534ce4311)


---

## 🚀 Tech Stack

- 🔗 **LangChain** – for managing LLM + retrieval workflows
- 🤖 **Azure OpenAI (GPT-3.5 / GPT-4)** – for generating intelligent, context-aware answers
- 🧠 **FAISS** – for semantic vector search of book content
- 📝 **Plain Text Input (`.txt`)** – easy to convert from PDF/EPUB
- 🐍 **Python** – core language for scripting

---

## 🎯 Key Features

- ✅ Ingests your own **physics textbook** or material in `.txt` format
- ✅ Embeds and indexes your content using **FAISS vector store**
- ✅ Retrieves top relevant content for each user question using **semantic search**
- ✅ Sends both the **query and relevant context** to OpenAI via LangChain
- ✅ Returns **concise, accurate answers** from GPT models
- ✅ Fully offline indexing (embedding happens once)
- ✅ Easy to customize for any domain or subject

---




---

## 🧠 How It Works (RAG Pipeline Overview)

**Step 1:** Load physics book from `.txt` file  
**Step 2:** Split the text into chunks (e.g., 500 words with overlap)  
**Step 3:** Embed chunks using OpenAI Embeddings (e.g., `text-embedding-ada-002`)  
**Step 4:** Store embeddings in FAISS index  
**Step 5:** For each user question:
  - Embed the question
  - Retrieve top-k matching chunks
  - Send retrieved context + question to OpenAI LLM via LangChain
  - Return generated answer

---

## ⚙️ Setup Instructions
## 🚀 Getting Started

Follow these steps to install and run the AI-Powered RAG Physics Q&A Assistant on your own machine:

---

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Gajanand1219/ai-rag-app.git
cd ai-rag-app

# On macOS/Linux:
python -m venv venv
source venv/bin/activate

# On Windows:
python -m venv venv
venv\Scripts\activate


pip install -r requirements.txt

# Azure OpenAI settings
AZURE_API_KEY=your_actual_key_here
AZURE_ENDPOINT=https://your-resource-name.openai.azure.com/
AZURE_DEPLOYMENT_NAME=gpt-4o
AZURE_API_VERSION=2024-05-01-preview

# If using a Streamlit interface
streamlit run app.py



--------------------------------------------------------------------------------------------------------------------------------------------....
### 1. Clone the Repository

```bash
❯ What is Newton's second law?
❓ Question: Explain the principle of conservation of momentum.

📄 Retrieved Context:
"In an isolated system, the total momentum before and after a collision remains constant..."

🤖 Answer (GPT-4):
The principle of conservation of momentum states that in a closed system with no external forces, the total momentum of the system remains constant over time. This means the momentum before and after an interaction is equal.


## 🧱 Project Structure
rag_project/
├── data/
│ └── physics_book.txt # Your source material
├── app.py # Main CLI application
└── README.md
