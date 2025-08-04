# Enhanced Chatbot with RAG for Google Colab

![Chatbot Demo](https://img.shields.io/badge/Demo-Live-success) ![Python](https://img.shields.io/badge/Python-3.8%2B-blue) ![License](https://img.shields.io/badge/License-MIT-green)

An advanced chatbot with Retrieval-Augmented Generation (RAG) capabilities designed specifically for Google Colab, featuring PDF processing, conversation history, and user profiles.

## Features

- **Natural Language Conversations**: Powered by Groq's ultra-fast LLMs
- **PDF Processing**: Upload and query PDF documents
- **Conversation Memory**: Maintains context across sessions
- **User Profiles**: Personalized experience with name and interests
- **Interactive Interface**: User-friendly Colab widgets interface
- **Search Capabilities**: Find past conversations easily
- **Multiple Sessions**: Organize different topics separately

## Setup Instructions

1. **Get a Groq API Key**:
   - Visit [Groq Cloud](https://console.groq.com/) and get your API key
   - Add it to the `Config` class in the notebook

2. **Run in Google Colab**:
   - Open the notebook in Google Colab
   - Run all cells or just the quick start function:

3. **First Run**:
   - The chatbot will prompt you for:
     - Your name
     - Your interests (comma separated)
   - This creates your user profile

## Usage

### Basic Chatting
- Type your message in the input box at the bottom
- Click "Send" or press Ctrl+Enter to submit

### Advanced Features
- **Upload PDFs**: Click "Upload PDF" to add documents to the knowledge base
- **View Sessions**: Click "Sessions" to see your conversation history
- **Search**: Use the search bar to find past messages
- **New Session**: Start fresh conversations with "New Session"
- **Profile**: View your profile information

## Technical Details

### Key Components
- **Database**: SQLite for conversation history and user profiles
- **Vector Store**: ChromaDB for document embeddings
- **Embeddings**: Sentence Transformers (`all-MiniLM-L6-v2`)
- **LLM**: Groq's Gemma2-9b-it model

### Configuration
Modify these in the `Config` class:
```python
class Config:
    GROQ_API_KEY = "your_key_here"  # Required
    CHAT_MODEL = "gemma2-9b-it"
    EMBEDDING_MODEL = "all-MiniLM-L6-v2"
    MAX_CONTEXT_MESSAGES = 20
    MAX_PDF_CHUNK_SIZE = 1000
