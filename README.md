# Medical QA Bot: Fine-Tuning & RAG Implementation

![Screenshot 2025-02-12 at 2 05 57 PM](https://github.com/user-attachments/assets/dc80c030-c9c5-4690-b525-1574234f1605)


## Project Summary
This project involves building a **Medical Question-Answering (QA) Bot** using **Retrieval-Augmented Generation (RAG)** and fine-tuning **T5-small** on the **ChatDoctor dataset**. The workflow includes **data exploration, model fine-tuning, evaluation, deployment, and interactive UI implementation** using Gradio.

### Key Steps & Implementation
1. **Exploratory Data Analysis (EDA)**
   - Analyzed dataset statistics, text length distributions, and most frequent words.
   - Applied **t-SNE visualization** on embeddings to understand document clustering.

2. **Fine-Tuning the Model**
   - Initially attempted fine-tuning **Mistral-7B-OpenOrca**, but due to **high resource demands**, switched to **T5-small**.
   - Applied **QLoRA (4-bit optimization)** but still encountered resource constraints.
   - Used **Google Colab & Kaggle GPUs**, preferring Kaggle due to **Colab session timeouts**.
   - Performed hyperparameter tuning to optimize training efficiency.

3. **Model Evaluation & Tracking**
   - Logged training loss and evaluation metrics using **TensorBoard**.
   - Applied **custom loss tracking** to monitor performance improvements.
   - Conducted inference tests to validate model responses.

4. **RAG-Based Retrieval System**
   - Implemented **FAISS** for storing and retrieving **document embeddings**.
   - Used **LangChain** to structure the **retrieval-augmented pipeline**.
   - Integrated **Hugging Face Embeddings (MiniLM)** for efficient similarity search.

5. **Interactive Deployment Using Gradio**
   - Built a **simple yet effective UI** for querying the medical chatbot.
   - Deployed the fine-tuned model with **Gradio-based web interface**.
   - Ensured that queries were processed in real-time using **LangChain RetrievalQA**.

---

## Results & Insights
- Fine-tuning a large model like Mistral-7B was infeasible due to resource constraints, necessitating a shift to **T5-small**.  
- Hyperparameter tuning significantly affects training time and performance, making **batch size, learning rate, and context length** crucial factors.  
- Retrieval-Augmented Generation (RAG) improves response relevance by incorporating contextual information from similar retrieved queries.  
- Gradio provides an effective and lightweight UI solution for real-time inference, making chatbot deployment seamless.  
- RAG helps reduce hallucination, but does not eliminate it completely, requiring further filtering and fine-tuning.

---

## Challenges Faced
- **High resource demand**: Training large models like Mistral-7B required **high-end GPUs**, making fine-tuning impractical.
- **Long training times**: Even with **QLoRA**, training remained **resource-intensive**.
- **Response repetition issues**: Initially, model outputs contained **repetitive sentences**, requiring **beam search tuning**.
- **Session timeouts**: **Colab frequently disconnected**, leading to preference for **Kaggle's persistent sessions**.

---

## Final Thoughts
This project demonstrated the feasibility of **fine-tuning T5-small for medical question answering** while leveraging **RAG-based retrieval for contextual enhancement**. While the chatbot performs well, **AI hallucination and response accuracy remain key challenges** that future work will focus on improving.

By optimizing training efficiency, enhancing retrieval mechanisms, and refining model deployment strategies, this project can be expanded into a **fully functional AI medical assistant** capable of handling **real-world use cases**.
