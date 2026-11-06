# 🎓 EDUAGENT – Autonomous Multi-Agent AI Education Platform

### Less Time Managing Education. More Time Learning.

EDUAGENT is an AI-powered educational assistance platform designed to reduce the time and effort students spend managing different academic activities.

Students often switch between multiple platforms to understand difficult concepts, find academic resources, discover educational videos, prepare study schedules and evaluate their knowledge.

Although these activities are individually simple, managing them across different platforms consumes valuable study time.

**EDUAGENT aims to bridge this gap by bringing multiple academic activities into one coordinated platform powered by specialised AI agents.**

---

## 🚀 Problem Statement

Students face several challenges during their academic preparation:

- Finding reliable academic resources takes time.
- Understanding difficult concepts requires additional learning support.
- Searching for relevant educational videos across multiple platforms can be inefficient.
- Preparing personalised study schedules requires planning and organisation.
- Students often lack a convenient way to evaluate their understanding and identify weak topics.

The central problem is not the lack of educational resources. It is the time and effort required to discover, organise and use them effectively.

### Our Solution

EDUAGENT provides a unified educational environment where students can access different academic services through a coordinated multi-agent architecture.

Instead of handling every request through a single general-purpose workflow, the platform is designed around specialised agents, each responsible for a particular educational task.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| AI Academic Tutor | Explains academic concepts with structured, student-friendly responses. |
| Academic Research | Helps discover academic books and reference materials. |
| Video Discovery | Finds relevant educational lectures and learning videos. |
| Study Planner | Generates structured study schedules and preparation roadmaps. |
| Assessment System | Generates quizzes and evaluates student understanding. |
| Student Performance Analysis | Analyses academic performance to identify strengths and weaknesses. |
| Domain Guard | Restricts assistance to academic and educational topics. |
| Agent Execution Trace | Displays the stages involved in processing requests. |
| Gemini API Management | Supports API key rotation and failover handling. |

---

## 🧠 Multi-Agent Architecture

EDUAGENT follows a specialised multi-agent design.

Each agent is responsible for a specific academic activity.

### 1. Academic Tutor Agent

- Explains complex academic concepts.
- Provides structured explanations.
- Supports syllabus-oriented learning.
- Helps students understand difficult topics.

### 2. Academic Research Agent

- Discovers relevant academic books and references.
- Provides descriptions and source information.
- Distinguishes open-access resources from commercial references.

### 3. Video Discovery Agent

- Finds educational videos related to academic topics.
- Supports syllabus-oriented video discovery.
- Provides relevant lecture resources.

### 4. Semester Study Planner Agent

- Creates personalised study schedules.
- Organises preparation into study and revision phases.
- Includes buffer days and mock-test sessions.
- Helps students manage their academic preparation.

### 5. Academic Assessment Agent

- Generates multiple-choice questions.
- Evaluates student answers.
- Identifies knowledge gaps.
- Supports diagnostic learning.

---

## ⚙️ How the Orchestrator Works

The Orchestrator, also called the Academic Coordinator, acts as the central management component of the multi-agent system.

Its responsibility is to coordinate academic requests and direct them towards the appropriate workflow.

### Request Processing Pipeline

```text
              STUDENT REQUEST
                     |
                     v
             REQUEST ANALYSIS
                     |
                     v
                DOMAIN GUARD
                     |
                     v
             INTENT / KEYWORD
                  ROUTING
                     |
          +----------+----------+
          |          |          |
          v          v          v
        TUTOR     RESEARCH    VIDEO
        AGENT      AGENT      AGENT
          |
          +----------+----------+
                     |
          +----------+----------+
          |                     |
          v                     v
      STUDY PLANNER         ASSESSMENT
         AGENT                AGENT
          |                     |
          +----------+----------+
                     |
                     v
              RESULT VALIDATION
                     |
                     v
             RESPONSE DELIVERY
                     |
                     v
                  STUDENT
```

### Orchestration Process

1. **Request Analysis:** Receives and analyses the student's academic request.
2. **Domain Validation:** Checks whether the request belongs to the educational domain.
3. **Task Routing:** Uses keyword-based routing logic to identify the appropriate workflow.
4. **Agent Execution:** Delegates the task to the corresponding specialised agent.
5. **Result Validation:** Validates and sanitises the generated response.
6. **Response Delivery:** Returns the result to the student.

The Python coordinator also supports a composite workflow in which the Tutor Agent explains a topic and the Assessment Agent generates practice questions.

---

## 🤖 AI Integration – Google Gemini SDK

EDUAGENT integrates Google's Gemini models through the official Google GenAI SDK.

The SDK provides the communication interface between the application backend and the Gemini model.

The application provides:

- Student queries.
- System instructions.
- Academic context.
- Relevant learning information.

Gemini processes the supplied context and generates language-based responses.

