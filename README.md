# AI Agent RAG Workflow - n8n

## Midterm Assignment

This project is an AI Agent RAG workflow created using n8n.

The workflow demonstrates the process of collecting PDF documents from Google Drive, extracting text, splitting the text into chunks, generating embeddings, and storing the documents in a Supabase Vector Database.

## Workflow

The current workflow follows these steps:

1. **Google Drive Trigger**
   - Detects when a new PDF file is uploaded to a specific Google Drive folder.

2. **Download File**
   - Downloads the uploaded PDF file from Google Drive.

3. **Extract from File**
   - Extracts text content from the PDF document.

4. **Default Data Loader**
   - Loads the extracted document data.

5. **Recursive Character Text Splitter**
   - Splits the document into smaller text chunks.

6. **Embeddings Ollama**
   - Generates vector embeddings using the local `nomic-embed-text` model.

7. **Supabase Vector Store**
   - Stores the text chunks and their embeddings in the Supabase `documents` table.

## Technologies

- n8n
- Google Drive
- Ollama
- nomic-embed-text
- Supabase Vector Database

## Database

The extracted document chunks and their embeddings are stored in a Supabase table named:

`documents`

The embedding vector dimension is **768**, corresponding to the `nomic-embed-text` model.

## Project Structure

```text
n8n-rag-midterm/
├── README.md
└── workflow/
    └── AI-Agent-RAG-Workflow.json
