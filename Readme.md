Introductory project to explore ai. Project intend to implement 

Dependencies/Tools : 

Ollama : Docker alternative for local development of ai tools. Interface to run llms locally.Ollama is an open-source tool that runs large language models (LLMs) directly on a local machine.By running models locally, you maintain full data ownership and avoid the potential security risks associated with cloud storage. Offline AI tools like Ollama also help reduce latency and reliance on external servers, making them faster and more reliable.

openhermes : State of art mistral 7B fine-tune.
             More details : https://huggingface.co/teknium/OpenHermes-2.5-Mistral-7B

langchain : open-source framework designed to facilitate the development of applications powered by large language models.

duckdb : In-memory SQL engine (local db for the poc)

sqlalchemy : ORM or SQL Interface

chromadb : Local vector DB to store embeddings for RAG implementation.

fastapi: Built async python api's

uvicorn : ASGI Server for fast api. Run api's locally.

pydantic : Data validation used when implementing api's in Fastapi

Data flow : 
User Query → FastAPI Endpoint
                   ↓
            Langchain Agent
                   ↓
            (Choose Ollama LLM / SQL / Pandas)
                   ↓
            → Ollama (text answers)
            → DuckDB / Pandas (data answers)
            → Tabulate (format output)
                   ↓
            Return Final Response