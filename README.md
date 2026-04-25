# IN226021_Final_RAG_Project
RAG-Based Customer Support Assistant
A Retrieval-Augmented Generation (RAG) system that answers customer support queries from a PDF knowledge base using LangGraph, ChromaDB, and Groq's Llama 3.3. Unanswered queries are escalated to a human agent via HITL.

Features

PDF ingestion with semantic chunking
Vector search using ChromaDB and MiniLM embeddings
LLM-powered answer generation via Groq (free tier)
LangGraph workflow with conditional routing
Human-in-the-Loop escalation for out-of-scope queries
Gradio chat interface with public shareable link


Tech Stack
ComponentToolPDF LoaderPyMuPDFEmbeddingsall-MiniLM-L6-v2Vector StoreChromaDBLLMLlama 3.3 70B via GroqWorkflowLangGraphUIGradioRuntimeGoogle Colab

Setup
1. Clone or open the notebook in Google Colab
2. Upload your PDF knowledge base to the Colab files panel
3. Get a free Groq API key at console.groq.com
4. Run all cells top to bottom
5. Open the Gradio public URL from the Cell 10 output

How It Works
PDF → Chunk → Embed → ChromaDB
                          ↓
User Query → Retrieve → Generate → Router
                                  /      \
                             High        Low
                           Confidence  Confidence
                              ↓            ↓
                           Answer        HITL

Project Structure
notebook.ipynb       # All code — single Colab notebook
knowledge_base.pdf   # FAQ document used as knowledge base
