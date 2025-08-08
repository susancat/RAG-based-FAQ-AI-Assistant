# 📚 RAG-based FAQ AI Assistant (Colab Demo)

This project demonstrates a simple implementation of a Retrieval-Augmented Generation (RAG) assistant to answer questions based on a custom FAQ file.

## ✅ Features

- Upload a `.csv` FAQ file with `Question` and `Answer` columns
- Use OpenAI Embedding API (`text-embedding-3-small`) to generate vector representations
- Build a vector database using FAISS for fast similarity search
- Given a user question, retrieve the most relevant answer(s)
- Optionally combine top FAQs into a context for better response (RAG-style)

## 🧰 Tech Stack

- Google Colab
- OpenAI API (embedding + completion)
- FAISS (`faiss-cpu`)
- `pandas`, `numpy`, `scikit-learn`, `tiktoken`, `tqdm`

## 💡 How it works

1. Upload your own FAQ `.csv` file (must contain `Question`, `Answer`)
2. Convert each question to an embedding
3. Build an FAISS index of all question embeddings
4. Input a user question
5. Retrieve the top-k most similar FAQs by cosine similarity
6. Use the original answers or combine them into a prompt to let the LLM respond more naturally (RAG)

## 📌 Example use case

"How do I earn more OC points?" → Assistant retrieves the closest FAQ and provides a confident response using the original answer or LLM completion.

## 📁 File structure
faq_rag_demo/  
├── FAQ_assistant_RAG_version.ipynb  
├── cleaned_faq.csv  
├── README.md  

## 🌊 Project Background

This demo is based on FAQ content from **Mindful Ocean Metaverse**, an interactive ocean conservation app (web3/AR) I managed as a Product Manager.  
https://www.mindful-ocean.org/  
The assistant is designed to help users understand app mechanics, point systems, and user journeys using intelligent retrieval and LLM response.
It showcases how PMs can use **RAG (Retrieval-Augmented Generation)** techniques to create helpful, AI-powered support tools grounded in real-world product data.

## 📎 To run

1. Open the Colab notebook
2. Install dependencies
3. Upload your CSV file
4. Follow the cells step-by-step

## 🚀 Future Extensions

- Support for multi-turn QA or chat history
- Streamlit web interface
- Improved context merging and re-ranking
