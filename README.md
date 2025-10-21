# 💊 Drug Interaction Checker: A RAG System for Medical Queries

This project implements an intelligent **Drug Interaction Checker** using a **Retrieval-Augmented Generation (RAG)** architecture powered by LangChain and a fast Large Language Model (LLM, typically Groq).

The primary goal is to provide **highly accurate, contextually relevant** information on **Drug-Drug Interactions (DDI)** by grounding the LLM's answers in a specialized medical knowledge base, thereby minimizing hallucinations and increasing clinical reliability.

## 🚀 Key Features

* **RAG Architecture for Accuracy:** Utilizes the Retrieval-Augmented Generation (RAG) pattern, ensuring the LLM's response is based directly on retrieved documents from the vector store, not general training data.
* **Specialized Knowledge Base:** The system uses a dedicated dataset (likely drug interaction summaries or tables) that is chunked, embedded, and stored in a vector database for efficient semantic search.
* **LangChain Orchestration:** A LangChain pipeline manages the flow, taking the user query, retrieving the top relevant drug interaction documents, and feeding the context to the LLM for final answer synthesis.
* **Fast & Contextual Responses:** Integrated with a high-speed LLM (like Llama 3 via Groq) to quickly synthesize complex medical facts into clear, concise, and understandable summaries of the interaction, including the type and mechanism.
* **Example DDI Analysis:** Designed to handle queries like "What are the potential interactions between Warfarin and Aspirin?" and provide precise, document-verified answers.

## ⚙️ Technology Stack

| Category | Tool / Library | Purpose |
| :--- | :--- | :--- |
| **RAG Framework** | LangChain | Orchestrates the entire RAG pipeline, handling loading, splitting, retrieval, and chaining. |
| **Language Model** | Groq (e.g., Llama 3) | Provides high-speed inference for synthesizing the retrieved information into the final answer. |
| **Vector Store** | ChromaDB / FAISS (or similar) | Stores and manages the embeddings of the medical knowledge base. |
| **Core Libraries** | Python, Pandas | Data processing and execution environment. |

## 🛠️ Setup and Execution

The entire project is self-contained within the `Drug_Interaction_Checker_rag.ipynb` Jupyter notebook.



2.  **Install dependencies:**
    You will need `langchain-groq`, `langchain-core`, and potentially other libraries for data loading/embeddings (e.g., `sentence-transformers` or `chromadb`).
    ```bash
    pip install langchain-groq langchain-core [other dependencies]
    ```
    *(Note: Ensure all dependencies mentioned in the notebook's initial cells are installed.)*

3.  **Set up Groq API Key:**
    The system requires a **Groq API Key** to run the LLM. Set this key as an environment variable or directly within the notebook's relevant cell for the `ChatGroq` initialization.

4.  **Run the Notebook:**
    Open `Drug_Interaction_Checker_rag.ipynb` in a Jupyter environment and execute all cells sequentially to load the data, build the RAG chain, and test the example queries.

### Example Output

When queried about a specific interaction, the system will provide documented responses, such as:

> **Query:** "Describe the interaction type for Nicergoline and Cilostazol."
> **Response:** "The interaction type for Nicergoline and Cilostazol is 'risk or severity of adverse effects'."
