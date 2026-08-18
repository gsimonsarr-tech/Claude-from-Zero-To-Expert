# Claude: From Zero to Expert

## The Complete Guide to Mastering Claude AI

*Edited by Gabriel S. Sarr*

---

The step-by-step guide to mastering Claude AI. Build websites, applications, and automations without writing a single line of code.

**No coding experience required.**

---

*Companion Video: youtube.com/watch?v=oS1RvuLPGbA*

\newpage

# Table of Contents

- **Introduction** — What is Claude, why it matters, how to get started
- **Chapter 1: Foundations** — Interface, Projects, Knowledge Base, Custom Instructions
- **Chapter 2: AI Assistant** — Prompt engineering, structured prompts, custom assistants
- **Chapter 3: Build a Website** — Create and deploy websites with Claude
- **Chapter 4: Build an Application** — Build functional apps with Claude Code
- **Chapter 5: Automation** — Automate workflows with n8n + Claude
- **Chapter 6: AI Agents** — Create autonomous AI agents with MCP
- **Chapter 7: Business** — Monetize your AI skills
- **Resources** — All tools, links, and references

\newpage

# Who Is This Guide For?

- **Complete beginners** who have never used AI before
- **Entrepreneurs** looking to integrate AI into their business
- **Freelancers** wanting to offer AI-powered services
- **Curious minds** who want to understand what Claude can really do

## How to Use This Guide

This guide follows a progressive learning path. Each chapter builds on the previous one:

1. Start with the **Introduction** to understand what Claude is
2. Master the **Foundations** (interface, projects, instructions)
3. Work through each **Use Case** chapter with hands-on exercises
4. Apply what you've learned in the **Business** chapter

**Quick Reference**: Already familiar with Claude?

- "I want to write better prompts" → Chapter 2
- "I want to build a website" → Chapter 3
- "I want to build an app" → Chapter 4
- "I want to automate tasks" → Chapter 5
- "I want to create AI agents" → Chapter 6
- "I want to make money with AI" → Chapter 7

## Key Principles

1. **Practice over theory** — Every chapter includes hands-on exercises
2. **Progressive complexity** — Each chapter builds on the last
3. **Real-world results** — Everything you build is usable immediately
4. **No code required** — Claude handles the technical parts for you

## Prerequisites

- A computer with internet access
- A Claude account at claude.ai (free tier works to start)
- Willingness to experiment and iterate

\newpage

# Introduction: Getting Started with Claude

## What Is Claude?

Claude is an AI assistant created by Anthropic. Think of it as a very capable colleague who can:

- **Write** — emails, articles, business plans, marketing copy, code
- **Analyze** — documents, data, spreadsheets, images
- **Create** — websites, applications, presentations, diagrams
- **Automate** — repetitive tasks, workflows, data processing
- **Reason** — solve complex problems, make recommendations, plan strategies

**Why Claude specifically?** Claude excels at following complex instructions precisely, handling long documents, producing high-quality writing, and building functional applications through Artifacts and Claude Code.

## Claude's Product Ecosystem

Claude AI has several products:

- **claude.ai** — Web interface for chat, projects, and artifacts
- **Claude Code** — CLI tool for building software
- **Claude API** — For developers building AI-powered apps
- **Claude for Teams** — Collaboration features for organizations
- **Claude Mobile App** — iOS and Android access

## Create Your Account

**Step 1**: Go to claude.ai and click "Sign Up"

**Step 2**: Choose your plan:

- **Free** ($0/month) — Trying Claude, light usage
- **Pro** ($20/month) — Regular use, longer conversations, Projects
- **Max** ($100/month) — Heavy use, priority access, advanced features

**Recommendation**: Start with Free for the Introduction and Chapter 1. Upgrade to Pro when you reach Chapter 2.

**Step 3**: Type your first message:

> Hello Claude! I'm learning how to use you effectively. Can you tell me 3 things you're really good at, and 1 thing you can't do?

## Understanding How Claude Thinks

**Within a conversation**: Claude remembers everything you've said.

**Between conversations**: Claude starts with a blank slate.

**With Projects**: Claude retains custom instructions and knowledge across conversations.

**Context window**: Claude can process approximately 200,000 tokens — roughly equivalent to a 500-page book.

## How to Get Better Results

The quality of Claude's output depends on the quality of your input.

