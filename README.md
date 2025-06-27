# AutoSmart RAG: Self-Correcting AI Search and Reasoning

A sophisticated Retrieval-Augmented Generation (RAG) system that combines web scraping, vector embeddings, and self-correcting local LLM reasoning to provide accurate, contextual answers to user queries.

## Features

- Real-time Web Scraping: Intelligently scrapes news sources and web content
- Vector Database Storage: Efficient storage and retrieval using ChromaDB or FAISS
- Self-Correcting Reasoning: Two-stage local LLM processing for improved accuracy
- Smart Caching: Reduces redundant scraping with intelligent cache management
- Multi-source Support: Prioritizes trusted news sources (BBC, ABC News, NYTimes)
- Flexible Configuration: Easily customizable parameters and models
- Comprehensive Logging: Efficient progress tracking

## Project Flow

```
Query → Web Scraping → Text Chunking → Embedding → Vector DB → Retrieval → Local LLM Reasoning → Self-Correction → Final Answer
```

## How to Run

### Prerequisites

- Python 3.8+
- Ollama (for Local LLM inference)
- Chrome/Chromium browser (for Selenium web scraping)

### Usage

1. Clone this repository on your local machine.
2. Install the required dependencies:
   ```bash
   pip install numpy pandas torch faiss-cpu chromadb sentence-transformers selenium webdriver-manager requests aiohttp beautifulsoup4 nltk transformers ollama tqdm
   ```
3. Install and setup Ollama, and run the LLM:
   ```bash
   # Install Ollama (visit https://ollama.ai)
   # Pull the required model
   ollama run deepseek-r1:14b
   ```
4. Open and run the `AutoSmart RAG.ipynb` Jupyter Notebook.

## System Components

### 1. Web Scraper
- Supports both requests and Selenium-based scraping
- Intelligent fallback mechanisms
- Caching system to avoid redundant requests
- Prioritizes trusted news sources

### 2. Text Chunker
- Sentence-aware text chunking
- Configurable chunk size and overlap
- Token-based chunking using transformers tokenizer
- Metadata preservation

### 3. Embedding Manager
- Uses SentenceTransformers for text embeddings
- Batch processing for efficiency
- GPU/MPS support for faster inference

### 4. Vector Database
- Supports ChromaDB (persistent) and FAISS (in-memory)
- Cosine similarity search
- Duplicate detection and filtering
- Configurable similarity thresholds

### 5. DeepSeek LLM
- Integrates with Ollama for local LLM inference
- Handles model availability checking
- Timeout and retry mechanisms
- Supports various DeepSeek model variants

### 6. RAG Reasoner
- Orchestrates the entire pipeline
- Two-stage reasoning process
- Self-correction mechanism
- Comprehensive error handling

## Performance Features

- Caching: Intelligent caching system reduces scraping overhead
- Batch Processing: Efficient embedding generation
- Async Operations: Non-blocking web scraping and processing
- Resource Management: Automatic cleanup and memory management

## Contributing

Contributions are welcome!

## License

Distributed under the MIT License.  
