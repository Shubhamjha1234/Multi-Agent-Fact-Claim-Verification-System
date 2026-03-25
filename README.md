# 🧠 Multi-Agent Fact & Claim Verification System

An AI-driven, multi-agent fact-checking system built using **n8n**, large language models, and real-time web search.
The system automatically extracts claims from text or URLs, retrieves evidence from trusted sources, verifies factual accuracy, and generates a structured accuracy report with citations and confidence scores.

---

# 🚀 Project Overview

The rapid growth of AI-generated content and online information has increased the risk of misinformation and hallucinated outputs.
Manual fact-checking is slow, expensive, and not scalable.

This project solves that problem by building an **automated multi-agent verification pipeline** that:

1. Extracts verifiable claims from input text or URLs
2. Searches real-world sources using web search APIs
3. Validates claims against retrieved evidence
4. Generates a structured accuracy report

The system is designed for:

* AI content validation
* News verification
* Compliance workflows
* Research automation
* Enterprise data reliability

---

# 🏗 System Architecture

User Input (Chat / Webhook / API)
│
▼
Claim Extraction Agent
│
▼
Split Claims Processor
│
▼
Research Agent
├── Google Search Agent
│      └── Tavily Search
├── Social Media Agent
│      ├── Instagram
│      ├── LinkedIn
│      └── X (Twitter)
└── Company Research Agent
└── Explorium Data Enrichment
│
▼
Verification Agent
│
▼
Accuracy Report Generator
│
▼
Webhook / UI Response

---

# 🧩 Key Features

## Automated Claim Extraction

* Converts paragraphs into discrete factual claims
* Removes opinions and questions
* Handles multiple claims in one input

Example:

Input:
"Tesla was founded in 2003 and is headquartered in Texas."

Output:
[
"Tesla was founded in 2003",
"Tesla is headquartered in Texas"
]

---

## Real-Time Evidence Retrieval

The system automatically searches the internet for supporting evidence using:

* Tavily Search API
* Web sources
* Knowledge bases
* Company data enrichment

It retrieves:

* Titles
* URLs
* Snippets
* Source metadata

---

## Intelligent Verification Engine

Each claim is evaluated against retrieved evidence and classified as:

True
False
Partially True
Unverifiable

The system also calculates:

* Confidence score
* Reasoning explanation
* Supporting citations

---

## Structured Accuracy Report

Example output:

```json
{
  "claim": "Trump is the PM of USA",
  "verdict": "False",
  "confidence": 100,
  "reasoning": "The United States does not have a Prime Minister. The head of government is the President.",
  "sources": [
    {
      "title": "Head of Government",
      "url": "https://en.wikipedia.org/wiki/Head_of_government",
      "snippet": "In the United States, the head of government is the President."
    }
  ]
}
```

---

# 🛠 Technology Stack

## Workflow Automation

n8n
Low-code automation platform used to orchestrate agents and APIs.

## AI Models

* Google Gemini
* OpenAI
* LLM-based reasoning models

Used for:

* Claim extraction
* Evidence reasoning
* Fact verification

## Search Integration

* Tavily API
* Web search
* Knowledge retrieval

## Data Enrichment

* Explorium MCP Client

Used for structured company intelligence.

## Backend

n8n Webhooks
REST API endpoints

## Frontend (Optional)

* React
* Next.js
* Streamlit
* Custom Web UI

---

# 🔄 Workflow Pipeline

Step 1 — Receive Input

The system accepts:

* Plain text
* News article URLs
* API requests
* Chat messages

---

Step 2 — Extract Claims

The Claim Extraction Agent identifies factual statements.

---

Step 3 — Retrieve Evidence

The Research Agent searches trusted sources.

---

Step 4 — Verify Claims

The Verification Agent compares claims against evidence.

---

Step 5 — Generate Report

The system produces a structured accuracy report.

---

# 📦 Installation

## 1) Clone the Repository

```bash
git clone https://github.com/your-username/fact-checking-system.git
cd fact-checking-system
```

---

## 2) Install n8n

```bash
npm install -g n8n
```

---

## 3) Start n8n

```bash
n8n start
```

---

## 4) Import Workflow

Open:

n8n Editor
→ Import Workflow
→ Upload:

workflow.json

---

# 🔑 Environment Variables

Create a `.env` file:

```
TAVILY_API_KEY=your_key
GEMINI_API_KEY=your_key
OPENAI_API_KEY=your_key
EXPLORIUM_API_KEY=your_key
```

---

# 🌐 API Usage

## Endpoint

POST /webhook/fact-check

---

## Request

```json
{
  "text": "Tesla was founded in 2003"
}
```

---

## Response

```json
{
  "claim": "Tesla was founded in 2003",
  "verdict": "True",
  "confidence": 95,
  "reasoning": "Multiple sources confirm Tesla was founded in 2003.",
  "sources": [...]
}
```

---

# 🧪 Example Test Cases

## False Claim

Input:

"Trump is the Prime Minister of the USA"

Expected:

Verdict: False

---

## True Claim

Input:

"The capital of Australia is Canberra"

Expected:

Verdict: True

---

## Multiple Claims

Input:

"Tesla was founded in 2003 and Elon Musk is the CEO"

Expected:

Two verification results

---

## Unverifiable Claim

Input:

"Aliens built the pyramids"

Expected:

Verdict: Unverifiable

---

# 📊 Evaluation Metrics

Accuracy
Correct classification of claims

Evidence Retrieval
Relevant and authoritative sources

Verification Logic
Evidence-based reasoning

Explainability
Clear reasoning and citations

User Experience
Readable accuracy reports

---

# 🧠 Multi-Agent Design

The system uses specialized agents:

Claim Extraction Agent
Identifies factual claims

Research Agent
Searches for evidence

Google Agent
Handles web search

Social Media Agent
Analyzes social platforms

Company Research Agent
Retrieves company intelligence

Verification Agent
Determines claim validity

---

# 🔒 Reliability Features

Retry logic
Rate limit protection
Structured output validation
Fallback model support
Error handling

---

# ⚡ Performance Optimizations

Batch processing
Caching
Search result limits
Controlled agent iterations
Token usage optimization

---

# 🎯 Use Cases

AI content validation
News fact checking
Research verification
Compliance automation
Enterprise data quality
Educational tools

---

# 🧩 Future Improvements

AI-generated text detection
Deepfake media detection
Source credibility scoring
Knowledge graph integration
Multi-language support
Streaming responses

---

# 📂 Project Structure

```
fact-checking-system/

workflow.json
README.md
.env.example

src/
  agents/
  prompts/
  tools/

docs/
  architecture.png
  demo-video.mp4
```

---

# 🎥 Demo

The system demonstrates:

1. True claim verification
2. False claim detection
3. Conflicting evidence handling

Demo duration:

10 minutes

---

# 🤝 Contributing

Pull requests are welcome.

Steps:

Fork repository
Create feature branch
Commit changes
Submit pull request

---

# 📄 License

MIT License

---

# 👤 Author

Shubham Jha

AI / Automation Engineer

---

# ⭐ Acknowledgments

n8n
OpenAI
Google Gemini
Tavily
Explorium
