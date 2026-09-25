# 🍳 AI Chef — Multimodal AI Recipe Agent

AI Chef is a multimodal AI Agent application built with LangChain / LangGraph.  
Users can upload photos of ingredients, and the AI automatically recognizes available ingredients, searches for suitable recipes, and provides personalized cooking suggestions through natural-language conversations.

## ✨ Features

### 📷 Multimodal Ingredient Recognition
Upload an image of ingredients from your refrigerator or kitchen. The multimodal model analyzes the image and identifies available ingredients automatically.

### 🔍 Intelligent Recipe Search
The Agent searches for relevant recipes based on recognized ingredients and user requirements.

### 🤖 AI Agent Workflow
The system uses an Agent-based architecture to understand user requests, decide which tools to call, execute them, and generate a final response.

Typical workflow:

User Input  
↓  
Image / Text Understanding  
↓  
Agent Reasoning  
↓  
Tool Selection & Execution  
↓  
Recipe Search / Analysis  
↓  
AI-generated Recommendation

### 🥗 Personalized Recommendations
Recipes can be recommended according to factors such as:

- Available ingredients
- Cooking difficulty
- User requirements
- Nutrition considerations
- Recipe relevance

### 💡 Creative Cooking Suggestions
When no suitable recipe is found, the Agent can generate creative meal ideas based on the ingredients currently available.

### 💬 Conversational Interaction
Users can continuously interact with the AI Chef through natural-language conversations and refine their cooking requirements.

---

## 🏗 Architecture

```text
                    ┌─────────────────┐
                    │      User       │
                    └────────┬────────┘
                             │
                    Image / Text Input
                             │
                             ▼
                    ┌─────────────────┐
                    │   AI Chef API   │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ LangGraph Agent │
                    └────────┬────────┘
                             │
                  ┌──────────┼──────────┐
                  ▼          ▼          ▼
            Multimodal    Recipe      Search
               Model       Tools       Tools
                  │          │          │
                  └──────────┼──────────┘
                             ▼
                    ┌─────────────────┐
                    │ AI Recommendation│
                    └─────────────────┘
```

---

## 🛠 Tech Stack

**AI / Agent**

- LangChain
- LangGraph
- Large Language Models
- Multimodal LLM
- Tool Calling

**Backend**

- Python
- LangGraph API

**AI Services**

- DeepSeek
- DashScope
- Tavily Search
- LangSmith

**Storage**

- Object Storage Service (OSS)

---

## 📁 Project Structure

```text
My_first_project/
├── src/                 # Main application source code
├── langgraph.json       # LangGraph configuration
├── pyproject.toml       # Python dependencies
├── uv.lock              # Dependency lock file
├── .env.example         # Environment variable template
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/codingcode1101/My_first_project.git
cd My_first_project
```

### 2. Install dependencies

Make sure Python and `uv` are installed.

```bash
uv sync
```

### 3. Configure environment variables

Create a `.env` file based on `.env.example`.

```env
DEEPSEEK_API_KEY=your_api_key
DASHSCOPE_BASE_URL=your_base_url
DASHSCOPE_API_KEY=your_api_key
TAVILY_API_KEY=your_api_key

LANGSMITH_API_KEY=your_api_key
LANGSMITH_TRACING=true
LANGSMITH_PROJECT=your_project

OSS_ACCESS_KEY_ID=your_access_key
OSS_ACCESS_KEY_SECRET=your_secret
OSS_BUCKET=your_bucket
```

> Never commit real API keys or credentials to GitHub.

### 4. Run the application

Start the LangGraph development server according to your local environment.

---

## 🔐 File Upload Design

Multimodal files are not directly encoded as Base64 and sent through the entire Agent request.

Instead, the system follows this workflow:

```text
Frontend
   │
   │ Request upload authorization
   ▼
Backend
   │
   │ Generate OSS upload authorization
   ▼
Frontend ──────► OSS
                  │
                  │ File URL
                  ▼
              AI Agent
```

This avoids transferring large image data through the application server and reduces unnecessary memory and request overhead.

---

## 📸 Demo

> Add screenshots or GIF demonstrations here.

Example:

- Ingredient image upload
- Ingredient recognition result
- Recipe recommendation
- Agent conversation
- Final cooking suggestion

---

## 🎯 Project Highlights

- Built a multimodal AI Agent capable of processing both image and text input.
- Designed an Agent workflow combining LLM reasoning with external tool calling.
- Integrated recipe search and AI-generated recommendations into a conversational experience.
- Designed an OSS-based direct-upload workflow for multimodal files instead of transferring Base64 files through the backend.
- Added LangSmith support for Agent tracing and debugging.

---

## 👨‍💻 Author

Leo Liu

Software Engineering  
Nanjing University of Posts and Telecommunications
