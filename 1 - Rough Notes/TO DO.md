
2025-08-06 18:28

Status:

Tags: 




# TO DO
## japanese
learn japanese - https://youtube.com/shorts/OdPQOyarROM?si=gCwGE7gb58b7haJE (Best way to start is to learn hiragana and katakana from duolingo after which i'd need to learn from anki and nativshark)

## Projects
https://www.youtube.com/watch?v=cAkMcPfY_Ns&list=TLPQMDcwODIwMjX7RDN5u0VqJA&index=2(Neural network from scratch)

# **45-Day ML Engineer Roadmap**

**Assumption**: You can dedicate **3–5 hours/day** consistently. If not, I can break it into a 60-day or weekend-focused version.

---

## ⚙️ Structure Overview

|Week|Focus|Deliverables|
|---|---|---|
|1|Hugging Face, LLMs, LangChain basics|Complete Hugging Face course, prep for RAG|
|2|Build RAG-based chatbot (FAISS/Pinecone)|RAG pipeline + chatbot UI|
|3|Finish chatbot + deploy with Docker|Live deployed chatbot|
|4|Fine-tune Transformer model + evaluate|Model + visualized metrics|
|5|Deploy fine-tuned model + set up CI/CD|API + Docker + GitHub Actions|
|6|Learn Cloud (AWS/GCP), monitor models|Live cloud deployment + dashboard|

---

## 🧠 **Week-by-Week Breakdown**

---

### 📘 **Week 1: Learn LLMs, Hugging Face, LangChain**

#### 🧩 Goals:

- Understand Transformers, Tokenizers
    
- Master Hugging Face ecosystem (datasets, trainer, inference)
    
- Learn LangChain concepts (prompt templates, chains, memory)
    

#### 📚 Resources:

- ✅ Hugging Face Course
    
- ✅ LangChain Quickstart
    

#### 🛠️ Tasks:

-  Complete Hugging Face course (10 chapters)
    
-  Try 2 examples using pre-trained models (`text-generation`, `question-answering`)
    
-  Test LangChain’s basic prompt chain with OpenAI or `llama2` locally
    

#### ✅ Deliverable:

- GitHub repo with basic Hugging Face model loading and inference
    
- Notes or blog: _“Intro to LLMs using Hugging Face”_
    

---

### 🤖 **Week 2: RAG Chatbot with LangChain + FAISS/Pinecone**

#### 🧩 Goals:

- Create a RAG pipeline using PDF/website knowledge
    
- Add a basic UI (Streamlit or FastAPI)
    

#### 📚 Resources:

- [YouTube: Greg Kamradt's RAG Chatbot](https://www.youtube.com/watch?v=j0LzFjPaQt4)
    
- LangChain RAG Docs
    

#### 🛠️ Tasks:

-  Extract text from PDFs or websites
    
-  Convert to embeddings using `SentenceTransformer` or `OpenAIEmbeddings`
    
-  Store in FAISS / Pinecone
    
-  Integrate retrieval with GPT using LangChain
    
-  Build chatbot UI with Streamlit or FastAPI
    

#### ✅ Deliverable:

- Working chatbot hosted locally or on `Render`
    
- GitHub README + demo video
    

---

### 🐳 **Week 3: Productionize the Chatbot (Docker + Deploy)**

#### 🧩 Goals:

- Dockerize the chatbot app
    
- Deploy to `Render`, `Railway`, or `AWS EC2`
    
- Optional: Add user auth + query logging
    

#### 📚 Resources:

- [Docker Crash Course](https://www.youtube.com/watch?v=fqMOX6JJhGo)
    
- Deploy FastAPI with Docker
    

#### 🛠️ Tasks:

-  Write Dockerfile + requirements
    
-  Test locally with Docker Compose
    
-  Deploy to Render or EC2
    
-  Optional: Use NGINX as reverse proxy
    

#### ✅ Deliverable:

- Live link to deployed chatbot
    
- GitHub repo with `Dockerfile`, setup instructions
    

---

### 🔬 **Week 4: Fine-tune Transformer Model on Custom Data**

#### 🧩 Goals:

- Choose dataset (e.g., IMDB, Hate Speech, StackOverflow)
    
- Fine-tune BERT/RoBERTa for classification
    
- Track experiments with W&B or MLflow
    

#### 📚 Resources:

- Hugging Face Fine-tuning
    
- Kaggle Datasets
    

#### 🛠️ Tasks:

-  Load dataset using HF Datasets
    
-  Tokenize + fine-tune with `Trainer`
    
-  Log results + visualize metrics
    
-  Export model + test inference
    

#### ✅ Deliverable:

- GitHub repo: fine-tuning project with Jupyter notebook
    
- README with results and graphs
    

---

### ☁️ **Week 5: API + CI/CD + Docker + Monitoring**

#### 🧩 Goals:

- Package model into FastAPI + Docker
    
- Automate retraining/deployment via GitHub Actions
    
- Learn basic monitoring with Prometheus + Grafana
    

#### 📚 Resources:

- Made With ML - Deployment
    
- Monitor ML models
    

#### 🛠️ Tasks:

-  Create FastAPI endpoint for prediction
    
-  Add Docker support
    
-  Set up GitHub Actions: push = redeploy
    
-  Optional: Add Prometheus logging
    

#### ✅ Deliverable:

- API live with test inputs
    
- Screenshot or video demo of monitoring setup
    

---

### 🌍 **Week 6: Cloud & Final Polish**

#### 🧩 Goals:

- Learn AWS basics (S3, EC2, Lambda)
    
- Deploy app to AWS or GCP
    
- Final polish on portfolio + GitHub
    

#### 📚 Resources:

- AWS Machine Learning Essentials
    
- Google Cloud ML Engineer Path
    

#### 🛠️ Tasks:

-  Create S3 bucket and upload dataset
    
-  Launch EC2 instance and deploy Docker container
    
-  Optional: Set up CloudWatch logs
    
-  Write LinkedIn post about your journey
    

#### ✅ Deliverable:

- Hosted app or model on AWS/GCP
    
- Updated resume + LinkedIn
    
- GitHub portfolio with 2 polished projects
    

---

## 📘 Bonus Tips:

- Use **Notion** or **Trello** to track daily tasks.
    
- Start a **GitHub project board** to show real-world planning.
    
- Use `README.md` to narrate your journey — it _really impresses recruiters_.
    
- If you're comfortable, post a weekly devlog or short demo on **LinkedIn** or **X** (Twitter).





# References