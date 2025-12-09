# Multi-Agent Research System

A sophisticated AI-powered research system built with n8n that orchestrates multiple AI agents to conduct comprehensive research on any topic. Inspired by [Anthropic's multi-agent research architecture](https://www.anthropic.com/research/building-effective-agents).

## 🎯 What It Does

This system autonomously researches any topic by:
1. **Clarifying** your research request through a Customer Support Agent
2. **Planning** research tasks via a Lead Agent (Orchestrator)
3. **Executing** parallel web searches through multiple Search Subagents
4. **Synthesizing** findings into a comprehensive markdown report via a Copywriter Agent
5. **Delivering** the final report to Google Drive

### Example Use Cases
- Market research and competitor analysis
- Industry trend analysis
- Product management research
- Technical documentation research
- Academic literature reviews

## 🏗️ Architecture

The system consists of four main agent types:
```
User Query
    ↓
Customer Support Agent (clarifies request)
    ↓
Lead Agent (Orchestrator) ←→ 3-12 Search Subagents (parallel execution)
    ↓
Copywriter Agent
    ↓
Google Drive (final report)
```

### Agent Responsibilities

| Agent | Purpose | Key Features |
|-------|---------|--------------|
| **Customer Support Agent** | Clarifies user requests and defines research scope | Structured JSON output, conversational memory |
| **Lead Agent (Orchestrator)** | Plans research tasks and coordinates subagents | Creates 3-12 research tasks, iterative refinement |
| **Search Subagent** | Executes specific research tasks | Web search via Brave API, website analysis via ScrapingAnt |
| **Copywriter Agent** | Synthesizes final report | Markdown formatting, structured output, iterative refinement |


### API Keys Required

| Service | Purpose | Cost | Sign Up |
|---------|---------|------|---------|
| **OpenRouter** | Unified LLM access (GPT-4, Claude, etc.) | Pay-per-use (~$0.12/report) | [openrouter.ai](https://openrouter.ai) |
| **Brave Search API** | Web search | $5/month (free tier available) | [brave.com/search/api](https://brave.com/search/api) |
| **ScrapingAnt** | Website content extraction | $12/month (free tier: 1k credits) | [scrapingant.com](https://scrapingant.com) |
| **Google Drive** (optional) | Report storage | Free | Google account required |

## n8n Workflow
<img width="1273" height="365" alt="Screenshot 2025-12-09 at 4 36 29 PM" src="https://github.com/user-attachments/assets/fa8f9524-6dd1-401f-b35b-fe8d8d31ee84" />
<img width="649" height="511" alt="Screenshot 2025-12-09 at 4 36 55 PM" src="https://github.com/user-attachments/assets/13eff643-4e80-4859-91d0-ae3c8aa21de3" />
