# ClassGPT

ClassGPT is a project designed to assist with daily classes by enabling the upload and analysis of PDF files, such as research papers or class lectures. It utilizes the power of artificial intelligence to answer questions related to the uploaded documents.

Usage : 
[Watch the video](https://youtu.be/a2BaHLKHFkk)




This repository contains code for parsing PDF files, constructing an index using LlamaIndex's GPTSimpleVectorIndex, and querying the index. It utilizes the text-embedding-ada-002 model to create embeddings. The indexes and files are stored on Amazon S3.

## How it Works

1. **PDF Parsing**: The repository uses the `pypdf` library to parse PDF files.

2. **Index Construction**: The index is constructed using LlamaIndex's GPTSimpleVectorIndex, which leverages the text-embedding-ada-002 model to create embeddings.

3. **Vector Store Index**: For more information on the vector store index, please refer to the vector store index page.

4. **Sample Index**: A sample index is available to explore and understand the functionality.

5. **Storage**: Both indexes and files are stored on Amazon S3.

## Querying the Index

The latest ChatGPT model, gpt-3.5-turbo, is used for querying the index.

## Usage

To use this repository, follow the steps below:

### Configuration and Secrets

1. Configure AWS by running the following command:
```
aws configure
```

2. Create an S3 bucket named "classgpt".

3. Rename `.env.local.example` to `.env` and add your OpenAI credentials.

### Locally

1. Create a Python environment:
```
conda create -n classgpt python=3.9
conda activate classgpt
```

2. Install the dependencies:
```
pip install -r requirements.txt
```

3. Run the Streamlit app:
```
cd app/
streamlit run app/01_❓_Ask.py
```

### Docker

Alternatively, you can use Docker:

```
docker compose up
```

Then, open a new tab and navigate to http://localhost:8501/.

## FAQ

**Tokens**: Tokens can be thought of as pieces of words. Before the API processes the prompts, the input is broken down into tokens. Tokens can include trailing spaces and even sub-words. Here are some helpful rules of thumb for understanding tokens in terms of lengths:
- 1 token ≈ 4 chars in English
- 1 token ≈ ¾ words
- 100 tokens ≈ 75 words
- 1-2 sentences ≈ 30 tokens
- 1 paragraph ≈ 100 tokens
- 1,500 words ≈ 2048 tokens

You can try the OpenAI Tokenizer tool to experiment with tokens.

**Source**: The source code for this project can be found at [GitHub - ClassGPT](https://github.com/jash2105/ClassGPT.git).

**Embeddings**: An embedding is a vector (list) of floating-point numbers. The distance between two vectors measures their relatedness, where small distances suggest high relatedness and large distances suggest low relatedness. For the `text-embedding-ada-002` model, the cost is $0.0004 per 1,000 tokens or 3,000 pages per dollar.

Feel free to explore and utilize this repository for your own purposes. If you have any further questions, please reach out!
