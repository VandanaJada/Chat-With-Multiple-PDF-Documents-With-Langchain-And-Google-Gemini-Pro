# Chat PDF with Gemini

A web application built using **Streamlit** that allows users to interactively chat with uploaded PDF files by leveraging **Google's Generative AI** and **FAISS** for semantic search and conversational AI capabilities.

---

## Features

- **PDF Upload and Processing**: Users can upload multiple PDF files, and their contents are processed for semantic search.
- **Text Chunking**: Handles large PDFs by splitting the text into manageable chunks using `RecursiveCharacterTextSplitter`.
- **Vector Embedding Storage**: Uses FAISS to create and manage vector embeddings for efficient similarity searches.
- **Generative AI Integration**: Employs Google Generative AI for generating contextual and accurate answers to user queries.
- **Interactive Chat**: Users can ask questions about the uploaded PDFs and get detailed responses based on the document context.

---

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   
2. Install dependencies:

bash
Copy code
pip install -r requirements.txt

3. Set up environment variables:

Create a .env file in the root directory.
Add your Google API key:
env
Copy code
GOOGLE_API_KEY=your_google_api_key

4.Run the app:

bash
Copy code
streamlit run app.py

Usage
Upload PDFs: Use the sidebar to upload one or more PDF files.
Process Files: Click the "Submit & Process" button to process the uploaded files.
Ask Questions: Enter your question in the main input field, and the app will generate an answer based on the context of the uploaded PDFs.
Code Overview
Key Functions
get_pdf_text(pdf_docs)

Extracts text from the uploaded PDF files.
Input: List of uploaded PDFs.
Output: Combined text from all PDF pages.
get_text_chunks(text)

Splits the extracted text into smaller chunks for better processing.
Input: Raw text.
Output: List of text chunks.
get_vector_store(text_chunks)

Creates vector embeddings using Google Generative AI and stores them locally with FAISS.
Input: List of text chunks.
Output: Saves the vector store locally.
get_conversational_chain()

Initializes a conversational chain using Google Generative AI with a custom prompt template.
Output: Chain object ready for answering questions.
user_input(user_question)

Handles user queries by retrieving relevant document chunks and generating a response.
Input: User's question.
Output: AI-generated response displayed on the app.
main()

The main function that handles the Streamlit interface and user interactions.
Dependencies
Streamlit: For the web interface.
PyPDF2: To extract text from PDF files.
LangChain: To handle text processing and chaining.
FAISS: For similarity search and vector management.
Google Generative AI: For embeddings and conversational AI.
dotenv: To manage API keys and environment variables.

Screenshots
Home Page: 
![image](https://github.com/user-attachments/assets/010d7ccb-1a34-4470-bdc2-59e044f1820e)
