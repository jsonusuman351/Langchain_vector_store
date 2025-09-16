# 🧠 Building a RAG Knowledge Base with LangChain Vector Stores

![LangChain](https://img.shields.io/badge/LangChain-0086CB?style=for-the-badge&logo=langchain) ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai) ![FAISS](https://img.shields.io/badge/FAISS-0080FF?style=for-the-badge) ![PyPDF](https://img.shields.io/badge/PyPDF-F40F0F?style=for-the-badge&logo=adobeacrobatreader) ![Python-Dotenv](https://img.shields.io/badge/Python--Dotenv-EFC538?style=for-the-badge)

Hey there! Welcome to my hands-on project where I built a complete vector store from scratch. This is the heart of any Retrieval-Augmented Generation (RAG) system. After learning about document loading, text splitting, and embeddings, I wanted to bring it all together to create a searchable knowledge base.

This repository, documented in a single Jupyter Notebook, is my journey of taking a raw PDF document, processing it, and turning it into a powerful semantic search engine using LangChain and FAISS.

---

### 🤔 Why a Vector Store? The Brain of RAG

So, what's the big deal with vector stores? I learned that they are specialized databases designed to store text data not as words, but as numerical vectors (embeddings). This is the magic that allows us to find documents based on their *meaning*, not just keywords.

When a user asks a question, we convert their question into a vector and use the vector store to find the most similar document chunks in our knowledge base. This context is then fed to the LLM to generate a factual, relevant answer.

---

### ✨ Core Workflow I Implemented

This project follows the complete, end-to-end lifecycle of a vector store for a RAG application:

1.  **📄 Document Loading**: First, I used `PyPDFLoader` to load a multi-page PDF document into memory.

2.  **🔪 Text Splitting**: I then used the `RecursiveCharacterTextSplitter` to break the document down into smaller, semantically coherent chunks that can be easily processed by an LLM.

3.  **🧠 Embedding & Storing**: Next, I used `OpenAIEmbeddings` to convert each text chunk into a numerical vector. I then used **FAISS** (Facebook AI Similarity Search), a super-efficient, in-memory vector store, to store these embeddings.

4.  **💾 Persisting the Knowledge Base**: I demonstrated how to save the fully populated FAISS vector store to disk. This is a crucial step for production, as you don't want to re-process your documents every time your application starts.

5.  **🔍 Advanced Retrieval Strategies**: Finally, I explored two powerful ways to query the vector store:
    -   **Similarity Search**: The standard method for finding the chunks that are most semantically similar to the user's query.
    -   **Max Marginal Relevance (MMR) Search**: A more advanced technique that is designed to fetch not only relevant but also *diverse* documents, which helps avoid returning redundant information.

---

### 🛠️ Tech Stack

-   **Core Framework**: LangChain
-   **LLM & Embedding Provider**: OpenAI
-   **Vector Store**: FAISS (CPU version)
-   **Document Loading**: PyPDF
-   **Notebook Environment**: Jupyter
-   **Core Libraries**: `langchain-core`, `langchain-community`, `langchain-openai`, `python-dotenv`

---

### ⚙️ Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/jsonusuman351/langchain_vector_store.git](https://github.com/jsonusuman351/langchain_vector_store.git)
    cd langchain_vector_store
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    # It is recommended to use Python 3.10 or higher
    python -m venv venv
    .\venv\Scripts\activate
    ```

3.  **Install the required packages:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Set Up Environment Variables:**
    -   Create a file named `.env` in the root directory.
    -   Add your OpenAI API key to this file:
        ```env
        OPENAI_API_KEY="your-openai-api-key"
        ```

---

### 🚀 How to Use This Project

The entire workflow is contained within a single Jupyter Notebook.

1.  **Launch Jupyter:**
    Make sure your virtual environment is active, then run:
    ```bash
    jupyter notebook
    ```

2.  **Open the Notebook:**
    In the Jupyter interface that opens in your browser, click on `langchain_vector_store.ipynb`.

3.  **Run the Cells:**
    You can run each cell in the notebook sequentially to see the entire process, from loading the PDF to performing similarity searches. Feel free to experiment by changing the queries or the document!

---

### 🔬 A Tour of the Notebook

The project is presented as a single, well-commented Jupyter Notebook, which makes it easy to follow the story from start to finish.

<details>
<summary>Click to view the code layout</summary>

```
langchain_vector_store/
│
├── langchain_vector_store.ipynb # The complete end-to-end workflow
│
├── project_document.pdf         # The sample document for the knowledge base
├── faiss_index/                 # This folder will be created when you save the store
│
├── requirements.txt
├── .env                         # (You need to create this for your API key)
└── README.md
```
</details>

---

---
