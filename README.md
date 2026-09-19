# GenAI on Databricks

**Build, evaluate, and deploy LLM applications with Mosaic AI**

Hands-on course materials for building a complete Generative AI application on Databricks — from data ingestion and embeddings, to a RAG pipeline, to a tool-calling agent, and finishing with evaluation using MLflow. You'll write real code in Databricks notebooks, trace runs with MLflow, and score output quality with LLM judges.

This repository accompanies the O'Reilly live event [**GenAI on Databricks**](https://learning.oreilly.com/live-events/genai-on-databricks/0642572365936/), taught by [Farah Abdou](https://learning.oreilly.com/live-events/genai-on-databricks/0642572365936/).

> These notebooks are meant to be **run cell by cell, not "Run All."** Along the way you'll be sent into the Databricks UI itself — Catalog Explorer, Compute, Serving, Experiments — so the platform tour isn't just code, it's clicking around too.

---

## What you'll learn

- Build a **RAG pipeline** on Databricks using Vector Search, Delta tables, and Unity Catalog for data governance
- Develop an **LLM agent** with tool-calling capabilities and a ReAct-style reasoning loop
- Evaluate **GenAI application quality** using MLflow tracing, LLM judges, and custom evaluation metrics
- Use MLflow to **trace, score, and interpret** the behavior of your GenAI application

---

## Course modules

### [Module 1 — Setup and Foundations](./Module%201%20-%20Setup%20and%20Foundations.ipynb)
GenAI on Databricks: the full stack. Configure the workspace with widgets, confirm compute and permissions, create the Unity Catalog objects (catalog, schema, volume) used throughout the course, turn on MLflow tracing, build a reusable client for querying Unity Gateway model services, and make your first traced LLM call.

### [Module 2 — Building a RAG Pipeline](./Module%202%20-%20Building%20RAG%20Pipeline.ipynb)
Ingest → Parse → Chunk → Embed → Index → Retrieve. Parse a PDF into structure, chunk it with change data feed enabled, create a Vector Search endpoint and index, watch the index sync live, run semantic search, and wire retrieval + generation into a single traced RAG chain.

### [Module 3 — From RAG to Agents](./Module%203%20-%20From%20RAG%20to%20Agents.ipynb)
Upgrade the RAG pipeline into an agent. Build an orders Delta table, add two tools (a SQL lookup and the retriever), configure the agent's tool-calling loop, and test multistep queries end-to-end — including cases where the agent must read a tool error and correct itself, and where one tool's input depends on another tool's output.

### [Module 4 — Evaluating GenAI Quality](./Module%204%20-%20Evaluating%20GenAI%20Quality.ipynb)
Why evaluation is the hardest part. Set up MLflow tracing, write test cases, build LLM judges (Guidelines-based) plus custom code checks the LLM can't do for you, run the evaluation, read the results, add a judge that reads the *trace* rather than the answer, and optionally record human feedback.

---

## Prerequisites

- A **Databricks account** — a free 14-day trial includes full access to all platform features used in this course
- **Intermediate Python** (comfortable with functions, classes, and working with APIs)
- **Basic familiarity with the Databricks workspace** (creating clusters, running notebooks)
- An understanding of **ML fundamentals** (training, evaluation, model lifecycle)
- Basic awareness of **GenAI concepts** (LLMs, prompts, embeddings)

---

## Getting started

1. **Clone this repository** (or download it) and import the notebooks into your Databricks workspace.
   ```bash
   git clone <your-repo-url>
   ```
2. In Databricks, go to **Workspace → Import** and upload the four `.ipynb` files (or connect this repo via **Repos / Git folders**).
3. Attach each notebook to a cluster with a recent Databricks Runtime (ML).
4. Open **Module 1** first and run it **cell by cell** — later modules reuse the catalog, schema, and configuration created there.

> Configuration is driven by notebook **widgets** (catalog, schema, volume, and chat model endpoint). Adjust these at the top of Module 1 to match your workspace, then re-run from that point.

---

## Tech stack

- **Databricks Mosaic AI** — Model Serving & Unity Gateway (`system.ai` chat models)
- **Unity Catalog** — governance for catalogs, schemas, volumes, and tables
- **Delta Lake** — storage for raw docs, chunks, and the orders table (with Change Data Feed)
- **Databricks Vector Search** — embeddings index and semantic retrieval
- **MLflow** — tracing, evaluation datasets, LLM judges, and human feedback

---

## Instructor

**Farah Abdou** is a lead machine learning engineer who specializes in end-to-end ML and NLP pipelines on cloud data platforms. She builds production data and AI systems using Databricks, MLflow, and Python. Farah created *The AI Language Gap*, an open research project measuring AI model performance across languages. She has spoken at Microsoft's Azure Cosmos DB Conf three consecutive years (2024–2026) and has published technical articles for Alibaba Cloud, Real Python, and the Microsoft Tech Community. She's also an IBM Champion and Alibaba Cloud MVP.

---

## License

Provided for educational use alongside the O'Reilly live event. See the event page for details.
