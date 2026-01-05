# RAG-Powered Resume Assistant

## Objective
The **RAG-Powered Resume Assistant** is an AI application designed to help HR professionals and recruiters quickly analyze resumes and extract relevant candidate information using a **Retrieval-Augmented Generation (RAG)** pipeline. Users can ask natural language questions about candidates’ skills, experience, and qualifications, and the system retrieves and summarizes the most relevant resumes.

---

## Problem Statement
Recruiters often spend hours manually reviewing resumes to find suitable candidates. This project aims to **automate resume analysis** by:
- Retrieving resumes that match specific criteria.
- Summarizing candidate experience and qualifications.
- Allowing natural language queries to extract structured insights.

This reduces time and improves accuracy in identifying qualified candidates.

---

## Tech Stack
- **Language Model & LLMs:** Google Gemini-3 (via `langchain-google-genai`)  
- **Vector Embeddings:** HuggingFace BGE (`sentence-transformers/all-MiniLM-L6-v2`)  
- **Vector Stores:** FAISS (fast in-memory), Chroma (persistent, local)  
- **Document Loading:** `PyPDFDirectoryLoader` for PDF resumes  
- **Text Splitting:** `RecursiveCharacterTextSplitter` from LangChain  
- **RAG Framework:** LangChain (`RetrievalQA`)  
- **UI:** Gradio for interactive web interface  
- **Python Packages:** `langchain`, `langchain-community`, `faiss-cpu`, `chromadb`, `pypdf`, `gradio`, `sentence-transformers`

---

## Project Structure
RAG-Resume-Assistant/
├── Documents/               # Folder containing all candidate resumes (PDFs)
│   ├── Resume 1.pdf
│   ├── Resume 2.pdf
│   └── ...
├── main.ipynb               # Jupyter Notebook containing the RAG pipeline and Gradio interface
├── requirements.txt         # Python dependencies
└── README.md                # Project documentation

---

## How to Run
1. **Clone the repository:**
git clone https://github.com/obeidYoussef/RAG-Powered-Resume-Assistant.git

cd RAG-Powered-Resume-Assistant

pip install -r Requirments.txt

Set your Google API Key:

if "GOOGLE_API_KEY" not in os.environ:

    os.environ["GOOGLE_API_KEY"] = "xxxxxxxxxxxxxxxx"
    
**Open the notebook and run the cells in AI_Powered_Resume_Screener.ipynb.**

**Interact with the Gradio interface:**
- Type your question about candidate experience, skills, or qualifications.
- The AI will return a concise answer along with the resumes used to generate the response.

**Test queries:**
- Find candidates with 3+ years of experience in NLP
- List candidates proficient in Python and SQL
- Who has experience with machine learning and data pipelines?

**Notes**
- The system supports both FAISS (fast, in-memory) and Chroma (persistent) vector stores.
- The chunk size for splitting resumes is 1000 with overlap 100 to preserve context.
- You can swap the embedding model in HuggingFaceBgeEmbeddings if you prefer a different one.
