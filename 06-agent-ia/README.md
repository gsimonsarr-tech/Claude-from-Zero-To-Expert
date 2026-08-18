# Section 6: Use Case 5 — AI Agents

> Build autonomous AI agents that can use tools, access data, and complete complex tasks independently.

📺 **Video reference**: [4:54:03 – 5:52:59](https://www.youtube.com/watch?v=oS1RvuLPGbA&t=17643s)

---

## What Is an AI Agent?

An AI agent is Claude with superpowers. While regular Claude can only chat, an agent can:

| Regular Claude | AI Agent |
|---------------|----------|
| Answers questions | Answers questions + takes action |
| Works with text you provide | Accesses databases, files, APIs |
| Single conversation | Runs multi-step processes autonomously |
| Needs manual input | Can trigger itself on events |
| Limited to chat interface | Connected to real-world tools |

### Real-World Example

**Without agents:**
```
You: "What's the weather in Paris?"
Claude: "I don't have access to real-time data,
        but generally in August..."
```

**With agents (MCP tools connected):**
```
You: "What's the weather in Paris?"
Agent: [Calls weather API] → "It's currently 24°C
       and sunny in Paris. Rain expected tomorrow
       afternoon. Should I add an umbrella reminder
       to your calendar?"
```

---

## MCP: The Model Context Protocol

**MCP** (Model Context Protocol) is what gives Claude the ability to use external tools. Think of it as USB ports for AI — you plug in tools, and Claude can use them.

### How MCP Works

```
┌─────────────────────────────────────────┐
│              CLAUDE                      │
│                                          │
│   "I need to check the database"         │
│            │                             │
│            v                             │
│   ┌─────────────────┐                    │
│   │   MCP Protocol   │                   │
│   └────────┬────────┘                    │
│            │                             │
├────────────┼────────────────────────────┤
│            v                             │
│   ┌────────────────┐  ┌──────────────┐   │
│   │  Database MCP  │  │  Gmail MCP   │   │
│   │    Server       │  │   Server     │   │
│   └────────────────┘  └──────────────┘   │
│   ┌────────────────┐  ┌──────────────┐   │
│   │  Calendar MCP  │  │  Slack MCP   │   │
│   │    Server       │  │   Server     │   │
│   └────────────────┘  └──────────────┘   │
└─────────────────────────────────────────┘
```

### What MCP Servers Exist?

| MCP Server | What It Gives Claude |
|-----------|---------------------|
| **Filesystem** | Read/write files on your computer |
| **GitHub** | Manage repos, issues, pull requests |
| **Google Drive** | Access documents, spreadsheets |
| **Slack** | Read/send messages in channels |
| **Database** | Query SQL databases (PostgreSQL, SQLite) |
| **Browser** | Navigate and interact with websites |
| **n8n** | Create and manage automation workflows |
| **Memory** | Persistent memory across conversations |

And hundreds more at [MCP server registries](https://github.com/modelcontextprotocol/servers).

---

## Setting Up MCP with Claude Code

### Step 1: Configure MCP Servers

MCP servers are configured in Claude Code's settings. Here's how:

```bash
# Start Claude Code
claude

# Then in Claude Code, configure MCP:
```

In your Claude Code configuration (`.claude/settings.json`), add MCP servers:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@anthropic-ai/mcp-filesystem", "/path/to/your/folder"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@anthropic-ai/mcp-github"],
      "env": {
        "GITHUB_TOKEN": "your-github-token"
      }
    }
  }
}
```

### Step 2: Verify the Connection

```bash
# In Claude Code, ask:
"What MCP tools do you have access to?"

# Claude will list all connected tools
```

### Step 3: Use the Tools

Once connected, Claude can use tools naturally:

```
Read the sales report from my Documents folder,
analyze the Q2 numbers, and create a summary in a
new file called "Q2-analysis.md".
```

Claude will:
1. Use the filesystem MCP to read the file
2. Analyze the content
3. Write a new file with the analysis

---

## Types of AI Agents

### Type 1: Task Agent
Completes a specific task from start to finish.

```
Example prompt:
"Go through my GitHub issues labeled 'bug', prioritize
them by severity, and create a markdown report with
recommended fixes for the top 5."
```

### Type 2: Research Agent
Gathers information from multiple sources and synthesizes it.

```
Example prompt:
"Research our top 3 competitors. For each, find their:
pricing, main features, recent changes, and customer
complaints. Create a competitive analysis document."
```

### Type 3: Monitor Agent
Watches for changes and takes action when conditions are met.

```
Example (via n8n + Claude):
"Monitor our website every hour. If it goes down,
send me a Slack message and create a GitHub issue.
If response time exceeds 3 seconds, log a warning."
```

### Type 4: Workflow Agent
Orchestrates multi-step business processes.

```
Example:
"When a new lead fills out our contact form:
1. Score them based on company size and budget
2. If score > 7: send personal email + add to CRM
3. If score 4-7: add to email nurture sequence
4. If score < 4: add to newsletter only
5. Log everything to our analytics spreadsheet"
```

---

## Building an Agent: Step-by-Step

### Project: Personal Research Agent

Build an agent that can research topics and create reports.

#### Step 1: Set Up the Project

```bash
mkdir research-agent
cd research-agent
claude
```

#### Step 2: Describe the Agent

```
Build a research agent that I can ask to investigate
any topic. The agent should:

