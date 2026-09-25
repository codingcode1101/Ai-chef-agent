# 🍳 AI Chef — Multimodal AI Recipe Agent

AI Chef is a multimodal AI Agent application built with **LangChain** and **LangGraph**.

Users can upload photos of ingredients, and the AI automatically recognizes available ingredients, searches for suitable recipes, and provides personalized cooking suggestions through natural-language conversations.

---

## ✨ Features

### 📷 Multimodal Ingredient Recognition

Upload an image of ingredients from your refrigerator or kitchen. The multimodal model analyzes the image and identifies available ingredients automatically.

### 🔍 Intelligent Recipe Search

The Agent searches for relevant recipes based on recognized ingredients and user requirements.

### 🤖 AI Agent Workflow

The system uses an Agent-based architecture to understand user requests, decide which tools to call, execute them, and generate a final response.

Typical workflow:

```text
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
```

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
                    ┌──────────────────┐
                    │ AI Recommendation│
                    └──────────────────┘
```

---

## 🛠 Tech Stack

### AI / Agent

- LangChain
- LangGraph
- Large Language Models (LLMs)
- Multimodal LLM
- Tool Calling

### Backend

- Python
- LangGraph API

### AI Services

- DeepSeek
- DashScope
- Tavily Search
- LangSmith

### Storage

- Object Storage Service (OSS)

---

## 📁 Project Structure

```text
Ai-chef-agent/
├── src/                 # Main application source code
├── .env.example         # Environment variable template
├── .gitignore           # Git ignored files
├── .python-version      # Python version configuration
├── langgraph.json       # LangGraph configuration
├── pyproject.toml       # Python project dependencies
├── uv.lock              # Dependency lock file
└── README.md            # Project documentation
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/codingcode1101/Ai-chef-agent.git
cd Ai-chef-agent
```

### 2. Install Dependencies

Make sure Python and `uv` are installed.

```bash
uv sync
```

### 3. Configure Environment Variables

Create a `.env` file based on `.env.example`.

```
