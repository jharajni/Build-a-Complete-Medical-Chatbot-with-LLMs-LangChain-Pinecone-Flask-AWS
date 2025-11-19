## Medical Chatbot

# Project Overview
This RAG-based system processes uploaded PDFs by extracting and chunking text, then uses an embedding model and Pinecone Vector Database for retrieval, finally generating user responses via a Generative LLM.

# Features

 Text Extraction & Storing the Vector Embedding : Extracts and chunks text from PDF pages then by using Embedding Model to generate vector embedding to store in Pinecone Vector DB for subsequent semantic retrieval.
 ![image alt](https://github.com/jharajni/Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask-AWS/blob/8012035012d598db837c8b37c32269de62892cea/Screenshot%202025-11-18%20225908.png)

# Workflow Diagram
 ![image alt](https://github.com/jharajni/Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask-AWS/blob/8012035012d598db837c8b37c32269de62892cea/Screenshot%202025-11-18%20225907.png)
# Setup
Clone the repository
git clone https://github.com/jharajni/Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask-AWS.git


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


