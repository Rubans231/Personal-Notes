
2025-08-06 18:28

Status:

Tags: 




# TO DO
## japanese
learn japanese - https://youtube.com/shorts/OdPQOyarROM?si=gCwGE7gb58b7haJE (Best way to start is to learn hiragana and katakana from duolingo after which i'd need to learn from anki and nativshark)

## Projects
https://www.youtube.com/watch?v=cAkMcPfY_Ns&list=TLPQMDcwODIwMjX7RDN5u0VqJA&index=2(Neural network from scratch)

## **Daily Structure**

- **2 hrs – Core ML Skills** (theory + coding)
    
- **3 hrs – Project Work** (progress on flagship + sub-projects)
    
- **30 min – Industry Awareness** (Rakuten news, tech blogs, ML papers)
    
- **30 min – Documentation/Public Profile** (GitHub commits, blog/LinkedIn updates)
    

---

## **WEEK 1 – LLMs, Hugging Face, LangChain Fundamentals**

**Goal:** Build core skills in LLMs & frameworks, start Rakuten AI Toolkit repo.

| Day | Core Skills                                                 | Project Work                                                | Industry Awareness                                          | Public Profile                                             |
| --- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------- |
| 1   | Read Hugging Face Course Ch. 1–2 (Transformers, Tokenizers) | Create “Rakuten AI Toolkit” GitHub repo                     | Google Alerts for “Rakuten India” & follow Rakuten Eng Blog | LinkedIn post: “Starting my 45-Day ML Internship Bootcamp” |
| 2   | HF Ch. 3–4 (Datasets, Trainer)                              | Load pretrained model (`bert-base-uncased`) & run inference | Read Rakuten AI-related blog post                           | Commit inference code                                      |
| 3   | HF Ch. 5–6 (Inference API, Pipelines)                       | Test `text-generation` & `question-answering`               | Read 1 arXiv paper on LLMs                                  | Write short summary in repo README                         |
| 4   | HF Ch. 7–8 (Training basics)                                | Build simple sentiment classifier using HF pipeline         | Explore FAISS basics                                        | Commit code + requirements.txt                             |
| 5   | HF Ch. 9–10 (Custom training loops)                         | Run local fine-tune on small dataset                        | Read “LangChain Prompt Templates” docs                      | LinkedIn post: “Intro to Hugging Face for LLMs”            |
| 6   | LangChain Quickstart (prompt templates, chains, memory)     | Create basic prompt chain with OpenAI API or LLaMA2         | Read Rakuten search/recommendation patent                   | Push LangChain example                                     |
| 7   | Review & mini quiz (self-test)                              | Document Rakuten AI Toolkit                                 | Skim Hacker News ML posts                                   | Weekly blog: “Week 1 – From Hugging Face to LangChain”     |

---

## **WEEK 2 – RAG Chatbot (Rakuten Domain)**

**Goal:** Build RAG pipeline using Rakuten-style data.

|Day|Core Skills|Project Work|Industry Awareness|Public Profile|
|---|---|---|---|---|
|8|Read LangChain RAG docs|Collect Rakuten product docs/news for dataset|Read 1 recsys paper on arXiv|Commit data collection script|
|9|SentenceTransformer embeddings|Convert data to vector embeddings|Read about Pinecone vs FAISS|Push embeddings code|
|10|FAISS basics (index, search)|Build FAISS index for product Q&A|Read Rakuten personalization blog|LinkedIn post: “Building a Rakuten RAG index”|
|11|LangChain RetrievalQA|Connect FAISS → GPT → LangChain chain|Read about GPT-4 retrieval|Commit RetrievalQA script|
|12|Streamlit basics|Add chatbot UI for local testing|Explore Rakuten front-end jobs for UI ideas|Push Streamlit app|
|13|Integration testing|Chatbot functional on local|Read MLOps for RAG blog|Record demo video|
|14|Review & refine|Weekly test session|Read LangChain community discussions|Blog: “Week 2 – My RAG Chatbot Journey”|

---

## **WEEK 3 – Productionizing the Chatbot**

**Goal:** Make it deployable, secure, and monitored.

