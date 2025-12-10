fastapi 
inngest 
llama-index-core 
llama-index-readers-file 
python-dotenv 
qdrant-client 
uvicorn 
streamlit 
openai - #pay price
google-genai - #free
node js-installed in system

#COMMANDS TO RUN
fastapi in main.py --> python -m uv run uvicorn main:app  
or  
python -m uvicorn main:app

inngest server running-->  npx inngest-cli@latest dev -u http://127.0.0.1:8000/api/inngest --no-discovery

#COMMANDS THAT WERE RUN 
allow running qdrant in qdrantRagDB container in docker---> docker run -d --name qdrantRagDB -p 6333:6333 -v "$(pwd)/qdrant_storage:/qdrant/storage" qdrant/qdrant


FILE EXPLANATIONS

data_loader.py -->
llama_index takes in the pdf -reads it , splits the pdf into small chunks then embedd (using gemini's embed model - "text-embedding-004" with DIM 768, since openAI embedding model "text-embedding-3-large" with DIM 3072 is paid ) them to store in the vector database.
ENSURE THE DIM IN EMBEDDING MODEL MATCHES THE DIM OF VECTOR DATABASE.

custom_types.py -->
to create custom python types to make the application more readable and to use pydantic that is supported by inngest