# Section 0: Introduction

> What is Claude, why it matters, and how to get started in under 15 minutes.

📺 **Video reference**: [0:00 – 6:37](https://www.youtube.com/watch?v=oS1RvuLPGbA&t=0s)

---

## What Is Claude?

Claude is an AI assistant created by [Anthropic](https://www.anthropic.com). Think of it as a very capable colleague who can:

- **Write** — emails, articles, business plans, marketing copy, code
- **Analyze** — documents, data, spreadsheets, images
- **Create** — websites, applications, presentations, diagrams
- **Automate** — repetitive tasks, workflows, data processing
- **Reason** — solve complex problems, make recommendations, plan strategies

### Claude vs. Other AIs

| Feature | Claude | ChatGPT | Gemini |
|---------|--------|---------|--------|
| Long documents (200K+ tokens) | Yes | Limited | Yes |
| Built-in code execution | Yes (Artifacts) | Yes | Yes |
| Projects with persistent memory | Yes | Yes | Limited |
| File uploads & analysis | Yes | Yes | Yes |
| Image understanding | Yes | Yes | Yes |
| Coding & app building | Excellent | Good | Good |

**Why Claude specifically?** Claude excels at following complex instructions precisely, handling long documents, producing high-quality writing, and building functional applications through Artifacts and Claude Code.

---

## Claude's Product Ecosystem

```
Claude AI Ecosystem
├── claude.ai ─────────── Web interface (chat, projects, artifacts)
├── Claude Code ───────── CLI tool for building software
├── Claude API ────────── For developers building AI-powered apps
├── Claude for Teams ──── Collaboration features for organizations
└── Claude Mobile App ─── iOS & Android access
```

### What You'll Use in This Guide

| Tool | What It Does | When You'll Use It |
|------|-------------|-------------------|
| **claude.ai** | Chat interface, Projects, Artifacts | Sections 0–3 |
| **Claude Code** | Build websites & apps from your terminal | Sections 3–6 |
| **n8n** | Visual automation builder | Section 5 |
| **MCP** | Connect Claude to external tools | Sections 5–6 |

---

## Step-by-Step: Create Your Account

### Step 1: Sign Up

1. Go to [claude.ai](https://claude.ai)
2. Click **"Sign Up"**
3. Use your email or Google/Apple account
4. Verify your email address

### Step 2: Choose Your Plan

| Plan | Price | Best For |
|------|-------|----------|
| **Free** | $0/month | Trying Claude, light usage |
| **Pro** | $20/month | Regular use, longer conversations, Projects |
| **Max** | $100/month | Heavy use, priority access, advanced features |
| **Team** | $25/user/month | Collaboration, shared projects |

**Recommendation**: Start with **Free** to follow Section 0–1. Upgrade to **Pro** when you reach Section 2 (you'll want Projects and higher limits).

### Step 3: First Conversation

Once logged in, you'll see the chat interface. Type your first message:

```
Hello Claude! I'm learning how to use you effectively.
Can you tell me 3 things you're really good at,
and 1 thing you can't do?
```

This simple prompt teaches you something important: **Claude is transparent about its capabilities and limitations.**

---

## Understanding How Claude Thinks

### The Conversation Model

Claude doesn't "remember" between separate conversations. Each new conversation starts fresh. This means:

- **Within a conversation**: Claude remembers everything you've said
- **Between conversations**: Claude starts with a blank slate
- **With Projects**: Claude retains custom instructions and knowledge across conversations

### Context Window

Claude can process approximately **200,000 tokens** in a single conversation — roughly equivalent to a 500-page book. This means you can:

- Upload and analyze entire documents
- Have very long, detailed conversations
- Provide extensive context and instructions

### How to Get Better Results

The quality of Claude's output depends on the quality of your input. Think of it like giving instructions to a new employee:

| Bad Instruction | Good Instruction |
|----------------|-----------------|
| "Write something about marketing" | "Write a 500-word blog post about email marketing for small e-commerce businesses. Include 3 actionable tips with examples." |
| "Analyze this" | "Analyze this sales spreadsheet. Identify the top 3 performing products by revenue, and explain any seasonal trends you notice." |
| "Make it better" | "Rewrite this paragraph to be more concise (under 50 words) while keeping the main argument about customer retention." |

---

## Exercise: Your First 5 Prompts

Practice these prompts to get comfortable with Claude:

### Prompt 1 — Simple Question
```
What are the 5 most important things a beginner should know
about using AI assistants effectively?
```

### Prompt 2 — Creative Task
```
Write a professional email to a client explaining that
their project will be delivered 2 days late due to
unexpected technical issues. Keep it under 150 words,
apologetic but confident.
```

### Prompt 3 — Analysis
```
Compare the pros and cons of starting a freelance business
vs. a product-based business in 2026. Present your analysis
in a table format.
```

### Prompt 4 — Step-by-Step Guide
```
Give me a step-by-step plan to learn social media marketing
in 30 days. Include specific daily actions and free resources.
Format it as a weekly schedule.
```

### Prompt 5 — Document Creation
```
Create a one-page business proposal template for an AI
consulting service. Include sections for: problem statement,
proposed solution, timeline, pricing, and next steps.
```

---

## Key Takeaways

- Claude is an AI assistant that can write, analyze, create, and automate
- Start with the free plan, upgrade to Pro when you need Projects
- The quality of your output depends on the quality of your input
- Each conversation starts fresh unless you use Projects
- Practice with simple prompts before moving to complex tasks

---

## Next Step

You're ready to learn the foundations. Head to **[Section 1: Foundations](../01-fondations/README.md)** to master Claude's interface, Projects, and custom instructions.
