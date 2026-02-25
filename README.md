
# 🧠 AI-Powered SQL Chatbot with Few-Shot Learning

### End-to-End NL2SQL System using LLMs + PostgreSQL + Chinook Dataset

An intelligent Natural Language to SQL (NL2SQL) assistant that allows users to query a PostgreSQL database using plain English.

This project includes:

* Database ingestion pipeline (CSV → PostgreSQL)
* Semantic Few-Shot Retrieval
* LLM-based SQL generation (Gemini 2.5 Flash)
* Natural language analytical explanations
* Interactive Streamlit interface

---

# 🚀 Project Overview

This system transforms natural language questions into executable SQL queries over a real relational database.

Instead of writing SQL manually, users can ask:

> "Who are the top 5 customers by total spending?"

And the system will:

1. Retrieve similar examples using vector similarity
2. Generate accurate PostgreSQL SQL
3. Execute the query
4. Return results in table format
5. Provide a natural language explanation

---

# 📊 Dataset: Chinook Database

This project uses the **Chinook dataset**, a sample digital media store database commonly used for SQL practice.

It includes CSV files such as:

* `Album.csv`
* `Artist.csv`
* `Customer.csv`
* `Employee.csv`
* `Genre.csv`
* `Invoice.csv`
* `InvoiceLine.csv`
* `MediaType.csv`
* `Playlist.csv`
* `PlaylistTrack.csv`
* `Track.csv`

These files simulate a real-world relational business schema including:

* Customers
* Employees
* Sales
* Music tracks
* Playlists
* Invoices

---

# 🗄️ Data Ingestion Pipeline (`deploy.py`)

The project includes a deployment script that:

1. Reads all Chinook CSV files
2. Connects to PostgreSQL
3. Creates tables automatically
4. Uploads data using Pandas + SQLAlchemy
5. Verifies successful upload

### Technologies Used

* `pandas`
* `sqlalchemy`
* `psycopg2`

This makes the project fully reproducible from raw CSV files.

---

# 🏗️ System Architecture

```text
Chinook CSV Files
        ↓
deploy.py (CSV → PostgreSQL)
        ↓
PostgreSQL Database
        ↓
Schema Extraction (information_schema)
        ↓
Few-Shot Example Selector (FAISS)
        ↓
LLM (Gemini 2.5 Flash)
        ↓
Generated SQL Query
        ↓
Query Execution
        ↓
Natural Language Explanation
        ↓
Streamlit UI
```

---

# ✨ Key Features

## 🔹 1. Dynamic Schema Awareness

* Automatically extracts database schema
* Injects tables & columns into prompt
* Reduces hallucinated SQL

## 🔹 2. Semantic Few-Shot Retrieval

* Uses `SemanticSimilarityExampleSelector`
* FAISS vector search
* Retrieves top-K similar NL→SQL examples
* Improves generation accuracy

## 🔹 3. PostgreSQL-Optimized SQL Generation

* Enforces double-quoted identifiers
* SELECT-only safety guard
* Handles joins, aggregations, filters

## 🔹 4. Natural Language Analytical Responses

* Converts raw SQL results into insights
* Adds context (percentages, trends, comparisons)
* Clean formatting of numbers and dates

## 🔹 5. Production-Oriented Design

* Cached resources for performance
* Modular functions
* Environment-based configuration
* Error handling

---

# 🧰 Tech Stack

| Layer           | Technology           |
| --------------- | -------------------- |
| LLM             | Gemini 2.5 Flash     |
| Embeddings      | Google Embedding-001 |
| Framework       | LangChain            |
| Vector Store    | FAISS                |
| Backend         | Python               |
| Database        | PostgreSQL           |
| ORM             | SQLAlchemy           |
| Data Processing | Pandas               |
| UI              | Streamlit            |

---

# 📂 Project Structure

```text
├── app.py                 # Streamlit NL2SQL chatbot
├── deploy.py              # CSV → PostgreSQL ingestion script
├── fewshots.json          # NL → SQL training examples
├── Chinook/               # All Chinook CSV files
│   ├── Album.csv
│   ├── Artist.csv
│   ├── Customer.csv
│   └── ...
├── .env                   # API keys & DB config
├── requirements.txt
└── README.md
```

---

# ⚙️ Setup Instructions

## 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/sql-chatbot-llm.git
cd sql-chatbot-llm
```

---

## 2️⃣ Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows
```

---

## 3️⃣ Install Requirements

```bash
pip install -r requirements.txt
```

---

## 4️⃣ Configure Environment Variables

Create `.env` file:

```env
GOOGLE_API_KEY=your_google_api_key
DB_URL=postgresql://username:password@host:port/database
```

---

## 5️⃣ Load Chinook Data into PostgreSQL

Run:

```bash
python deploy.py
```

This will:

* Create tables
* Upload all CSV files
* Verify database connection

---

## 6️⃣ Run Streamlit App

```bash
streamlit run app.py
```

---

# 🧠 Example Questions

* Top 10 customers by revenue
* Monthly sales trend
* Best selling genres
* Average invoice value per country
* Employees ranked by sales performance
* Most purchased tracks

---

# 🔒 Safety Mechanisms

* SELECT-only enforcement
* SQL cleaning before execution
* Exception handling
* Empty-result smart responses

---

# 📈 Advanced Concepts Demonstrated

This project showcases:

* NL2SQL System Design
* Retrieval-Augmented Generation (RAG)
* Few-Shot Prompt Engineering
* Semantic Vector Search
* LLM-based Structured Output
* Data Engineering Pipelines
* LLM + Database Integration

---

# 🎯 Real-World Applications

* Enterprise BI Chatbots
* Internal Data Copilots
* Digital Transformation Analytics
* CX Analytics Assistants
* Executive Data Interfaces
* Self-Service Business Intelligence

---

# 👨‍💻 Author

**Mohamed Hamed**
AI Engineer | NLP & LLM Systems | Data Analytics

Specialized in:

* LLM Applications
* RAG Systems
* NL2SQL Agents
* Intelligent Data Platforms

---

# ⭐ Why This Project Matters

This is not a simple chatbot.

It is a complete AI data system combining:

* Data ingestion
* Vector retrieval
* Prompt engineering
* LLM reasoning
* Database querying
* Analytical explanation
* Interactive UI

It demonstrates production-level thinking in:

* AI Engineering
* Data Architecture
* Intelligent Analytics Systems