|Day|Core Skills|Project Work|Industry Awareness|Public Profile|
|---|---|---|---|---|
|15|Docker basics|Write Dockerfile for chatbot|Read Rakuten cloud infrastructure news|Commit Dockerfile|
|16|Docker Compose|Add FAISS persistence in container|Read about container scaling|Push docker-compose.yml|
|17|FastAPI for backend|Convert chatbot to FastAPI API|Read API gateway basics|Commit API version|
|18|NGINX reverse proxy|Secure endpoint|Read Rakuten site performance case study|Push config|
|19|Render/Railway deploy|Deploy containerized chatbot|Read Kubernetes basics|Share live link|
|20|User auth basics|Add token-based auth|Read OWASP ML security notes|Commit auth code|
|21|Weekly review|Stress test chatbot|Read Hacker News on LLM security|Blog: “Week 3 – Shipping My First AI Product”|

---

## **WEEK 4 – Fine-Tuning for Rakuten Use Case**

**Goal:** Add domain-specific ML capabilities.

|Day|Core Skills|Project Work|Industry Awareness|Public Profile|
|---|---|---|---|---|
|22|Review fine-tuning theory|Pick dataset (e.g., product sentiment)|Read Rakuten customer experience case study|Share dataset choice|
|23|HF Datasets loading|Prepare dataset|Read paper on product recommendation ML|Commit dataset preprocessing|
|24|Tokenization + training loop|Fine-tune BERT/RoBERTa|Read Hugging Face blog on LoRA|Push training code|
|25|Experiment tracking (W&B/MLflow)|Log fine-tuning runs|Read about ML model evaluation|Share W&B dashboard|
|26|Inference testing|Integrate fine-tuned model into chatbot|Read Rakuten AI API docs|Commit integration|
|27|Evaluation & improvement|Improve accuracy/F1|Read model bias/fairness paper|Update README with results|
|28|Weekly review|Test chatbot with new feature|Read LangChain integration case studies|Blog: “Week 4 – Fine-tuning BERT for E-commerce AI”|

---

## **WEEK 5 – MLOps: CI/CD, Monitoring**

**Goal:** Automate deployment and monitor chatbot.

|Day|Core Skills|Project Work|Industry Awareness|Public Profile|
|---|---|---|---|---|
|29|GitHub Actions basics|Auto-deploy on push|Read MLOps at scale blog|Commit CI workflow|
|30|Model packaging|Bundle chatbot + model|Read about Rakuten deployment strategies|Push packaged build|
|31|Prometheus basics|Set up basic metrics|Read Grafana dashboards|Commit metrics setup|
|32|Grafana visualization|Create dashboard|Read cloud monitoring best practices|Share screenshot|
|33|Logging & alerts|Add logging to FastAPI|Read ML logging tools|Push logging code|
|34|Testing pipeline|Simulate retraining|Read MLOps failures case studies|Share pipeline video|
|35|Weekly review|Finalize CI/CD + monitoring|Read Hacker News ML threads|Blog: “Week 5 – My First MLOps Pipeline”|

---

## **WEEK 6 – Cloud, Portfolio, Networking**

**Goal:** Host final product, polish resume, make profile recruiter-ready.

|Day|Core Skills|Project Work|Industry Awareness|Public Profile|
|---|---|---|---|---|
|36|AWS S3 basics|Upload dataset/model|Read AWS ML service case study|Commit AWS setup|
|37|AWS EC2 deploy|Deploy chatbot container|Read GCP AI blog|Share live EC2 link|
|38|CloudWatch basics|Set up logs|Read about cost optimization|Commit logs setup|
|39|Resume deep clean|Add projects + metrics|Read resume tips for ML engineers|Push updated resume to LinkedIn|
|40|Portfolio website|Build with GitHub Pages|Read about personal branding|Publish site|
|41|Mock interview 1|Technical round simulation|Read Rakuten interview experience|Share learnings post|
|42|Mock interview 2|System design simulation|Read system design tips|Push system diagrams to repo|
|43|Final testing|Test full chatbot + fine-tune features|Read final ML trends newsletter|Record 3-min demo video|
|44|Public release|Announce final project on LinkedIn + Twitter|Engage with Rakuten engineers online|Post video + repo link|
|45|Reflection & next steps|Write blog summarizing 45 days|Read job postings to adjust skill plan|Blog: “My 45-Day ML Internship Bootcamp Journey”|

---

## **Outcome by Day 45**

- **1 flagship integrated system**: Rakuten-style AI Assistant (RAG chatbot + fine-tuned model + monitoring + cloud hosting)
    
- **3–4 smaller sub-projects** from stages of development
    
- **Professional GitHub** with clean READMEs and commits every week
    
- **3+ blog posts + LinkedIn updates** showing expertise and growth
    
- **Mock interview practice + recruiter-ready resume**
    
- **Industry familiarity** with Rakuten’s AI and data engineering practices




# References