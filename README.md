# RAG Assignment – Small Data

**An AI-powered Retrieval-Augmented Generation (RAG) workflow using n8n, Ollama, and Supabase Vector Store.**

## 📌 Project Overview

This project implements a Retrieval-Augmented Generation (RAG) system to retrieve relevant information from stored documents and generate AI-powered answers. The workflow integrates a vector database with a local language model and automatically sends generated answers via email.

The project demonstrates how AI can use external knowledge sources to provide context-aware responses instead of relying only on the language model's internal knowledge.

## 🎯 Objectives

- Build a RAG workflow using n8n.
- Extract and process documents for knowledge retrieval.
- Generate embeddings and store document vectors in Supabase Vector Store.
- Use Ollama as the chat model for generating answers.
- Automate email delivery of AI-generated responses.
- Explore how small datasets can support AI-powered question answering.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| Ollama | Local language model and embedding integration |
| Supabase Vector Store | Store and retrieve document embeddings |
| Google Drive | Source of documents for ingestion |
| Gmail / SMTP | Deliver AI-generated answers by email |
| RAG | Retrieve relevant context before generating answers |

## 🔄 Workflow Architecture

### 1. Document Ingestion

- Google Drive Trigger detects the source file.
- Download File retrieves the document.
- Extract from File extracts its text content.
- Default Data Loader and Recursive Character Text Splitter prepare the text for processing.
- An embedding model converts text into vector representations.
- Supabase Vector Store stores the document vectors for retrieval.

### 2. Question Answering

- When Chat Message Received starts the interaction.
- AI Agent processes the user's question.
- Ollama Chat Model generates the answer.
- Supabase Vector Store retrieves relevant information from the indexed knowledge base.
- The AI Agent uses the retrieved context to formulate a response.

### 3. Email Automation

- Edit Fields prepares the generated answer.
- Send an Email sends the answer to the configured recipient through SMTP.
- The workflow returns the email delivery result.

## 🧪 Testing and Results

The email delivery workflow was tested successfully.

**Test configuration:**
- Email subject: `RAG Assignment - Small Data`
- Recipient: `apichaya@kbu.ac.kr`
- Email format: Text
- Result: SMTP accepted the message for delivery.
- Message content: An AI-generated answer about small data and its potential benefits.

The test confirms that the email-sending node executed successfully. The message was subsequently found in Gmail's Spam folder, so additional email configuration or spam troubleshooting may be needed.

## 🚀 How to Run

1. Install and configure n8n.
2. Install and configure Ollama with the required chat and embedding models.
3. Create a Supabase project and configure the vector store.
4. Connect Google Drive credentials if using document ingestion.
5. Configure the email credentials and recipient address in the Send an Email node.
6. Import or recreate the workflow in n8n.
7. Execute the document ingestion workflow to index the source documents.
8. Run the chat workflow, submit a question, and verify the generated answer.
9. Check the configured recipient's Inbox and Spam folders for the email.

## 🔐 Security Notes

- Do not commit API keys, SMTP passwords, access tokens, or credentials to GitHub.
- Use environment variables or n8n credentials to store sensitive information.
- Remove personal email addresses and other private information from public screenshots and workflow exports when appropriate.

## 📚 Conclusion

This project demonstrates the integration of document processing, vector search, AI-generated responses, and email automation in a single n8n workflow. It provides a practical example of how RAG can connect a language model with external knowledge and automate the delivery of useful information.

## 👩‍💻 Author

**Apichaya Saensiri**

Project: RAG Assignment – Small Data

GitHub Repository: https://github.com/apcyssr/n8n-rag-midterm