### API Reliability

The backend includes a Gemini API management mechanism that supports:

- Multiple API key configuration.
- Round-robin key rotation.
- Failure detection.
- Automatic failover.
- Temporary recovery cooldowns.
- Alternative model attempts.

API key rotation helps handle temporary availability and rate-limit failures. It does not increase the quota allocated to an individual API key.

---

## 📚 Document Processing and Retrieval

The Python implementation includes document-processing and retrieval services.

The general workflow is:

```text
       PDF DOCUMENT
             |
             v
       TEXT EXTRACTION
             |
             v
       TEXT CHUNKING
             |
             v
       LOCAL STORAGE
             |
             v
       KEYWORD RETRIEVAL
             |
             v
       RELEVANT CONTEXT
             |
             v
       AI RESPONSE
```

This approach helps identify relevant academic information from uploaded documents.

The current retrieval implementation uses keyword-based matching rather than a vector-embedding database.

---

## 🏗️ Technology Stack

### Frontend
- React
- TypeScript
- Vite
- Tailwind CSS
- Lucide React

### Backend
- Node.js
- Express.js
- Python
- Streamlit

### Artificial Intelligence
- Google Gemini
- Google GenAI SDK
- Multi-Agent Architecture

### Data Processing and Storage
- SQLite
- PyMuPDF
- Python
- Document Retrieval Services

### External Integration
- YouTube Data API v3
- Educational resource sources

---

## 📂 Project Structure

```text
EDUAGENT/
│
├── agents/
│   ├── academic_tutor.py
│   ├── research_agent.py
│   ├── video_agent.py
│   ├── study_planner.py
│   └── assessment_agent.py
│
├── core/
│   ├── coordinator.py
│   ├── agent_base.py
│   ├── domain_guard.py
│   ├── api_manager.py
│   └── security.py
│
├── services/
│   ├── document_service.py
│   ├── retrieval_service.py
│   ├── study_service.py
│   ├── syllabus_service.py
│   └── web_research.py
│
├── database/
│
├── config/
│
├── ui/
│
├── src/
│   └── React frontend files
│
├── server.ts
├── app.py
├── package.json
├── requirements.txt
├── .env.example
└── README.md
```

---

## 💻 Installation and Setup

EDUAGENT contains a TypeScript/React application and a separate Python/Streamlit implementation.

### Prerequisites

- Python 3.10+
- Node.js 20+
- npm
- Google Gemini API key

### 1. Clone the Repository

```bash
git clone YOUR_REPOSITORY_URL
```

```bash
cd YOUR_REPOSITORY_FOLDER
```

### 2. Configure Environment Variables

Create a `.env` file in the project root.

```env
GEMINI_API_KEY=your_gemini_api_key

GEMINI_API_KEY_1=your_first_api_key
GEMINI_API_KEY_2=your_second_api_key
GEMINI_API_KEY_3=your_third_api_key

GEMINI_FLASH_MODEL=gemini-3.1-flash-lite

YOUTUBE_API_KEY=your_youtube_api_key

ADMIN_PASSWORD=your_secure_admin_password
```

Use your own API credentials. Never upload real API keys, passwords or other secrets to GitHub.

### 3. Run the React + TypeScript Application

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

### 4. Run the Python Application

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the Streamlit application:

```bash
streamlit run app.py
```

The Streamlit application will normally be available at:

```text
http://localhost:8501
```

---

## 🔐 Security Notes

- Store API credentials in environment variables.
- Never commit `.env` files.
- Replace all example credentials with placeholders before publishing.
- Use strong administrator passwords.
- Avoid exposing sensitive information in application logs.
- Rotate any API credentials accidentally committed to a public repository.

---

## 🔭 Future Scope

Potential improvements include:

- Integrating the TypeScript and Python agent implementations into one unified execution pipeline.
- Implementing semantic search using vector embeddings.
- Adding advanced student learning analytics.
- Introducing more sophisticated natural-language intent classification.
- Supporting additional educational content formats.
- Improving adaptive learning recommendations.
- Implementing token-budget-based context optimisation.
- Supporting multilingual academic assistance.

---

## 🎯 Our Vision

We believe students should spend more time learning and less time managing the process of learning.

EDUAGENT aims to make academic preparation more organised, accessible and personalised through coordinated AI-powered educational assistance.

**EDUAGENT — Learn Smarter. Save Time. Achieve More.**

---

## 👨‍💻 Project Information

**Project:** EDUAGENT – Autonomous Multi-Agent AI Education Platform

**Category:** Agentic AI | Education Technology | Artificial Intelligence

**Core Concept:** Specialised AI Agents + Central Orchestration

**AI Integration:** Google Gemini SDK

**Status:** Development / Prototype

---

*Built to make learning more organised, efficient and accessible.*


Author : Karna Rishik