1. Break down the research question into sub-questions
2. Search for information (using available tools)
3. Organize findings into categories
4. Create a structured report with:
   - Executive summary
   - Key findings (with sources when available)
   - Different perspectives / counterarguments
   - Practical recommendations
   - Areas needing further research

The output should be a well-formatted markdown document
saved to the project folder.

When I say "research [topic]", the agent should begin
the full process automatically.
```

#### Step 3: Add Tool Connections

Connect relevant MCP servers so the agent can:
- Read/write files (filesystem MCP)
- Search the web (browser MCP or web search tools)
- Access your documents (Google Drive MCP)

#### Step 4: Test and Refine

```
Research the current state of AI automation for
small businesses. Focus on:
- Most common use cases
- ROI metrics
- Implementation challenges
- Top tools available
- Predictions for the next 12 months
```

---

## Agent Design Patterns

### Pattern 1: Plan → Execute → Verify

```
1. PLAN: "Before doing anything, outline your plan
   and confirm with me."
2. EXECUTE: "Now carry out the plan step by step."
3. VERIFY: "Review what you've done and check for
   errors or missed items."
```

### Pattern 2: Human-in-the-Loop

```
"At each major decision point, pause and ask me
before proceeding. Show me what you plan to do and
why, then wait for my approval."
```

### Pattern 3: Fallback Strategy

```
"If you encounter an error or can't complete a step:
1. Try an alternative approach
2. If that fails, document what went wrong
3. Continue with the remaining steps
4. Report all issues at the end"
```

### Pattern 3: Autonomous with Guardrails

```
"You have full autonomy to complete this task, but:
- Never delete files — only create or modify
- Never send messages to external services without drafting first
- If budget/cost decisions arise, stop and ask
- Log every action you take in agent-log.md"
```

---

## Claude Code as an Agent

Claude Code itself is an AI agent. Here's how to maximize it:

### Give Claude Code a Mission

```
You are my development partner for this project.
Your mission is to:

1. Understand the project structure and goals
2. Implement features I describe
3. Test your own code before confirming it works
4. Suggest improvements proactively
5. Keep documentation updated

For each task:
- Read relevant files first to understand context
- Make changes incrementally (small commits)
- Run tests after changes
- Explain what you changed and why
```

### Multi-Step Project with Claude Code

```
We're building a customer feedback dashboard.
Here's the full plan:

Phase 1: Set up the project structure
Phase 2: Build the data input form
Phase 3: Create the analysis engine (sentiment, categories)
Phase 4: Build the dashboard visualization
Phase 5: Add export functionality

Start with Phase 1. After each phase, show me the
result and wait for my feedback before continuing.
```

---

## Exercise: Build Your First Agent

### Task: Create a "Daily Briefing" Agent

1. Start Claude Code in a new project
2. Create an agent that:

```
Build me a "Daily Briefing" system.

Every time I run it, the agent should:
1. Read a file called "priorities.md" (my current priorities)
2. Check a "tasks.json" file for pending tasks
3. Generate a daily briefing that includes:
   - Today's date and day of the week
   - Top 3 priorities for today
   - Pending tasks sorted by urgency
   - A motivational insight related to my goals
   - Suggested schedule for the day

Save the briefing as "briefings/YYYY-MM-DD.md"
Create the briefings folder if it doesn't exist.

Also create a sample priorities.md and tasks.json
so I can test immediately.
```

3. Run the agent and review the output
4. Customize the briefing format to your preferences

---

## Key Takeaways

- **AI Agents** = Claude + tools + autonomy
- **MCP** (Model Context Protocol) connects Claude to external tools and data
- Start with **simple agents** (file-based) before connecting to APIs
- Use **human-in-the-loop** patterns when actions have consequences
- **Claude Code itself is an agent** — use it as your development partner
- Always include **guardrails** — limits on what the agent can do autonomously

---

## Next Step

Now that you have all the technical skills, it's time to turn them into a business. Head to **[Section 7: Business](../07-business/README.md)** to monetize your AI expertise.
