# Ayurvedic Semantic Search System using RAG and a Knowledge Graph

This project implements a semantic search and Question-Answering (QA) system for Ayurvedic medicine. [cite_start]It uses a hybrid approach that combines **Retrieval-Augmented Generation (RAG)** with a **Knowledge Graph (KG)** to provide accurate, context-aware answers from unstructured Ayurvedic texts[cite: 2158, 2159].

[cite_start]This repository contains the implementation described in the research paper found in the `docs/` directory[cite: 2152].

## Project Workflow

The project is divided into two main Jupyter Notebooks:

1.  **RAG Implementation & Evaluation (`1_RAG_Implementation_and_Evaluation.ipynb`)**: This notebook handles the processing of the source PDF, text chunking, vector embedding, and the implementation of a RAG pipeline for answering queries. [cite_start]It also includes evaluation against reference answers using ROUGE scores[cite: 2164, 2288].

2.  **Knowledge Graph Construction & QA (`2_Knowledge_Graph_Construction_and_QA.ipynb`)**: This notebook focuses on building a structured knowledge graph in Neo4j from the Ayurvedic text. [cite_start]It extracts entities (e.g., Disease, Symptom, Treatment) and their relationships, and then uses a LangChain QA chain to query this graph using natural language[cite: 2264, 2265, 2330].

## Repository Structure

```
Ayurvedic-QnA-System/
│
├── data/                    # Contains the source PDF document
│   └── ayurveda_book.pdf
│
├── docs/                    # Contains the research paper
│   └── research_paper.pdf
│
└── notebooks/               # Main implementation notebooks
    ├── 1_RAG_Implementation_and_Evaluation.ipynb
    └── 2_Knowledge_Graph_Construction_and_QA.ipynb
```

## Setup and Installation

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/your-username/Ayurvedic-QnA-System.git](https://github.com/your-username/Ayurvedic-QnA-System.git)
    cd Ayurvedic-QnA-System
    ```

2.  **Create a Virtual Environment**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Set Up Credentials**
    * You will need API keys and credentials for **Neo4j** and **Groq**. These should be entered directly into the `2_Knowledge_Graph_Construction_and_QA.ipynb` notebook where prompted.
    * For the RAG notebook, you will need to log in to Hugging Face to download the Gemma model.

## Usage

1.  **Place Data**: The source document `data1.pdf` should be placed in the `data/` directory and renamed to `ayurveda_book.pdf`.
2.  **Run the Notebooks**: Open the `notebooks/` directory and run the Jupyter Notebooks in order.
    * Start with `1_RAG_Implementation_and_Evaluation.ipynb` to see the RAG pipeline and evaluation.
    * Then, run `2_Knowledge_Graph_Construction_and_QA.ipynb` to build the knowledge graph and interact with the graph-based QA system.

## Technologies Used
* **Language**: Python
* **Knowledge Graph**: Neo4j
* **LLMs & NLP**: LangChain, Groq (Llama-3), Hugging Face Transformers (Gemma), Sentence-Transformers
* **Data Processing**: PyMuPDF, PyPDF, Pandas
* **Evaluation**: ROUGE Score
