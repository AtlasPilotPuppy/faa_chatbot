## LLM Rag Demo

This repo demonstrates the creation of a simple Retrieval Assisted Generation pipeline using langchain.
You can access the api [here](https://faa-chat-gmowtb4zma-wl.a.run.app/docs)
The docs used for this can be found [here](https://storage.googleapis.com/faa_docs_public/).

The pipeline has 2 parts:
- Vectorstore creation
  - We read the documents, split and tokenize them
  - We create a vectorstore from the documents.
- Retrieval
  - We generate an embedding for the question
  - We then use the vectorstore to retrieve the most similar documents to a query
  - The documents are passsed into the context of the LLM for generating a coherent answer

## Setup

- Clone this repo
- Set up env for the vectorstore creation and install requirements.
  - `cd vectorstore_creation`
  - `pip install -r requirements.txt`
  - Get the docs for the vectorstore creation - [here](https://storage.googleapis.com/faa_docs_public/)
  - generate the vectorstore using `python rag_index.py`
- Set up a new python env for the Retrieval pipeline
  - `cd gcloud`
  - `pip install -r requirements.txt`
  - copy the `my_deeplake` folder from the vectorstore_creation into the `gcloud` folder
  - `python faa_chat_api.py`
