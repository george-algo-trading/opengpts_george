# OpenGPTs

This is an open source effort to create a similar experience to OpenAI's GPTs and Assistants API.
It is powered by [LangGraph](https://github.com/langchain-ai/langgraph) - a framework for creating agent runtimes.
It also builds upon [LangChain](https://github.com/langchain-ai/langchain), [LangServe](https://github.com/langchain-ai/langserve) and [LangSmith](https://smith.langchain.com/).
OpenGPTs gives you more control, allowing you to configure:

- The LLM you use (choose between the 60+ that LangChain offers)
- The prompts you use (use LangSmith to debug those)
- The tools you give it (choose from LangChain's 100+ tools, or easily write your own)
- The vector database you use (choose from LangChain's 60+ vector database integrations)
- The retrieval algorithm you use
- The chat history database you use

Most importantly, it gives you full control over the **cognitive architecture** of your application.
Currently, there are three different architectures implemented:

- Assistant
- RAG
- Chatbot

See below for more details on those.
Because this is open source, if you do not like those architectures or want to modify them, you can easily do that!

<p align="center">
    <img alt="Configure" src="_static/configure.png" width="49%" />
    <img alt="Chat" src="_static/chat.png" width="49%" />
</p>

**Key Links**

- [GPTs: a simple hosted version](https://opengpts-example-vz4y4ooboq-uc.a.run.app/)
- [Assistants API: a getting started guide](API.md)
- [Auth: a guide for production](auth.md)

## Quickstart with Docker

This project supports a Docker-based setup, streamlining installation and execution. It automatically builds images for 
the frontend and backend and sets up Postgres using docker-compose.


1. **Prerequisites:**  
    Ensure you have Docker and docker-compose installed on your system.


2. **Clone the Repository:**  
   Obtain the project files by cloning the repository.

   ```
   git clone https://github.com/langchain-ai/opengpts.git
   cd opengpts
   ```

3. **Set Up Environment Variables:**  
   Create a `.env` file in the root directory of the project by copying `.env.example` as a template, and add the 
   following environment variables:
   ```shell
   # At least one language model API key is required
   OPENAI_API_KEY=sk-...
   # LANGCHAIN_TRACING_V2=true
   # LANGCHAIN_API_KEY=...
   
   # Setup for Postgres. Docker compose will use these values to set up the database.
   POSTGRES_PORT=5432
   POSTGRES_DB=opengpts
   POSTGRES_USER=postgres
   POSTGRES_PASSWORD=...
   ```

   Replace `sk-...` with your OpenAI API key and `...` with your LangChain API key.


4. **Run with Docker Compose:**  
   In the root directory of the project, execute:

   ```
   docker compose up
   ```
