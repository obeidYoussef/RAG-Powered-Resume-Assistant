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

## About the Resumes (Important)

⚠️ Disclaimer:

The resumes included in the Documents/ folder are **synthetic/fake resumes** created for demonstration and testing purposes only. They do not belong to real individuals and contain no real personal data.

**Using your own resumes**

  • You are free to delete the existing PDFs in the Documents/ folder.
  
  • You can upload your own resume PDFs into the same folder.
  
  • The system will automatically index and process any new documents placed in Documents/.

This design allows you to easily adapt the project to real-world datasets, experiments, or custom use cases.

## Project Structure

RAG-Powered-Resume-Assistant/

├── Documents/               (# Folder containing all candidate resumes (PDFs))

│   ├── Resume 1.pdf

│   ├── Resume 2.pdf

│   └── ...

├── AI_Powered_Resume_Screener.ipynb               (# Jupyter Notebook containing the RAG pipeline and Gradio interface)

├── Requirements.txt         (# Python dependencies)

└── README.md                (# Project documentation)


---

## How to Run
1. **Clone the repository:**
   
git clone https://github.com/obeidYoussef/RAG-Powered-Resume-Assistant.git

2. cd RAG-Powered-Resume-Assistant

3. pip install -r Requirments.txt

4. **Set your Google API Key:**

if "GOOGLE_API_KEY" not in os.environ:

    os.environ["GOOGLE_API_KEY"] = "xxxxxxxxxxxxxxxx"
    
**Open the notebook and run the cells in AI_Powered_Resume_Screener.ipynb.**

**Interact with the Gradio interface:**
- Type your question about candidate experience, skills, or qualifications.
- The AI will return a concise answer along with the resumes used to generate the response.

**Test queries:**
- Find candidates with more than 2 years of experience in data science and machine learning
- Find candidates with 3+ years of experience in NLP
- List candidates proficient in Python and SQL
- Who has experience with machine learning and data pipelines?
<img width="881" height="410" alt="1" src="https://github.com/user-attachments/assets/e0cf7558-0251-4f0d-80e7-df38b3862689" />

<img width="940" height="406" alt="2" src="https://github.com/user-attachments/assets/27333c62-37af-4f63-ab7b-7cfa271a90db" />

<img width="932" height="410" alt="3" src="https://github.com/user-attachments/assets/c390590d-8515-48a3-9cc4-4f38b5bb39b0" />

<img width="934" height="411" alt="4" src="https://github.com/user-attachments/assets/72596d1b-72e7-41d2-8cd9-a5962874f121" />

**Notes**
- The system supports both FAISS (fast, in-memory) and Chroma (persistent) vector stores.
- The chunk size for splitting resumes is 1000 with an overlap of 100 to preserve context.
- You can swap the embedding model in HuggingFaceBgeEmbeddings if you prefer a different one.
