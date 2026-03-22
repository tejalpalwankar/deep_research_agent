# 🚀 Deep Research Agent

**Multi-Agent AI System for End-to-End Research Automation**

---

## 📌 Overview

Deep Research Agent is a **multi-agent AI system** that transforms a simple query into a **structured, in-depth research report**, using a coordinated pipeline of specialized agents.

Instead of directly answering queries, the system:

1. **Clarifies the intent**
2. **Plans research strategy**
3. **Performs web searches**
4. **Synthesizes insights into a report**
5. **Optionally sends results via email**

This mimics how a real research team operates — but fully automated.

---

## 🧠 System Architecture

The system is built using an **agent orchestration pattern**, where each agent has a clearly defined responsibility.

### 🔹 Agent Flow

```
User Query
   ↓
Clarifier Agent → Refines query via questions
   ↓
Planner Agent → Breaks problem into search tasks
   ↓
Search Agent → Performs web searches
   ↓
Writer Agent → Generates structured report
   ↓
Email Agent → Sends formatted output (optional)
```

---

## ⚙️ Core Components

### 1. Clarifier Agent

* Generates **3 targeted questions** to refine user intent
* Prevents vague or low-quality research inputs
* Uses structured output via Pydantic

📄 Reference: 

---

### 2. Planner Agent

* Breaks query into **5 strategic search queries**
* Adds reasoning for each search
* Improves coverage and depth of research

📄 Reference: 

---

### 3. Search Agent

* Uses web search tool to fetch information
* Produces **concise summaries (≤300 words)**
* Optimized for downstream synthesis

📄 Reference: 

---

### 4. Writer Agent

* Converts raw search outputs into a **structured report**
* Generates:

  * Summary
  * Detailed markdown report (1000+ words)
  * Follow-up questions

📄 Reference: 

---

### 5. Email Agent

* Converts report into **HTML format**
* Sends via SendGrid API

📄 Reference: 

---

### 6. Research Manager (Coordinator)

* Orchestrates full pipeline
* Handles:

  * Planning
  * Parallel search execution
  * Report generation
  * Email sending

📄 Reference: 

---

### 7. UI Layer (Gradio)

* Interactive interface for:

  * Query input
  * Clarifying questions
  * Report display
  * Email toggle

📄 Reference: 

---

## 🔐 Rate Limiting & Control

The system includes a custom **RateLimiter**:

* 2 requests per minute
* 10 requests per day
* Tracks users via request headers/IP

Prevents abuse and simulates production constraints.

---

## 🚀 Features

* ✅ Multi-agent orchestration (Planner + Search + Writer + Email)
* ✅ Structured outputs using Pydantic
* ✅ Async pipeline with parallel search execution
* ✅ Real-time streaming responses
* ✅ Gradio UI for interaction
* ✅ Email delivery via SendGrid
* ✅ Rate limiting for production-like behavior
* ✅ OpenAI trace integration for debugging

---

## 🛠️ Tech Stack

* **Python**
* **OpenAI Agents SDK**
* **Gradio**
* **Pydantic**
* **AsyncIO**
* **SendGrid API**
* **dotenv**

---

## 📂 Project Structure

```
deep_research/
│
├── deep_research.py        # Main UI + pipeline entry
├── research_manager.py     # Orchestrator
├── planner_agent.py        # Search planning
├── search_agent.py         # Web search execution
├── writer_agent.py         # Report generation
├── clarifier_agent.py      # Query refinement
├── email_agent.py          # Email delivery
```

---

## ▶️ How to Run

### 1. Clone repo

```bash
git clone https://github.com/YOUR_USERNAME/deep_research_agent.git
cd deep_research_agent
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set environment variables

Create `.env` file:

```env
OPENAI_API_KEY=your_key
SENDGRID_API_KEY=your_key
```

---

### 4. Run the app

```bash
python deep_research.py
```

---

## 💡 Example Use Case

Input:

```
"Impact of AI on healthcare"
```

Flow:

* Clarifier asks:

  * Which region?
  * Which use case?
  * Time horizon?
* System performs targeted searches
* Generates:

  * Structured report
  * Key insights
  * Follow-up research questions
* Optional: sends via email

---

## 🧪 Design Decisions (Interview Ready)

* **Why multi-agent?**
  Separation of concerns → better reasoning + modularity

* **Why clarifier step?**
  Improves input quality → better downstream output

* **Why async searches?**
  Parallel execution reduces latency

* **Why structured outputs?**
  Ensures reliability between agents

---

## 🔮 Future Improvements

* Memory layer (vector DB for past queries)
* Cost optimization (token tracking)
* Better search ranking
* UI improvements (history, export PDF)
* Multi-user authentication

---

## ⚠️ Disclaimer

This project is based on a tutorial and has been **extended and customized** with:

* Rate limiting
* Full multi-agent orchestration
* Email integration
* Production-style pipeline design

---

## ⭐ Final Note

This project demonstrates:

* **Agentic AI design**
* **System thinking**
* **Production-level architecture**
* **End-to-end ownership**


