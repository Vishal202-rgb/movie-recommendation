# 🎬 Movie Recommendation System using GraphRAG, Neo4j & Pinecone

A hybrid **Graph + Vector Retrieval (GraphRAG)** based Movie Recommendation System that understands natural language queries, extracts entities, traverses knowledge graphs, and retrieves semantic information using embeddings.

The system combines the power of **Neo4j Graph Database** and **Pinecone Vector Database** to provide intelligent movie recommendations and relationship-based answers.

---

## 🚀 Features

- 📄 Parse movie dataset from PDF
- ✂️ Split documents into semantic chunks
- 🧠 Generate embeddings for each chunk
- 🌲 Store embeddings in **Pinecone Vector Database**
- 🕸️ Build a **Knowledge Graph** in **Neo4j**
- 🔍 Entity extraction from user queries
- 🎯 Entity resolution using graph matching
- 🤖 Automatic query classification
- 📚 Graph-based relationship reasoning
- 🔗 Vector similarity search
- 💬 Natural language movie recommendation
- 🎭 Discover relationships between actors, directors, genres, and movies

Example queries:

```
Recommend sci-fi movies like Interstellar

Who directed Inception?

Show movies starring Leonardo DiCaprio

How is Tom Hardy connected to Leonardo DiCaprio?

Recommend action movies released after 2018
```

---

# 🏗️ Architecture

```
                +----------------------+
                |    movies.pdf        |
                +----------+-----------+
                           |
                           v
                 PDF Parsing & Chunking
                           |
                 +---------+---------+
                 |                   |
                 v                   v
         Generate Embeddings     Extract Entities
                 |                   |
                 v                   v
      Pinecone Vector DB      Neo4j Graph Database
                 |                   |
                 +---------+---------+
                           |
                           v
                 Query Classification
                           |
             +-------------+-------------+
             |                           |
             v                           v
      Vector Retrieval            Graph Traversal
             |                           |
             +-------------+-------------+
                           |
                           v
                  Final AI Generated Answer
```

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| JavaScript (Node.js) | Backend |
| Neo4j | Graph Database |
| Pinecone | Vector Database |
| Google Gemini | LLM & Embeddings |
| GraphRAG | Hybrid Retrieval |
| PDF Parser | Document Processing |
| LangChain Components | Embedding & Retrieval Pipeline |

---

# 📂 Project Structure

```
MovieRecommendation/
│
├── data/
│   └── movies.pdf
│
├── pdfParser.js
├── entityExtractor.js
├── entityResolver.js
├── graphBuilder.js
├── graphHandler.js
├── factualHandler.js
├── descriptiveHandler.js
├── queryPlanner.js
├── queryClassifier.js
├── cypherTemplates.js
├── config.js
├── runIndexing.js
│
├── package.json
└── README.md
```

---

# ⚙️ Workflow

## 1. Document Processing

- Load `movies.pdf`
- Extract text
- Split into chunks
- Clean and preprocess data

## 2. Vector Indexing

- Generate embeddings
- Store vectors in Pinecone
- Enable semantic similarity search

## 3. Graph Construction

- Extract entities (Movies, Actors, Directors, Genres)
- Create nodes and relationships
- Store graph in Neo4j

## 4. User Query Processing

When a user asks:

```
How is Tom Hardy connected to Leonardo DiCaprio?
```

Pipeline:

```
User Query
     │
     ▼
Entity Extraction
     │
     ▼
Entity Resolution
     │
     ▼
Query Classification
     │
     ▼
Graph Traversal (Neo4j)
     │
     ▼
Relationship Discovery
     │
     ▼
Final Response
```

---

# 🖥️ Sample Terminal Output

```
You: how is Tom Hardy connected to Leonardo DiCaprio

🔍 ENTITY RESOLUTION

Step 1: Extracting entities...
Found:
- Tom Hardy
- Leonardo DiCaprio

Step 2: Resolving entities...

✓ Tom Hardy -> Actor
✓ Leonardo DiCaprio -> Actor

CLASSIFICATION

Type: graph

Reason:
The user is asking for a relationship between two actors,
which requires graph traversal in Neo4j.

Generating response...
```

---

# 📊 Why Hybrid Retrieval?

## 🔹 Neo4j Graph Database

Best for:

- Actor ↔ Movie relationships
- Director ↔ Movie links
- Multi-hop reasoning
- Connection discovery
- Structured queries

Example:

```
Tom Hardy
      │
 acted_in
      │
 Inception
      │
 acted_in
      │
 Leonardo DiCaprio
```

---

## 🔹 Pinecone Vector Database

Best for:

- Semantic search
- Similar movie recommendations
- Context retrieval
- Embedding-based matching
- Natural language understanding

Example:

```
User:
"I want emotional space exploration movies"

↓

Embedding Search

↓

Interstellar
The Martian
Gravity
Arrival
```

---

# 📦 Installation

```bash
git clone <repository-url>

cd MovieRecommendation

npm install
```

---

# ▶️ Run the Project

```bash
node runIndexing.js
```

Then interact with the system through the terminal by entering natural language movie queries.

---

# 🔮 Future Improvements

- 🎨 Web-based UI
- 🎙️ Voice query support
- 👤 Personalized recommendations
- ⭐ User ratings integration
- 🎞️ TMDB/IMDb API integration
- 📈 Recommendation explanations
- 🌍 Multi-language support

---

# 👨‍💻 Author

**Vishal Kumar**

Built as a GraphRAG-powered movie recommendation engine leveraging **Neo4j** for relationship reasoning and **Pinecone** for semantic vector search to deliver intelligent, context-aware movie insights.
