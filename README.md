# AI Hiring Assistant 🤖📬

An open-source, RAG-based AI automation system that screens job applications directly from email — reducing manual review time by up to 80%.

This workflow uses **n8n**, **OpenAI GPT-4o**, **Pinecone**, and **LangChain** to automatically extract, analyze, and rank candidates from incoming emails based on role-specific criteria.

---

## 🔧 What It Does

- 📥 **Reads incoming job application emails** (via Gmail API)  
- 📑 **Extracts candidate details** (resume, cover letter, etc.)  
- 🧠 **Retrieves job requirements** from internal documentation using Pinecone + embeddings  
- 💬 **Generates candidate analysis and ranking** using GPT-4o and contextual prompt templates  
- 🗂️ **Logs summaries and scores** in a Google Sheet for team review  
- 🚩 **Flags unclear or incomplete applications** for manual review

---

## 🛠 Tech Stack

| Tool             | Purpose                                                             |
|------------------|----------------------------------------------------------------------|
| **n8n**          | No-code orchestration for the full automation pipeline               |
| **OpenAI GPT-4o**| LLM to analyze and score candidates based on job criteria            |
| **Pinecone**     | Vector store for job requirement embeddings and semantic search      |
| **LangChain**    | Agent memory, prompt modularity, and RAG integration                 |
| **Google Sheets**| Stores output, scores, and unanswered items                          |
| **Gmail API**    | Triggers on incoming job applications and supplies message content   |

---

## 🧩 Workflow Architecture

Gmail → n8n → Extract Application → Embed + Search (Pinecone) → GPT-4o → Score + Summary → Google Sheets


Each incoming email is embedded → matched to job criteria via Pinecone → passed into GPT-4o → candidate is scored and logged → team receives a human-readable summary.

---

## 📦 Installation & Usage

### 1. Requirements

- A working **n8n** instance (self-hosted or cloud)
- Accounts/API keys for:
  - OpenAI
  - Pinecone
  - Google (OAuth setup for Gmail and Sheets)

### 2. Import Workflow

1. Download the `ai-hiring-assistant.json` file in this repo  
2. Log into your n8n workspace  
3. Click the **Import** icon on your dashboard  
4. Upload the JSON file to view/edit the workflow  

### 3. Customize

- Update API credentials and webhook triggers  
- Replace placeholder prompts and field mappings to match your team’s hiring needs  
- Configure Gmail labels or filters for target emails  

---

## 🔐 Security Considerations

- OAuth 2.0 used for Gmail API access  
- No candidate data is stored long-term in this workflow  
- Error handling is built in to avoid accidental replies or infinite loops

---

## 📸 Screenshots

*Add screenshots here if desired — e.g., n8n flow, Google Sheets output, etc.*

---

## 🧠 Why This Matters

Hiring teams spend hours manually reviewing applications — especially in high-volume roles. This assistant removes the grunt work and delivers consistent, criteria-aligned analysis using AI, while still keeping humans in the loop for edge cases.

---

## 📬 Questions or Contributions?

Feel free to fork this repo, raise issues, or suggest improvements.  
For inquiries, contact: **henry@arcnetlabs.com**

---

## 📄 License

Open-source under [MIT License](LICENSE). Use freely, adapt responsibly.

