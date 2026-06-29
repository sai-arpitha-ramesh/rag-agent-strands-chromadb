# rag-agent-strands-chromadb
RAG Agent built with Strands Agents SDK, ChromaDB, AWS Bedrock and Qwen3 embeddings for document Q&amp;A

# RAG Agent with Strands Agents, ChromaDB & AWS Bedrock

A production-style Retrieval-Augmented Generation (RAG) agent 
built from scratch for document Q&A.

## What This Project Does
Upload any PDF document and ask questions about it in natural 
language. The agent retrieves the most relevant sections from 
the document and generates accurate, cited answers using Claude 
on AWS Bedrock.

## Architecture
- **Embedding Model**: Qwen3-Embedding-0.6B (via SentenceTransformers)
- **Vector Database**: ChromaDB with cosine similarity search
- **Document Parser**: Docling (PDF → Markdown)
- **Chunking**: Chonkie RecursiveChunker
- **Agent Framework**: AWS Strands Agents SDK
- **LLM**: Claude Sonnet (via AWS Bedrock)
- **Platform**: Google Colab (T4 GPU)

## How It Works
1. PDF uploaded and parsed into markdown using Docling
2. Document split into semantic chunks using Chonkie
3. Chunks embedded using Qwen3 and stored in ChromaDB
4. User query embedded and matched against stored vectors
5. Top relevant chunks retrieved and injected into agent context
6. Claude generates a grounded, cited answer via AWS Bedrock

## Key Concepts Demonstrated
- Retrieval Augmented Generation (RAG) pipeline end to end
- Vector embeddings and semantic similarity search
- Custom Strands tool creation with @tool decorator
- AWS Bedrock integration with Strands Agents SDK
- Persistent vector database with ChromaDB
- PDF parsing and intelligent document chunking

## Setup
1. Open the notebook in Google Colab
2. Add AWS credentials to Colab Secrets:
   - AWS_ACCESS_KEY_ID
   - AWS_SECRET_ACCESS_KEY  
   - AWS_DEFAULT_REGION
3. Run all cells in order
4. Upload your PDF when prompted
5. Ask questions about your document

## Sample Output
**Query**: Is AI helping skill formation or not?

**Agent Response**: Based on the retrieved documents, AI has a 
mixed impact on skill formation. The research found that using 
AI to complete tasks reduces skill formation when participants 
delegate thinking entirely. However, participants who used AI 
for conceptual explanations showed high skill retention...