| Bad Instruction | Good Instruction |
|---|---|
| "Write something about marketing" | "Write a 500-word blog post about email marketing for small e-commerce businesses. Include 3 actionable tips." |
| "Analyze this" | "Analyze this sales spreadsheet. Identify the top 3 performing products and explain any seasonal trends." |
| "Make it better" | "Rewrite this paragraph to be more concise (under 50 words) while keeping the main argument." |

## Exercise: Your First 5 Prompts

**Prompt 1 — Simple Question**

> What are the 5 most important things a beginner should know about using AI assistants effectively?

**Prompt 2 — Creative Task**

> Write a professional email to a client explaining that their project will be delivered 2 days late. Keep it under 150 words, apologetic but confident.

**Prompt 3 — Analysis**

> Compare the pros and cons of starting a freelance business vs. a product-based business. Present in a table format.

**Prompt 4 — Step-by-Step Guide**

> Give me a step-by-step plan to learn social media marketing in 30 days. Include daily actions and free resources.

**Prompt 5 — Document Creation**

> Create a one-page business proposal template for an AI consulting service.

\newpage

# Chapter 1: Foundations

## The Claude Interface

When you open claude.ai, you'll find:

- **Sidebar** — New Chat, Projects, Recent conversations
- **Main Chat Area** — Where conversations happen
- **Attach Button** — Upload files, images, documents
- **Model Selector** — Choose between Claude models
- **Artifacts Panel** — Preview generated content

## Claude Models: Which One to Use?

- **Haiku 4.5** — Very fast, good quality. Best for quick questions and high-volume work.
- **Sonnet** — Fast, very good quality. Best for daily work, writing, analysis — 80% of your tasks.
- **Opus** — Slower, excellent quality. Best for complex reasoning, coding, critical tasks.

**Rule of thumb**: Use Sonnet for most work. Use Opus when quality matters more than speed. Use Haiku for quick answers.

## Projects: Your AI Workspace

Projects are the most powerful feature for getting consistent results. A Project is a dedicated workspace where Claude already knows your context.

**Without Projects:**

> You: "Write a marketing email for my SaaS product"
>
> Claude: "Sure! What's your product? Who's your audience? What tone?" (back and forth...)

**With Projects:**

> You: "Write a marketing email for the summer campaign"
>
> Claude: Already knows your product, audience, tone, brand guidelines. Delivers immediately.

### Create Your First Project

**Step 1**: Click "Projects" → "Create Project"

**Step 2**: Name it (e.g., "My Business Assistant")

**Step 3**: Add Custom Instructions — this is the system prompt that shapes every conversation:

> You are my business assistant. Here's what you need to know:
>
> ABOUT MY BUSINESS:
> - Company: [Your Company Name]
> - Industry: Digital marketing agency
> - Target clients: Small businesses with 10-50 employees
>
> MY PREFERENCES:
> - Communication style: Professional but friendly
> - Response length: Concise, use bullet points
> - Always include actionable next steps
>
> RULES:
> - Never invent statistics
> - Suggest tools with free tiers when possible
> - Format deliverables so they're ready to use

**Step 4**: Upload Knowledge Base files — documents Claude should reference (brand guidelines, product docs, templates, examples).

**Step 5**: Start a conversation within the project. Claude now has persistent context.

## Custom Instructions: Proven Templates

### Personal Assistant

> ROLE: You are my personal productivity assistant.
>
> CONTEXT: I am a [your role] at [your company]. My main responsibilities: [list them].
>
> BEHAVIOR: Be direct and concise. When I ask for a document, make it ready to send. If a task is ambiguous, make reasonable assumptions and state them.
>
> OUTPUT FORMAT: Use headers and bullet points. Include "Action Items" at the end.

### Content Creator

> ROLE: You are my content strategist and writer.
>
> BRAND VOICE: Tone: [Professional/Casual/Witty]. Audience: [describe]. Avoid: [words to never use].
>
> CONTENT RULES: SEO keywords naturally included. Short paragraphs (2-3 sentences). Every piece has a clear CTA.

### Research Analyst

> ROLE: You are my research analyst.
>
> METHODOLOGY: Always cite your reasoning. Distinguish facts from opinions. Present multiple perspectives.
>
> OUTPUT: Executive summary first. Detailed analysis with headers. Pros/cons in tables. Sources and limitations noted.

## Knowledge Base Best Practices

**Upload**: Brand guidelines, product docs, customer personas, past successful work, FAQ documents, process docs.

