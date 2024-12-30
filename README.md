# Rag_conversation_with_pdf_and_chat_history
 This repository provides a Streamlit-based interface for performing conversational retrieval-augmented generation (RAG) on PDF documents. Users can upload PDF files, ask questions about their content, and interact with the data through a chat interface. The project incorporates chat history for a more context-aware conversational experience.

# Features

**1. PDF Upload and Parsing**
 - Users can upload multiple PDF files through the web interface.
 - Extracts and processes the content of uploaded PDFs using PyPDFLoader.

**2. Text Splitting and Embeddings**
 - Splits extracted document content into manageable chunks using RecursiveCharacterTextSplitter.
 - Generates embeddings for these chunks using HuggingFaceEmbeddings with the all-MiniLM-L6-v2 model.

**3. Vector Store Creation**
 - Stores document chunks and their embeddings in a FAISS vector store for efficient retrieval.

**4. History-Aware Question Retrieval**
 - Utilizes create_history_aware_retriever to contextualize user queries based on chat history.
 - Reformulates queries for better understanding without relying solely on chat context.

**5. Conversational Question-Answering**
 - Retrieves relevant document chunks and formulates concise answers.
 - Uses a system prompt to ensure accurate and focused responses.

**6. Session Management**
 - Tracks chat history for each session using ChatMessageHistory.

**7. Streamlit Integration**
 - Provides an interactive and user-friendly web interface with Streamlit.

## Features include:
 - PDF upload functionality.
 -  Input for Groq API Key to access LLM capabilities.
 - Text input for asking questions and receiving answers.

# Usage
 - Open the Streamlit app in your browser.
 - Enter your Groq API Key
 - Upload one or more PDF files
 - Ask questions about the uploaded content in the chat input
 - View responses and chat history

# Key Components

## Functions

**PDF Processing:**

 - **PyPDFLoader:** Loads and processes the content of PDF files.

 - **RecursiveCharacterTextSplitter:** Splits document text into smaller chunks for embedding.

**Retrieval and Embedding**

 - **HuggingFaceEmbeddings:** Generates embeddings for text chunks.

 - **FAISS:** Creates a vector store for document retrieval.

# Conversational AI:

 - **create_history_aware_retriever:** Contextualizes user queries based on chat history.

 - **create_stuff_documents_chain:** Combines retrieved documents for generating answers.
 - **RunnableWithMessageHistory:** Manages chat history and chains for seamless interactions.

# Prompts

 - **Query Reformulation Prompt:** Reformulates user questions to be standalone.

 - **Answer Prompt:** Provides concise, accurate answers to user questions.

# Dependencies
 - Streamlit
 - LangChain
 - FAISS
 - HuggingFace Embeddings
 - PyPDFLoader
 - dotenv

# Environment Variables

 - **HF_TOKEN:** Hugging Face API token for embedding generation.

 - **Groq API Key:** Provided during runtime for accessing LLM capabilities.
