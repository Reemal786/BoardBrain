# 🎲 BoardBrain — AI Board Game Rules Assistant

**BoardBrain** is an AI-powered board game assistant that answers natural language questions about game rules using **Retrieval-Augmented Generation (RAG)**.

Instead of searching through an entire rulebook during game night, users can ask BoardBrain a question and receive an answer grounded in the official rule documents.

> Because "just read the rulebook" isn't always helpful at 11 PM on game night.

## 🎯 Purpose

Board game rulebooks can be lengthy and difficult to search when players need an answer to one specific question.

RulesBot explores how **Retrieval-Augmented Generation and semantic search** can make those documents easier to navigate. Instead of manually searching through pages of rules, players can ask a question and retrieve information relevant to the situation.

The project also demonstrates the core components of a RAG system: **document chunking, embeddings, vector storage, semantic retrieval, context construction, and LLM-based response generation**.

## ✨ Features

* **Natural Language Q&A** — Ask questions about board game rules conversationally
* **Semantic Search** — Finds relevant rule passages based on meaning rather than exact keyword matches
* **RAG Pipeline** — Retrieves relevant context before generating an answer
* **Vector Search** — Stores and searches document embeddings using ChromaDB
* **Grounded Responses** — Generates answers using retrieved rulebook content
* **Multiple Games** — Search rules across several popular board games
* **Interactive Interface** — Simple Gradio interface for asking questions

## 🎮 Supported Games

| Game           | Rulebook             |
| -------------- | -------------------- |
| Catan          | `catan.txt`          |
| Clue           | `clue.txt`           |
| Codenames      | `codenames.txt`      |
| Monopoly       | `monopoly.txt`       |
| Pandemic       | `pandemic.txt`       |
| Risk           | `risk.txt`           |
| Ticket to Ride | `ticket_to_ride.txt` |
| Uno            | `uno.txt`            |

## 🧠 How It Works

BaordBrain uses a RAG pipeline to retrieve information from board game rulebooks before generating an answer.

```text
             Board Game Rulebooks
                      │
                      ▼
              Document Chunking
                      │
                      ▼
              Generate Embeddings
                      │
                      ▼
                  ChromaDB
                      │
                      │
User Question ────────┘
      │
      ▼
Generate Query Embedding
      │
      ▼
 Semantic Similarity Search
      │
      ▼
 Relevant Rule Passages
      │
      ▼
        LLM
      │
      ▼
Grounded Rules Answer
```

### 1. Document Ingestion

Board game rulebooks are loaded from the `docs/` directory and divided into smaller chunks that can be searched efficiently.

### 2. Embeddings

Each rulebook chunk is converted into a vector embedding using a **SentenceTransformer** model.

These embeddings represent the semantic meaning of each passage rather than relying only on exact keyword matches.

### 3. Vector Storage

The document embeddings and their associated text are stored in **ChromaDB** for efficient similarity search.

### 4. Retrieval

When a user asks a question, BoardBrain converts the query into an embedding and searches ChromaDB for the most semantically relevant passages from the rulebooks.

### 5. Response Generation

The retrieved passages are provided to the LLM as context along with the user's question.

The model then generates an answer based on the retrieved rule information rather than relying solely on its existing knowledge.

## 🛠️ Tech Stack

**Language**

* Python

**AI & Retrieval**

* Retrieval-Augmented Generation (RAG)
* SentenceTransformers
* Vector Embeddings
* Semantic Search
* LLMs

**Database**

* ChromaDB

**LLM API**

* Groq

**Interface**

* Gradio

## 🔮 Future Improvements

* Allow users to upload their own rulebooks
* Support PDF rulebooks
* Add citations to specific rulebook sections
* Filter questions by individual game
* Add conversation history for follow-up questions
* Expand the collection of supported games
* Improve retrieval evaluation and relevance scoring
* Add support for comparing rules across different games

## 👩‍💻 Author

**Reemal Hoor**
Computer Engineering