**Avoid uploading**: Sensitive credentials, constantly changing data, extremely large datasets, redundant documents.

**Tips**: Name files clearly. Keep files current. Summarize large documents first.

## Artifacts: Your Creation Panel

Artifacts create standalone content in a side panel: documents, code, web pages, diagrams, interactive apps.

To trigger: Ask Claude to create something standalone.

> Create a landing page for a coffee subscription service called "Morning Ritual". Use warm earth tones.

Claude generates the code and shows a live preview.

## Exercise: Set Up Your First Project

1. Go to claude.ai → Projects → Create Project
2. Name it "My Personal Assistant"
3. Add custom instructions (adapt the Personal Assistant template above)
4. Upload 1-2 relevant documents
5. Test with: "Based on what you know about me, suggest 3 ways I could use AI to save 5 hours per week."

\newpage

# Chapter 2: AI Assistant — Prompt Engineering

## The RICE Method

Every great prompt has four elements:

- **R — Role**: Who should Claude be?
- **I — Instructions**: What exactly should Claude do?
- **C — Context**: What background information is needed?
- **E — Examples**: What does good output look like?

### Bad vs. Good Prompt

**Bad**: "Write me a LinkedIn post"

**Good (RICE method)**:

> ROLE: You are a LinkedIn content strategist for B2B tech companies.
>
> INSTRUCTIONS: Write a LinkedIn post announcing our new AI tool. Hook the reader in the first line. Include 3 key benefits with metrics. End with a CTA. 150-200 words.
>
> CONTEXT: Our company (TechFlow) launched "ServiceAI" — reduces customer response time by 73%. Audience: CTOs and customer service managers.
>
> EXAMPLE TONE: "Last week, I watched a customer wait 47 minutes for a simple password reset..."

## Structured Prompting with XML Tags

Claude responds exceptionally well to XML-style tags:

> \<role\>Senior marketing strategist with 15 years in e-commerce\</role\>
>
> \<task\>Create a 90-day marketing plan for launching an organic skincare brand\</task\>
>
> \<constraints\>Budget: $5,000. Channels: Instagram, TikTok, Email only. No paid ads in first 30 days.\</constraints\>
>
> \<output_format\>Organize by month with weekly actions, KPIs, tools needed, and budget allocation in table format.\</output_format\>

**Why XML tags work**: Clear boundaries, no ambiguity, reusable sections, scalable structure.

## The Mega-Prompt Technique

A comprehensive prompt that produces professional output in a single shot:

> \# IDENTITY
> You are [specific role with experience].
>
> \# MISSION
> [One clear sentence about the goal]
>
> \# CONTEXT
> Industry, company stage, target audience, current situation, success criteria.
>
> \# DETAILED INSTRUCTIONS
> 1. [First major task with specifics]
> 2. [Second major task with specifics]
> 3. [Third major task with specifics]
>
> \# CONSTRAINTS
> Must/must not rules, tone, length.
>
> \# OUTPUT FORMAT
> Headers, sections, formatting details.
>
> \# QUALITY CRITERIA
> How to measure if the output is good.

## Multi-Turn Conversations

For complex tasks, break work into steps:

**Step 1 — Set Context**: Share your brand document. Ask Claude to confirm understanding.

**Step 2 — Strategy**: Request a content calendar with specifics for each post.

**Step 3 — Execution**: Ask Claude to write the full content for one item.

**Step 4 — Refinement**: Adjust tone, style, or structure.

**Why this works**: Claude focuses on one thing at a time. You course-correct at each step. Context builds naturally.

## Building Specialized Assistants

### Email Writer Project

> RULES: Every email must have a clear subject line, greeting, body (3 paragraphs max), CTA, professional signature. Match formality to recipient. Keep under 200 words.
>
> SHORTCUTS: "cold outreach" → Sales email. "follow-up" → Follow-up email. "proposal" → Proposal email. "update" → Status update.

### Meeting Analyzer Project

> WHEN I PASTE MEETING NOTES, ALWAYS:
> 1. Start with 3-sentence executive summary
> 2. List action items (what, who, deadline)
> 3. Identify key decisions made
> 4. Flag unresolved questions
> 5. Suggest follow-up actions

### Social Media Manager Project

