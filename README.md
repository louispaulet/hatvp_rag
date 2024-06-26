# HATVP Project Overview  

## Folders 📁

### 1. RAG (Retrieval Augmented Generation) 🚀

#### Purpose
Develop an assistant to accurately answer questions about HATVP declarations of interest using the RAG technique to ensure responses are grounded in verified data.

#### Key Components
- **Data Sources**: HATVP open data declarations.
- **Language Models**: Primarily Llama8B and Llama70B, with some tests using GPT-4.
- **Inference**: Groq Cloud and OpenAI for embedding.

#### Workflow
1. **Data Preparation**: Split XML files, convert to JSON, extract text and metadata.
2. **Indexing**: Use OpenAI large model for text embeddings.
3. **Query Processing**: Embed user query, retrieve relevant document, augment context, generate response.

#### Notebooks
- Data conversion: `Part_1` to `Part_4`
- RAG system: `Part_5`
- Experiments: Various salary-related queries
- Minimal RAG code: `Part_6`

[GitHub Project Link](https://github.com/louispaulet/hatvp_rag)

### 2. WIP Data Analysis 📊

#### Purpose
Conduct ongoing data analysis on stock declarations by representatives in the HATVP datasets.

#### Key Components
- Analyzing patterns and trends in stock declarations.
- Identifying potential conflicts of interest or unusual activity.

#### Status
Work in Progress. Further details and updates will be provided as the analysis progresses.
