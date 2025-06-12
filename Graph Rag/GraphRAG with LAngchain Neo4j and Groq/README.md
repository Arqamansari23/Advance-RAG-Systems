# GraphRAG with LangChain, Neo4j, and Groq Gemma Model

This project demonstrates a **Graph Retrieval-Augmented Generation (GraphRAG)** pipeline using [LangChain](https://python.langchain.com/), [Neo4j](https://neo4j.com/), and the [Groq Gemma LLM](https://groq.com/). The notebook shows how to connect to a Neo4j graph database, extract knowledge from text, transform it into a graph structure, and use a large language model to answer questions with Cypher-powered graph retrieval.

## Key Features

- **Neo4j Integration:** Connects to a remote Neo4j AuraDB instance for graph storage and querying.
- **Groq Gemma LLM:** Uses Groq's Gemma model for fast, high-quality language generation.
- **Graph Construction:** Extracts entities and relationships from unstructured text and loads them into Neo4j.
- **Cypher QA Chain:** Uses LangChain's GraphCypherQAChain to translate natural language questions into Cypher queries and generate answers.
- **Movie Dataset Example:** Loads and queries a sample movie dataset to demonstrate graph-based QA.

## How It Works

1. **Install Dependencies:** Installs required Python packages (`langchain`, `langchain-community`, `langchain-groq`, `neo4j`, `langchain-experimental`).
2. **Connect to Neo4j:** Sets up connection credentials and initializes a Neo4j graph object.
3. **Connect to Groq LLM:** Sets up the Groq API key and initializes the Gemma model.
4. **Extract Graph from Text:** Uses `LLMGraphTransformer` to extract entities and relationships from sample text and convert them into graph documents.
5. **Load Movie Dataset:** Loads a sample movie dataset into Neo4j using Cypher.
6. **Graph QA Chain:** Uses `GraphCypherQAChain` to answer natural language questions by translating them into Cypher queries and retrieving answers from the graph.

## Example Usage

```python
# Ask a question about the graph
response = chain.invoke({"query": "Who was the director of the movie GoldenEye"})
print(response)

response = chain.invoke({"query": "Tell me the genre of the movie GoldenEye"})
print(response)
```

## Requirements

- Python 3.9+
- Neo4j AuraDB instance (or local Neo4j)
- Groq API key for Gemma model

## Setup

1. **Install dependencies:**
    ```bash
    pip install langchain langchain-community langchain-groq neo4j langchain-experimental
    ```

2. **Set your Neo4j credentials:**
    - Update `NEO4J_URI`, `NEO4J_USERNAME`, and `NEO4J_PASSWORD` in the notebook.

3. **Set your Groq API key:**
    - Update `groq_api_key` in the notebook.

4. **Run the notebook:**
    - Open `Untitled0.ipynb` in Jupyter or VS Code and execute the cells.

## Notes

- The notebook demonstrates both knowledge extraction from text and graph-based QA.
- You can adapt the code to your own datasets and questions.
- For more on LangChain graph features, see the [LangChain Graph Documentation](https://python.langchain.com/docs/integrations/graph/).

---

*This project showcases advanced graph-based retrieval-augmented generation using LangChain, Neo4j, and Groq LLMs.*