> CAPABILITIES: Create posts for LinkedIn, Instagram, Twitter/X, TikTok. Repurpose one piece into 5 platform-specific posts. Suggest hashtags and posting times.
>
> TEMPLATES: Carousel = Hook → Problem → Solution → Steps → CTA. Reel = Hook (3s) → Value (20s) → CTA (5s). LinkedIn = Story → Lesson → Engagement question.

## Advanced Techniques

**Chain of Thought**: Ask Claude to "think through this step-by-step" for better reasoning.

**Role Reversal**: "Instead of writing it for me, interview me with the 10 most important questions." — Claude asks one at a time, building a complete brief.

**Perspective Analysis**: "Analyze my idea from three perspectives: an excited investor, a skeptical competitor, and a practical customer."

**Output Iteration**: Request version 1 (rough draft), version 2 (tightened), version 3 (final polish).

## Exercise: Build a Business Strategist

1. Create a Project called "Business Strategist"
2. Add custom instructions defining your business context
3. Include rules: start with "why" before "how", quantify when possible, end with "Recommended Next Steps"
4. Test with: "What should I focus on this week to grow revenue?"

\newpage

# Chapter 3: Build a Website

## Method 1: Claude Artifacts (Fastest)

### Step 1: Describe Your Website

> Create a professional landing page for a freelance AI consultant named [Your Name].
>
> SECTIONS: Hero with headline + CTA, Services (3 cards), How It Works (3 steps), Testimonials, About, Contact form, Footer.
>
> DESIGN: Modern, clean. Colors: Dark navy (#1a1a2e) + Electric blue (#4361ee) + White. Responsive. Dark mode support.

### Step 2: Iterate

> Make these changes: taller hero with gradient, hover effects on cards, pulse animation on CTA, sticky nav bar, more whitespace between sections.

### Step 3: Add Interactivity

> Add: smooth scrolling, mobile hamburger menu, form validation, back-to-top button, animated counters.

### Step 4: Deploy

**Option A**: Share the Artifact URL directly (simplest).

**Option B**: Copy the code and deploy for free:

- **GitHub Pages** — Push index.html to a repo, enable Pages
- **Netlify** — Drag and drop your HTML file
- **Vercel** — Connect your repo, auto-deploy

## Method 2: Claude Code (More Powerful)

For multi-page websites:

1. Install Claude Code: `npm install -g @anthropic-ai/claude-code`
2. Create a project folder and run `claude`
3. Describe your multi-page website with all details
4. Preview with `npx serve .`
5. Deploy to Netlify, Vercel, or GitHub Pages

## Method 3: Paperclip (Hosted)

Visit paperclip.ing, describe your website, and Claude-powered AI builds and hosts it for you.

## Website Prompts: Copy-Paste Ready

**Landing Page**: "Create a conversion-optimized landing page with hero, problem/solution, 3 pricing tiers, testimonials, FAQ, and CTA section."

**Portfolio**: "Build a minimalist portfolio with full-screen hero, scrolling project showcase, skills section, timeline, and contact form."

**Restaurant**: "Create a restaurant website with food photo hero, menu with prices, about, hours/location, reservation CTA, and Instagram feed."

**SaaS**: "Build a SaaS landing page with product screenshot, 6 features, how it works, pricing table, competitor comparison, testimonials, and FAQ."

## Design Iteration Tips

- Reference real websites: "I like the design style of stripe.com"
- Be specific: "Add 80px padding between sections"
- Check mobile: "Make sure touch targets are at least 44px"
- Add polish: "Subtle fade-in animations, loading states, smooth hover transitions"

## Exercise

Open claude.ai, describe a personal landing page (your name, title, tagline, 3 services, about section, contact), iterate 2-3 times, then share or deploy.

\newpage

# Chapter 4: Build an Application

## Claude Code: Your AI Developer

Claude Code is like having a senior developer. You describe what you want in plain language, and Claude writes, tests, and debugs the code.

**What Claude Code can build**: Web apps (dashboards, calculators, booking systems), tools (data processors, converters), APIs, automations, mobile-friendly PWAs.

**What you need to provide**: Clear description, user stories, specific features, data structure.

**What you do NOT need**: Coding knowledge, technical vocabulary, framework expertise.

## Build Your First App: Invoice Generator

### Step 1: Set Up

```
mkdir invoice-generator
cd invoice-generator
claude
```

### Step 2: Describe the App

> Build a client invoice generator web application.
>
> Features: Fill in business info, add client details, add line items, auto-calculate subtotal/tax/total, generate and download PDF, auto-numbering, tax rate selector, currency selector, save drafts locally, invoice history.
>
> Design: Clean, professional, mobile responsive, light/dark mode.

### Step 3: Review and Iterate

> Improvements: Better invoice template typography, "Duplicate Invoice" button, input validation for amounts, success animation on download, persistent business info.

### Step 4: Test

Open in browser with `npx serve .` and verify every feature.

## More App Ideas

**Habit Tracker**: Daily check-off with animations, streaks, statistics dashboard, CSV export.

**Time Tracker**: Projects with hourly rates, start/stop timer, reports, earnings calculator, PDF timesheet export.

**Recipe Manager**: Add recipes with ingredients and steps, categorize, adjust serving sizes, generate shopping lists.

**Client CRM**: Contacts, deal pipeline, Kanban board, activity log, follow-up reminders, dashboard.

**Content Calendar**: Monthly calendar with drag-and-drop, multi-platform posts, status tracking, content library.

## The Development Workflow

1. **Idea** — What problem does it solve?
2. **Describe** — Write a detailed prompt
3. **Build** — Claude Code creates the app
4. **Test** — Try every feature, find issues
5. **Refine** — Fix issues, add polish
6. **Deploy** — Put it online

**Key principles**: Start simple, test early, be specific, plan for 3-5 rounds of refinement.

## Deploying Your App

Free hosting options:

- **GitHub Pages** — Static sites. Push to GitHub, enable Pages.
- **Netlify** — Static sites with forms. Drag and drop or connect repo.
- **Vercel** — React/Next.js apps. Connect repo, auto-deploy.
- **Railway** — Apps with databases. Connect repo, add database.

## Debugging Tips

- **Describe the problem**: "The tax calculation shows $125 instead of $120 for $100 at 20%"
- **Share error messages**: Include the exact console error text
- **Expected vs. actual**: "Expected: new row appears. Actual: nothing happens when I click"

## Exercise

Build a personal dashboard with: task list (priorities), notes (markdown), Pomodoro timer, daily goals, quick links grid. All stored in localStorage. Deploy to Netlify.

\newpage

# Chapter 5: Automation

## What Is Automation?

Making things happen automatically without manual intervention.

**Manual**: Email arrives → You read it → You categorize → You reply → You update spreadsheet.

**Automated**: Email arrives → AI reads → Auto-categorized → Draft reply ready → Spreadsheet updated. All in seconds.

## The Automation Stack

- **n8n** — Visual workflow builder that connects apps and services (free self-hosted, or from $24/mo cloud)
- **Claude API** — The AI brain inside your workflows (pay per use)

## Getting Started with n8n

**Option 1 — n8n Cloud**: Sign up at n8n.io for a free trial.

**Option 2 — Self-Hosted**: Run with Docker.

**Option 3 — Claude Code + n8n MCP**: Describe workflows to Claude, and it builds them for you.

## Automation Recipes

### Recipe 1: Email Auto-Responder

Trigger: New email received → Claude classifies (URGENT/QUESTION/MEETING/NEWSLETTER/SPAM) → Route based on classification → Log to Google Sheets.

### Recipe 2: Social Media Content Pipeline

Trigger: Weekly schedule → Read topics from Google Sheets → Claude generates content for each platform → Split into individual posts → Schedule via Buffer/Hootsuite → Slack notification.

### Recipe 3: Lead Qualification

Trigger: Form submission → Claude scores lead 1-10 → Route by score (Hot = CRM + email alert, Warm = nurture sequence, Cold = newsletter) → Send personalized auto-response → Log to spreadsheet.

### Recipe 4: Meeting Notes Processor

Trigger: New recording uploaded → Transcribe audio → Claude extracts summary, decisions, action items → Create Google Doc → Create task cards in Asana/Trello → Email summary to attendees.

### Recipe 5: Customer Feedback Analyzer

Trigger: Daily at 6 AM → Fetch reviews from multiple sources → Claude analyzes sentiment, category, priority → Add to feedback database → Generate weekly executive summary → Email report.

## Connecting Claude to n8n

1. In n8n, add the Anthropic node or use HTTP Request
2. Get your API key from console.anthropic.com
3. Configure: model, max tokens, temperature (0 for consistent, 0.7 for creative)

**Prompt tips for automation**: Always request structured JSON output for easy processing.

> Analyze this ticket and return JSON:
> {"category": "billing|technical|feature_request", "priority": "high|medium|low", "sentiment": "positive|neutral|negative", "summary": "one sentence", "suggested_response": "draft under 100 words"}

## Exercise: Email-to-Summary Workflow

Build a 3-node workflow: Gmail Trigger → Claude (summarize email, extract deadlines and actions) → Google Sheets (log summary, deadline, action needed). Activate and test.

\newpage

# Chapter 6: AI Agents

## What Is an AI Agent?

An AI agent is Claude with superpowers. Regular Claude answers questions. An agent answers questions AND takes action — accesses databases, files, APIs, and runs multi-step processes autonomously.

## MCP: The Model Context Protocol

MCP is what gives Claude the ability to use external tools. Think of it as USB ports for AI — plug in tools and Claude can use them.

**Available MCP Servers**:

- **Filesystem** — Read/write files on your computer
- **GitHub** — Manage repos, issues, pull requests
- **Google Drive** — Access documents, spreadsheets
- **Slack** — Read/send messages
- **Database** — Query SQL databases
- **Browser** — Navigate and interact with websites
- **n8n** — Create and manage automation workflows
- **Memory** — Persistent memory across conversations

## Setting Up MCP

In Claude Code's configuration, add MCP servers with their commands and credentials. Once connected, Claude can use tools naturally:

> Read the sales report from my Documents folder, analyze Q2 numbers, and create a summary file.

Claude uses filesystem MCP to read → analyzes content → writes a new file.

## Types of AI Agents

**Task Agent**: Completes a specific task from start to finish. "Go through GitHub issues labeled 'bug', prioritize by severity, create a markdown report."

**Research Agent**: Gathers information from multiple sources. "Research our top 3 competitors — pricing, features, recent changes, complaints — and create a competitive analysis."

**Monitor Agent**: Watches for changes and acts on conditions. "Monitor our website hourly. If it goes down, send a Slack message and create a GitHub issue."

**Workflow Agent**: Orchestrates multi-step business processes. "When a new lead fills the form: score them, route based on score, send appropriate email, log everything."

## Agent Design Patterns

**Plan → Execute → Verify**: Claude outlines a plan, gets approval, executes, then reviews its own work.

**Human-in-the-Loop**: At major decision points, Claude pauses and asks before proceeding.

**Fallback Strategy**: If a step fails, try an alternative, document the issue, continue with remaining steps.

**Autonomous with Guardrails**: Full autonomy but with limits — never delete files, never send messages without drafting first, log every action.

## Exercise: Daily Briefing Agent

Build an agent that reads your priorities file and tasks file, then generates a daily briefing with today's priorities, pending tasks sorted by urgency, a motivational insight, and a suggested schedule. Save each briefing as a dated markdown file.

\newpage

# Chapter 7: Business

## The Opportunity

Businesses that want AI: ~85%. Businesses that have AI: ~12%. That gap is your opportunity.

## What You Can Offer

- **AI Strategy Consulting** ($500–$2,000/project) — Audit and recommend AI solutions
- **Prompt Engineering** ($200–$1,000/project) — Create custom prompts and instruction sets
- **Automation Setup** ($500–$3,000/project) — Build n8n workflows
- **Website Creation** ($500–$5,000/project) — Build sites with Claude
- **Content Systems** ($300–$1,500/project) — Set up AI content pipelines
- **AI Training** ($500–$2,000/session) — Teach teams to use Claude
- **AI Agent Development** ($1,000–$5,000/project) — Build custom agents

## Business Model 1: AI Freelancer

### Week 1-2: Foundation

1. **Define your offer** — Pick ONE service to start
2. **Build portfolio pieces** — Use Claude to create case studies and examples
3. **Create your website** — Use the skills from Chapter 3
4. **Set up outreach** — LinkedIn profile, outreach templates

### Client Acquisition Channels

- **LinkedIn** — Post AI tips daily, DM business owners (1-3 leads/week)
- **Local businesses** — Walk in or email with specific proposals (1-2 meetings/week)
- **Freelance platforms** — Upwork, Fiverr, Malt
- **Communities** — Skool, Facebook groups, Slack communities
- **Referrals** — Ask satisfied clients (highest conversion rate)

## Business Model 2: Productized Services

Create repeatable packages instead of custom work every time.

### Example: "AI Business Starter Pack" ($997)

Includes: AI audit + custom Claude Project setup + one automation workflow + 1-hour training session + 30-day support.

### Example: "Website in a Day" ($1,500)

Includes: 30-min discovery call + complete website (5-7 pages) + mobile responsive + SEO + contact form + deployment + training video.

### Example: "Monthly AI Retainer" ($500–$2,000/month)

Includes: X hours of AI work + ongoing automation maintenance + 1-2 new workflows per month + monthly report + priority support.

## Pricing Strategy: Value-Based

Don't charge for your time. Charge for the value you create.

**Example**: An employee spends 15 hours/week on manual data entry at $25/hour = $19,500/year. Your automation reduces it to 2 hours/week, saving $16,900/year. Charge 10-20% of annual savings = $1,690–$3,380 one-time. Client saves $13,500+ in year one. That's a 5.6x ROI.

Always offer 3 tiers. Most clients choose the middle one.

## Client Acquisition Playbook

**Week 1-2**: Define offer, build portfolio, create website, optimize LinkedIn, write templates.

**Week 3-4**: Post daily on LinkedIn, send 5 outreach messages/day, join 3 communities, offer free audits.

**Week 5-8**: Deliver exceptional work, document results, ask for referrals and testimonials, raise prices 20%.

**Month 3+**: Create productized packages, build referral system, consider hiring, develop case studies.

## Using Claude to Run Your Business

Claude isn't just your product — it's your operating system:

- **Proposals** — Generate custom proposals in minutes
- **Contracts** — Draft service agreements
- **Marketing** — Write all your content
- **Sales emails** — Personalized outreach at scale
- **Client reports** — Generate progress reports
- **Onboarding** — Create client onboarding guides

### Meta-Prompt for Business Operations

Create a Project called "My Business" with shortcuts:

- "proposal for [client]" → Full proposal
- "invoice [client] [amount]" → Invoice
- "outreach [business type]" → Outreach message
- "report for [client]" → Progress report
- "content for [platform]" → Social post

## Exercise

Use Claude to generate in one session: service description, three pricing packages, personal website, 5 outreach templates, proposal template, and client onboarding checklist.

\newpage

# Resources

## Official Claude Resources

- **Claude.ai** — claude.ai — Main interface
- **Claude Code Docs** — code.claude.com/docs — Documentation
- **Anthropic Console** — console.anthropic.com — API keys and usage
- **Prompt Engineering Guide** — claude.com/blog/best-practices-for-prompt-engineering

## Tools Used in This Guide

- **Claude.ai** — AI chat interface (Free / $20 Pro)
- **Claude Code** — CLI for building software (included with Pro)
- **n8n** — Visual workflow automation (n8n.io, free self-hosted)
- **Node.js** — JavaScript runtime (nodejs.org, free)
- **GitHub Pages** — Free website hosting (pages.github.com)
- **Netlify** — Free website hosting (netlify.com)
- **Vercel** — Free app hosting (vercel.com)
- **Paperclip** — AI website builder (paperclip.ing)

## Video Chapter Reference

- Intro — 0:00
- Les Fondations — 6:37
- Assistant IA — 24:16
- Site Web — 1:38:11
- Application — 2:40:56
- Automatisation — 3:53:22
- Agent IA — 4:54:03
- Business — 5:52:59

Watch the full training: youtube.com/watch?v=oS1RvuLPGbA

## Glossary

- **AI** — Computer systems performing tasks requiring human intelligence
- **API** — Application Programming Interface — how software communicates
- **Artifact** — Standalone content generated by Claude
- **Claude Code** — CLI tool for building software with Claude
- **Context Window** — Amount of text Claude can process (~200K tokens)
- **Custom Instructions** — Persistent rules in a Project
- **Knowledge Base** — Files uploaded to a Project for reference
- **LLM** — Large Language Model — the AI type powering Claude
- **MCP** — Model Context Protocol — connecting AI to external tools
- **n8n** — Open-source workflow automation tool
- **Project** — Organized workspace in Claude with persistent settings
- **Prompt** — Text input you give to Claude
- **Prompt Engineering** — Crafting effective AI prompts
- **Token** — Unit of text (~4 characters)

## Credits

- **Edited by**: Gabriel S. Sarr
- **Companion Video**: youtube.com/watch?v=oS1RvuLPGbA
- **Community**: skool.com/intelligenceartificielle (52,000+ members)

---

*This guide is open source. Share it, improve it, learn from it.*

*Remember: You don't need to know everything to start. You just need to start.*
