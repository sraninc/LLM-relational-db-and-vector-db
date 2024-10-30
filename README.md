# LLM-relational-db-and-vector-db
### Problem Statement:
The project aims to create an automated SQL query generation system that interprets natural language questions and retrieves data from a relational database (SQLite). This solution allows users to interact with complex databases without needing SQL knowledge.

### Workflow:
1. Database Connection and Document Creation:
    * The project begins by connecting to a SQLite database and converting the rows into structured documents (LangChain's `Document` objects). THese documents provide a structured format that enables easier processing and retrieval.
2. Vectorization and Similarity Search:
    * Each document is then transformed into a vector embedding using Hugging Face Transformer models, resulting in a vector database (via Chroma). This vector database enables similarity search, where user queries can be vectorized and matched with stored documents to find relevant resutls based on content similarity alone.
    * This step allows the project to retrieve relevant documents quickly based on similarity without SQL, serving as a basic retrieval layer.
3. Incorporating LLMs for SQL Generation:
    * With the Groq Language model (LLM) integrated through LangChain, the project advances to a more sophisticated pipeline. Here, the LLM is leveraged to interpret the user's natural language question, generate a SQL query based on the database schema, and retrieve relevant data:
        * Step 1: The user's question is passed to the Groq model alongside the schema as context. The LLM translates the question into a SQL query, ensuring it's accurate and schema-compliant.
        * Step 2: The generated SQL query is then executed on the database to retrieve precise, structured information.
    * This approach provides users with contextually rich, SQL-based responses, leveraging the database's structure to provide accurate answers. 

### Purpose:
This setup is especially useful for users with limited SQL knowledge, as it enables them to query and retrieve information from relational databases using only natural language. The LLM-powered query generation further enhances the system's flexibility and ability to handle complex questions by generating and running SQL queries autonomously.