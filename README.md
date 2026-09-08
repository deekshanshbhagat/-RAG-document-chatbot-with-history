# Conversational RAG Chatbot with PDF Uploads and Chat History

This project is a conversational RAG (Retrieval-Augmented Generation) chatbot that allows you to chat with your PDF documents. It maintains chat history, enabling it to understand context from the ongoing conversation.

The application is built using Streamlit, LangChain, Groq for language-model inference, and Hugging Face for text embeddings.

## Features

- **PDF Document Upload:** Upload one or more PDF files to use as the chatbot's knowledge base.
- **Conversational Interface:** Interactive chat interface powered by Streamlit.
- **Chat History:** Maintains previous conversation turns for context-aware responses.
- **Retrieval-Augmented Generation:** Retrieves relevant information from uploaded documents before generating responses.
- **Fast LLM Inference:** Uses the Groq API for language-model inference.
- **Text Embeddings:** Uses Hugging Face's `all-MiniLM-L6-v2` model for generating embeddings.
- **Session Management:** Supports different chat sessions using unique session IDs.

## How It Works

1. **PDF Processing:** Uploaded PDF files are processed and their text is extracted.
2. **Text Splitting and Embedding:** The extracted text is split into smaller chunks, and each chunk is converted into an embedding using a Hugging Face model.
3. **Vector Storage:** The embeddings are stored in a Chroma vector store for efficient retrieval.
4. **History-Aware Retrieval:** Chat history is used to reformulate follow-up questions into standalone queries.
5. **Question Answering:** Relevant document chunks are retrieved and passed to the language model along with the conversation context.
6. **Response Generation:** The model generates a concise answer based on the retrieved context.

## Setup and Installation

### 1. Create a virtual environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set up environment variables

Create a `.env` file in the project folder and add your Hugging Face API key:

```env
HF_API_KEY="your_hugging_face_api_key"
```

Keep your API keys private and do not share the `.env` file.

## Usage

Start the application with:

```bash
streamlit run app.py
```

Then:

1. Open the application in your browser.
2. Enter your Groq API key.
3. Upload one or more PDF files.
4. Ask questions about your documents.
5. Continue the conversation using follow-up questions.

## Project Structure

```text
RAG-document-chatbot-with-history/
│
├── app.py
├── README.md
└── requirements.txt
```

## Dependencies

- Streamlit
- LangChain
- Groq
- Hugging Face
- ChromaDB
- PyPDF
- python-dotenv

## Future Improvements

- Persistent vector storage
- Support for additional document formats
- Source citations for retrieved document chunks
- Streaming responses
- Improved chat-session management
- Cloud deployment

## License

This project is available for educational and portfolio purposes.
