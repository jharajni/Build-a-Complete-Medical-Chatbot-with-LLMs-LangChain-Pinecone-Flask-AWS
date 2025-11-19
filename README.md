## Medical Chatbot

# Project Overview
This project is an end-to-end Medical Chatbot built using a Retrieval-Augmented Generation (RAG) pipeline that processes medical PDFs and delivers accurate, context-aware answers. The system uses LangChain’s PyPDFLoader to extract text from uploaded PDFs, followed by RecursiveCharacterTextSplitter to break the content into structured chunks (500-token size with 20-token overlap). These chunks are embedded using the HuggingFace Sentence Transformer – all-MiniLM-L6-v2, and the vector representations are stored in Pinecone for fast similarity search. User queries are also converted into embeddings using the same model, and Pinecone returns the top-matching chunks through a similarity retriever (k=3). The retrieved context is passed to the Gemini 2.5 Flash LLM via LangChain’s ChatGoogleGenerativeAI to generate accurate medical responses using a custom prompt-based create_stuff_documents_chain setup. The complete pipeline runs through a Flask backend, with a simple frontend interface allowing users to upload PDFs, ask questions, and receive AI-generated answers in real time. This architecture ensures reliable, grounded, and efficient medical information retrieval from custom documents.

# Features

 Text Extraction & Storing the Vector Embedding : Extracts and chunks text from PDF pages then by using Embedding Model to generate vector embedding to store in Pinecone Vector DB for subsequent semantic retrieval.
 ![image alt](https://github.com/jharajni/Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask/blob/8012035012d598db837c8b37c32269de62892cea/Screenshot%202025-11-18%20225908.png)

# Workflow Diagram
 ![image alt](https://github.com/jharajni/Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask/blob/8012035012d598db837c8b37c32269de62892cea/Screenshot%202025-11-18%20225907.png)
# Setup
Clone the repository
git clone https://github.com/jharajni/Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask.git


# STEP 01- Create a conda environment after opening the repository

     conda create -n medibot python=3.10 -y

     conda activate medibot

# STEP 02- install the requirements
   pip install -r requirements.txt

# Create a .env file in the root directory and add your Pinecone & openai credentials as follows:

     PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
     OPENAI_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"


# run the following command to store embeddings to pinecone
    python store_index.py

# Finally run the following command
    python app.py

Now,
  open up localhost:

  Techstack Used:
    1. Python
    2. LangChain
    3. Flask
    4. Gemini
    5. Pinecone


