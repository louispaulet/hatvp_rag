# HATVP RAG Experiment 🚀

Welcome to the HATVP RAG Experiment project! Our goal is to create an intelligent assistant capable of answering questions about declarations of interest published by the HATVP. To ensure accuracy and mitigate hallucinations, we employ the Retrieval Augmented Generation (RAG) technique, grounding our responses in verified data.

## Project Overview 📊

### Why RAG? 🤔

Retrieval Augmented Generation (RAG) combines retrieval-based methods with generative models to enhance the quality and relevance of generated text. In RAG, a retrieval component first searches for relevant documents or information from a large dataset based on the input query. Then, a generative model, such as a language model, uses this retrieved information to produce a more accurate and contextually relevant response. This approach leverages the strengths of both retrieval and generation, resulting in more informative and coherent outputs.

### Data Sources 📂

We use the open data declarations dataset provided by HATVP. You can access these datasets through the following links:
- [Open Data Page](https://www.hatvp.fr/open-data/)
- [XML Dataset](https://www.hatvp.fr/livraison/merge/declarations.xml)

### Language Models 🧠

For this project, we primarily use Llama8B and Llama70B, with some experiments conducted using GPT-4. Inference is performed using Groq Cloud for free API access, while OpenAI is utilized mainly for generating embeddings.

### Dataset Availability 📥

The datasets used in this project are available on Huggingface Hub. You can find the links in the relevant notebooks listed below.

## Project Workflow 🔄

### Data Preparation 🛠️

1. **Splitting XML Files**: The single XML file is divided into individual declaration XML files.
2. **Conversion to JSON**: These XML files are converted to JSON format to fit entirely within the LLM context while using 30% fewer characters.
3. **Text and Metadata Extraction**: We extract text values and key fields (name, surname, last job title) for indexing purposes.

### Indexing 📈

We index either the entire text or specific text fields using embeddings generated by the OpenAI text embedding large model. Observations show improved French language sensitivity with the large model, making the increased cost worthwhile.

### Query Processing 🔍

1. **Query Embedding**: The user's query is embedded using the OpenAI large embedding model.
2. **Document Retrieval**: The closest matching document is retrieved.
3. **Context Augmentation**: The JSON declaration of the retrieved document is added to the LLM context.
4. **Generating Responses**: The LLM, augmented with the retrieved context, generates an accurate response.

### Example Query 🤓

**User Query**: What was the salary of Damien Abad in 2019?
1. Retrieve Damien Abad's declaration.
2. Augment the context with Damien Abad's JSON declaration.
3. Query Llama70B via Groq with the augmented context and user query.
4. Display the answer.

## Notebooks 📒

The following notebooks were used to create the necessary datasets for our experiments:

1. **Data Conversion**:
   - `Part_1_HATVP_RAG_Convert_XML_to_JSON`
   - `Part_2_HATVP_RAG_Convert_JSON_to_text`
   - `Part_3_HATVP_RAG_Convert_JSON_to_text_index`
   - `Part_4_HATVP_RAG_Convert_JSON_to_text_with_metadata`

2. **RAG System**:
   - `Part_5_HATVP_Llangchain_on_JSON_dataset_3_NO_chunks`: Contains examples of document retrieval for context enrichment and LLM inference.

3. **Experiments**:
   - Various queries like:
     - "Give me the salary of person X in year Y."
     - "Give me the salary of a person whose spouse is a nurse."
     - "Give me the salary of a person that is a Mayor."
   - Demonstrates that the LLM does not hallucinate when provided with the correct context.

4. **Minimal RAG Code**:
   - `Part_6_HATVP_RAG_Light_functional_version`: Contains the minimal code needed to perform RAG on the HATVP dataset. Feel free to play with it, ask questions, and see if it can retrieve documents and answer truthfully.

---

Check out our project on GitHub: [HATVP RAG Experiment](https://github.com/louispaulet/hatvp_rag)

We hope you find this project insightful and engaging. Happy querying! 🎉
