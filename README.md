# FinSight.Ai: Virtual Assistant for Real-Time Financial Market Insights  

**Author:** Prithvi Elancherran  
**Date:** December 08, 2024  

---

## Objective  
The objective of this project is to develop a cutting-edge, AI-powered virtual assistant (VA) for financial market insights. Leveraging advanced Retrieval-Augmented Generation (RAG) and Natural Language Processing (NLP) techniques, the system aims to deliver accurate, real-time responses to user queries. It will provide actionable insights on stock performance, market trends, and trading metrics, empowering users with data-driven decision-making in the financial domain.  

---

## Data Sources  

### Data Collection  
- **Stock Market Data:** Sourced using yFinance API.  
- **S&P 500 Tickers:** Extracted from official lists.  

### Data Processing  
- Preprocessed data to remove null values.  
- Cleaned and normalized stock price, trading volume, and return data.  
- Stored processed data in **Pinecone** for efficient retrieval.  

---

## Model Selection  
- **Sentence Transformer:** all-MiniLM-L6-v2 for document embedding.  
- **Large Language Model API:** Gemini API for advanced question answering and enhanced contextual understanding.  
- **Text Generation:** Google Flan-T5-Large for response generation.  

---

## Implementation  

### RAG Setup  
- Used **Pinecone** as a vector database for embedding storage and retrieval.  
- Designed a **Gradio-powered web interface** for user interaction.  

### Query Handling Pipeline  
1. User submits a query.  
2. The system queries Pinecone for relevant documents.  
3. Retrieved data is embedded into an adaptive prompt.  
4. The prompt is passed to Google Flan-T5-Large for response generation.  

---

## Evaluation Metrics  

### Metrics Used  
- **Cosine Similarity:** To measure response relevance.  
- **Accuracy:** Based on matching ground-truth responses.  

### Results  
- **Initial Accuracy:** 66.67%  
- **Initial Average Cosine Similarity:** 75.09%  

---

## Improvement Techniques  
1. **Adaptive Prompting:** Enhanced prompts based on query type (e.g., performance, trends, prices).  
2. **Ground-Truth Extraction:** Dynamically generated adaptive ground-truth responses to improve evaluation accuracy.  
3. **Response Reformatting:** Reformatted incomplete numerical answers into full descriptive sentences.  
4. **Filtering Responses:** Applied grammar checks to filter responses.  

### Improved Results  
- **Improved Accuracy:** 70.00%  
- **Improved Average Cosine Similarity:** 78.22%  

---

## User Interface  
- Built with **Gradio**, an open-source Python library for creating user-friendly web interfaces for machine learning models, APIs, and data workflows.  
- Integrated **dynamic interaction** for real-time chat functionality.  

---

## Challenges & Resolutions  

### 1. Creating Embeddings for Numerical Data  
- **Challenge:** Converting rows of numerical data into meaningful text representations for embeddings.  
- **Resolution:** Preprocessed data into descriptive strings before generating embeddings.  

### 2. Choosing Lightweight Models  
- **Challenge:** Most models either ran for too long or failed due to the large query/prompt size.  
- **Resolution:** Tested over 10 models and finalized the best-performing ones, including Flan-T5 and Gemini API.  

### 3. Response Redundancy in Flan-T5  
- **Challenge:** Flan-T5 generated multiple or redundant responses.  
- **Resolution:** Applied early stopping and refined prompt structures to limit verbosity.  

### 4. Improving VA Performance  
- **Challenge:** Several individual improvement techniques failed to yield significant gains.  
- **Resolution:** Combined three key approaches—adaptive prompting, revising model responses, and filtering (grammar checks)—to achieve notable performance improvements.  

---

## Conclusion & Future Work  
This project successfully implemented a financial market VA capable of real-time insights using the RAG framework.  

### Future Enhancements  
1. Integration of additional financial APIs.  
2. Fine-tuning LLMs for specific financial tasks.  
3. Expanding evaluation metrics for improved performance analysis.  

---

## How to Run the Project  

1. Clone the repository:  
   ```bash  
   git clone https://github.com/PrithviElancherran/FinSight.Ai.git 
   cd FinSight.Ai

2. Install dependencies:
    ```bash
    pip install -r requirements.txt  

3. Open the Jupyter Notebook:
    ```bash
    jupyter notebook notebook.ipynb  

4. Run the cells in the notebook sequentially.

