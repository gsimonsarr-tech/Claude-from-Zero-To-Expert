# Section 1: Foundations

> Master Claude's interface, Projects, Knowledge Base, and Custom Instructions — the building blocks for everything that follows.

📺 **Video reference**: [6:37 – 24:16](https://www.youtube.com/watch?v=oS1RvuLPGbA&t=397s)

---

## The Claude Interface

When you open [claude.ai](https://claude.ai), here's what you see:

```
┌─────────────────────────────────────────────────────┐
│  Sidebar          │           Main Chat Area        │
│                   │                                 │
│  ┌─────────────┐  │  ┌──────────────────────────┐   │
│  │ New Chat     │  │  │                          │   │
│  │ Projects     │  │  │     Conversation          │   │
│  │ Recents      │  │  │     appears here          │   │
│  │             │  │  │                          │   │
│  │             │  │  │                          │   │
│  └─────────────┘  │  └──────────────────────────┘   │
│                   │  ┌──────────────────────────┐   │
│                   │  │  Type your message...     │   │
│                   │  │  📎 Attach  🎤 Voice       │   │
│                   │  └──────────────────────────┘   │
└─────────────────────────────────────────────────────┘
```

### Key Interface Elements

| Element | What It Does |
|---------|-------------|
| **New Chat** | Start a fresh conversation |
| **Projects** | Organized workspaces with persistent settings |
| **Recents** | Your conversation history |
| **Attach (📎)** | Upload files, images, documents |
| **Model Selector** | Choose between Claude models (Sonnet, Opus, Haiku) |
| **Artifacts Panel** | Preview generated content (code, documents, apps) |

---

## Claude Models: Which One to Use?

Claude offers different models for different needs:

| Model | Speed | Quality | Best For |
|-------|-------|---------|----------|
| **Haiku 4.5** | Very fast | Good | Quick questions, simple tasks, high-volume work |
| **Sonnet** | Fast | Very good | Daily work, writing, analysis, most tasks |
| **Opus** | Slower | Excellent | Complex reasoning, coding, research, critical tasks |

**Rule of thumb**:
- Use **Sonnet** for 80% of your work (it's the best balance)
- Use **Opus** when quality matters more than speed
- Use **Haiku** when you need quick answers or are processing many items

---

## Projects: Your AI Workspace

Projects are the most powerful feature for getting consistent, high-quality results from Claude. Think of a Project as a dedicated workspace where Claude already knows your context.

### Why Projects Matter

Without Projects:
```
You: "Write a marketing email for my SaaS product"
Claude: "Sure! What's your product? Who's your audience?
        What tone? What's the goal?" (back and forth...)
```

With Projects:
```
You: "Write a marketing email for the summer campaign"
Claude: [Already knows your product, audience, tone, brand
         guidelines, and past campaigns] → Delivers immediately
```

### Step-by-Step: Create Your First Project

#### Step 1: Open Projects
- Click **"Projects"** in the sidebar
- Click **"Create Project"**
- Name it (e.g., "My Business Assistant")

#### Step 2: Add Custom Instructions
This is the **system prompt** — instructions Claude follows in every conversation within this project.

```
Example Custom Instructions:

You are my business assistant. Here's what you need to know:

ABOUT MY BUSINESS:
- Company: [Your Company Name]
- Industry: Digital marketing agency
- Target clients: Small businesses with 10-50 employees
- Services: Social media management, SEO, paid advertising

MY PREFERENCES:
- Communication style: Professional but friendly
- Response length: Concise, use bullet points
- Language: English
- Always include actionable next steps

RULES:
- Never invent statistics — say "I don't have that data" if unsure
- Always consider budget constraints for small businesses
- Suggest tools that have free tiers when possible
- Format deliverables so they're ready to use immediately
```

#### Step 3: Add Knowledge Base Files
Upload documents that Claude should reference:

- **Company documents**: brand guidelines, product descriptions, pricing
- **Templates**: email templates, proposal formats, report structures
- **Data**: customer personas, market research, competitor analysis
- **Examples**: past work you liked, reference materials

**Supported formats**: PDF, TXT, CSV, MD, images (PNG, JPG), and more.

#### Step 4: Start a Conversation
Click **"New Chat"** within the project. Claude now has:
- Your custom instructions (always active)
- Your knowledge base (referenced when relevant)
- A consistent context for every new conversation

---

## Custom Instructions: The Deep Dive

Custom instructions are the single most impactful thing you can set up. Here are proven templates:

### Template 1: Personal Assistant
```
ROLE: You are my personal productivity assistant.

CONTEXT:
- I am a [your role] at [your company]
- My main responsibilities: [list them]
- I work with: [tools you use daily]

BEHAVIOR:
- Be direct and concise — no fluff
- When I ask for a document, make it ready to send
- Proactively suggest improvements
- If a task is ambiguous, make reasonable assumptions
  and state them rather than asking me

OUTPUT FORMAT:
- Use headers and bullet points for readability
- Include "Action Items" at the end of analytical responses
- For emails: subject line + body, ready to copy-paste
```

### Template 2: Content Creator
```
ROLE: You are my content strategist and writer.

BRAND VOICE:
- Tone: [Professional / Casual / Witty / Authoritative]
- Audience: [Describe your target reader]
- Avoid: [Words or phrases to never use]
- Examples of voice I like: [Reference specific content]

CONTENT RULES:
- SEO: Include relevant keywords naturally
- Structure: Use short paragraphs (2-3 sentences max)
- CTA: Every piece should have a clear call to action
- Length: Blog posts = 800-1200 words, Social = under 280 chars

PLATFORMS:
- Blog: WordPress, long-form educational content
- LinkedIn: Professional insights, industry commentary
- Instagram: Visual-first, carousel-friendly tips
```

### Template 3: Research Analyst
```
ROLE: You are my research analyst.

METHODOLOGY:
- Always cite your reasoning
- Distinguish between facts and opinions
- Present multiple perspectives on controversial topics
- Use data and examples to support claims

OUTPUT STANDARDS:
- Executive summary at the top (3-4 sentences)
- Detailed analysis with headers
- Pros/cons in table format when comparing options
- Risk assessment when recommending actions
- Sources and limitations at the bottom

CONSTRAINTS:
- Clearly state when information might be outdated
- Never present speculation as fact
- Flag when additional primary research would be valuable
```

---

## Knowledge Base: Best Practices

### What to Upload

| Upload This | Why |
|------------|-----|
| Brand guidelines | Consistent voice and style |
| Product documentation | Accurate descriptions and features |
| Customer personas | Targeted content and advice |
| Past successful work | Examples for Claude to learn from |
| FAQ documents | Quick, accurate answers |
| Process documents | Step-by-step assistance |

### What NOT to Upload

| Avoid This | Why |
|-----------|-----|
| Sensitive credentials | Security risk |
| Constantly changing data | Will become outdated |
| Extremely large datasets | Better to summarize first |
| Redundant documents | Clutters context, reduces quality |

### Organization Tips

1. **Name files clearly**: `brand-guidelines-2026.pdf` not `doc1.pdf`
2. **Keep files current**: Remove outdated versions
3. **Summarize large documents**: Claude works better with concise context
4. **Group related content**: One project per major workflow

---

## Artifacts: Your Creation Panel

Artifacts are a side panel where Claude can generate standalone content:

### What Artifacts Can Create

| Type | Example |
|------|---------|
| **Documents** | Reports, proposals, guides |
| **Code** | HTML, CSS, JavaScript, Python |
| **Web pages** | Landing pages, dashboards, calculators |
| **Diagrams** | Flowcharts, org charts, mind maps |
| **SVG graphics** | Logos, icons, illustrations |
| **Interactive apps** | Tools, games, forms |

### How to Trigger Artifacts

Simply ask Claude to create something that works as a standalone piece:

```
Create a landing page for a coffee subscription service
called "Morning Ritual". Use warm earth tones.
```

Claude will generate the code AND show you a live preview in the Artifacts panel.

---

## Exercise: Set Up Your First Project

### Task: Create a "Personal Assistant" Project

1. Go to [claude.ai](https://claude.ai)
2. Click **Projects** → **Create Project**
3. Name it: **"My Personal Assistant"**
4. Add these custom instructions:

```
You are my personal AI assistant.

ABOUT ME:
- Name: [Your name]
- Role: [Your job/role]
- Goals: [What you're working toward]

PREFERENCES:
- Be concise and actionable
- Use bullet points and clear formatting
- Don't ask unnecessary clarifying questions
- Include next steps in every response

STYLE:
- Professional but warm
- No jargon unless I use it first
- Provide examples when explaining concepts
```

5. Upload 1-2 relevant documents (resume, company info, project brief)
6. Start a new chat and test with:

```
Based on what you know about me, suggest 3 ways
I could use AI to save at least 5 hours per week
in my current role.
```

---

## Key Takeaways

- **Projects** give Claude persistent context — use them for any recurring workflow
- **Custom Instructions** shape Claude's behavior — invest time writing them well
- **Knowledge Base** provides reference material — keep it organized and current
- **Artifacts** create standalone content — websites, documents, tools
- **Model selection** matters — Sonnet for daily work, Opus for critical tasks

---

## Next Step

Now that you've mastered the foundations, it's time to build your first real AI assistant. Head to **[Section 2: AI Assistant](../02-assistant-ia/README.md)**.
