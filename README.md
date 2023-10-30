# OpenRAG

OpenRAG aims to implement a variety of RAG (Retriever-Augmented Generation) recipes, making them easily accessible as plug-and-play solutions.

## Structure of RAG
RAG is structured around four primary steps: Data Ingestion, Indexing, Retrieval, and Generation. Each step offers multiple design choices to consider.

### 1. Data Ingestion
Methods and processes to import data.
- **Data Sources**: Determining origins like databases, files, APIs, and web scraping.
- **Formats & Modality**: 
  - **Formats**: Handling various data formats such as CSV, JSON, XML, Parquet, Articles, Books, PDFs, SQL, and more.
  - **Modality**: Types of data including Text, Images, Audio, Video, or a mix.
- **Data Transformation**: Converting data for suitable destinations, including cleaning, filtering, aggregating, and joining tasks.
- **Domain**: Categories like General, Code, Med, and Food.

### 2. Data Indexing
Decisions to consider:
- **2.1. Database Selection**: Should we opt for only a vector database, or both vector and keyword-based databases?
- **2.2. Vector Database Choice**: Options include Qdrant, Chroma, Meilisearch, and more.
- **2.3. Document Vectorization**: How should we create vectors for documents? Do we choose single or multiple vectors per document? If multiple, how should a document be split? Should we interleave vectors? Would it be usefule to summarize documents, then index the summary?
- **2.4. Vector Embedding Model**: Which model should we use for vector embeddings? Is it necessary to finetune the embedding model?
- **2.5. Vector Types**: Should we use quantized or non-quantized vectors? Do we opt for exact vector searches or approximate methods?

### 3. Retrieval
Decisions to consider:
- **3.1. Database Query Formation**: Given a user query, how should we construct a database query? Should it be used as-is, or should an LLM (Language Model) assist in generating the database query/queries based on the user input?
- **3.2. Result Ensembling**: If utilizing both vector and keyword-based databases, how should we ensemble the results for optimal relevance?
- **3.3. Result Reranking**: What strategy should be employed to rerank results? How many of these results should be incorporated into the LLM's context?

### 4. Generation
Decisions to consider:
- **4.1. LLM Selection**: Which LLM should we employ? What should be the prompt structure?
- **4.2. Hallucination Prevention**: How can we ensure the LLM isn't producing false or "hallucinated" information?

## Implementation Considerations
- **Ready-made Solutions**: Should we use pre-existing tools like privateGPT, or develop from scratch?
- **Frameworks**: Should we implement with or without tools such as Langchain or Llama index?
- **Dspy & ColBert Utilization**: How can Dspy and ColBert be integrated into our implementation?
