# Section 5: Use Case 4 — Automation

> Automate repetitive workflows by connecting Claude with n8n — save hours of manual work every week.

📺 **Video reference**: [3:53:22 – 4:54:03](https://www.youtube.com/watch?v=oS1RvuLPGbA&t=14002s)

---

## What Is Automation?

Automation means making things happen automatically without your manual intervention. Instead of:

```
Manual: Email arrives → You read it → You categorize it → You reply → You update spreadsheet
```

Automated:
```
Email arrives → AI reads it → Auto-categorized → Draft reply ready → Spreadsheet updated
All in seconds. While you sleep.
```

---

## The Automation Stack

This section uses two main tools:

| Tool | What It Does | Cost |
|------|-------------|------|
| **n8n** | Visual workflow builder — connects apps and services | Free (self-hosted) or from $24/mo (cloud) |
| **Claude API** | AI brain inside your workflows | Pay per use (see [pricing](https://www.anthropic.com/pricing)) |

### How They Work Together

```
┌─────────┐     ┌─────────┐     ┌─────────┐     ┌─────────┐
│ TRIGGER │ ──> │  CLAUDE  │ ──> │ ACTION  │ ──> │ OUTPUT  │
│         │     │   (AI)   │     │         │     │         │
│ Email   │     │ Analyze  │     │ Reply   │     │ Done!   │
│ Form    │     │ Classify │     │ Store   │     │         │
│ Schedule│     │ Generate │     │ Send    │     │         │
│ Webhook │     │ Decide   │     │ Create  │     │         │
└─────────┘     └─────────┘     └─────────┘     └─────────┘
```

---

## Getting Started with n8n

### Option 1: n8n Cloud (Easiest)

1. Go to [n8n.io](https://n8n.io/)
2. Sign up for a free trial
3. You're ready — no setup needed

### Option 2: Self-Hosted (Free)

```bash
# Using Docker (recommended)
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  n8nio/n8n

# Open http://localhost:5678 in your browser
```

### Option 3: Claude Code + n8n MCP (Advanced)

Use Claude Code with the n8n MCP server to build workflows by describing them:

```bash
# Install the n8n MCP skill
# See: https://github.com/EtienneLescot/n8n-as-code
```

With MCP connected, you can tell Claude:
```
Create an n8n workflow that monitors my Gmail for
invoices, extracts the amounts and due dates, and
adds them to a Google Sheet.
```

Claude builds the entire workflow for you.

---

## The n8n Interface

```
┌─────────────────────────────────────────────────────┐
│                   n8n Workflow Editor                │
│                                                     │
│   ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐     │
│   │Trigger├───►│ Node ├───►│ Node ├───►│Output│     │
│   └──────┘    └──────┘    └──────┘    └──────┘     │
│                                                     │
│   Drag nodes from the sidebar, connect them with    │
│   lines, configure each node's settings.            │
│                                                     │
│   [+ Add Node]  [▶ Execute]  [💾 Save]  [⚡ Active] │
└─────────────────────────────────────────────────────┘
```

### Key Concepts

| Concept | Meaning |
|---------|---------|
| **Node** | A single action (send email, call API, transform data) |
| **Trigger** | What starts the workflow (new email, schedule, webhook) |
| **Connection** | The line linking one node to the next |
| **Workflow** | The complete chain of connected nodes |
| **Execution** | One run of the workflow from start to finish |

---

## Automation Recipes: Ready to Build

### Recipe 1: Email Auto-Responder

**What it does**: Reads incoming emails, classifies them, drafts appropriate responses.

```
WORKFLOW:

1. TRIGGER: Gmail — New Email Received
2. FILTER: Skip if from known spam domains
3. CLAUDE: Analyze the email
   Prompt: "Classify this email as: URGENT, QUESTION,
   MEETING_REQUEST, NEWSLETTER, or SPAM.
   Then draft an appropriate response.
   Email content: {{$json.body}}"
4. SWITCH: Route based on classification
   - URGENT → Send response immediately + Slack notification
   - QUESTION → Create draft response for review
   - MEETING_REQUEST → Check calendar + suggest times
   - NEWSLETTER → Archive
   - SPAM → Delete
5. GOOGLE SHEETS: Log all emails with classification
```

### Recipe 2: Social Media Content Pipeline

**What it does**: Takes a topic, generates content for 4 platforms, schedules posts.

```
WORKFLOW:

1. TRIGGER: Monday at 9 AM (weekly schedule)
2. GOOGLE SHEETS: Read this week's content topics
3. CLAUDE: Generate content for each topic
   Prompt: "For the topic '{{$json.topic}}', create:
   1. LinkedIn post (150 words, professional tone)
   2. Twitter/X post (under 280 chars, with hook)
   3. Instagram caption (with 15 hashtags)
   4. TikTok script (30-second video outline)
   Format as JSON."
4. SPLIT: Separate into individual posts
5. BUFFER/HOOTSUITE: Schedule each post
6. SLACK: Notify "Content for this week is scheduled ✓"
```

### Recipe 3: Lead Qualification

**What it does**: When someone fills a form on your website, AI qualifies them and routes accordingly.

```
WORKFLOW:

1. TRIGGER: Webhook — Form submission from website
2. CLAUDE: Qualify the lead
   Prompt: "Based on this form submission, score this lead 1-10:
   Name: {{$json.name}}
   Company: {{$json.company}}
   Budget: {{$json.budget}}
   Timeline: {{$json.timeline}}
   Need: {{$json.message}}

   Score based on: budget fit, timeline urgency, company size.
   Return: score, reasoning, and recommended next action."
3. SWITCH: Route by score
   - Score 8-10 (Hot): Send to CRM as Priority + Email alert
   - Score 5-7 (Warm): Add to nurture sequence
   - Score 1-4 (Cold): Add to newsletter list
4. EMAIL: Send personalized auto-response based on score
5. GOOGLE SHEETS: Log lead with score and classification
```

### Recipe 4: Meeting Notes Processor

**What it does**: After a meeting, processes the recording/notes and distributes action items.

```
WORKFLOW:

1. TRIGGER: New file in Google Drive (meeting recordings folder)
2. TRANSCRIPTION: Convert audio to text
3. CLAUDE: Process the transcript
   Prompt: "From this meeting transcript, extract:
   1. Executive summary (3 sentences)
   2. Key decisions made
   3. Action items (who, what, deadline)
   4. Open questions to resolve
   5. Next meeting agenda suggestions

   Transcript: {{$json.text}}"
4. GOOGLE DOCS: Create meeting summary document
5. ASANA/TRELLO: Create task cards for each action item
6. EMAIL: Send summary to all attendees
7. SLACK: Post summary in #team-meetings channel
```

### Recipe 5: Customer Feedback Analyzer

**What it does**: Collects reviews from multiple sources, analyzes sentiment, and generates reports.

```
WORKFLOW:

1. TRIGGER: Daily at 6 AM
2. PARALLEL:
   - Google Reviews API: Fetch new reviews
   - Trustpilot API: Fetch new reviews
   - Support tickets: Fetch resolved tickets
3. MERGE: Combine all feedback
4. CLAUDE: Analyze each piece of feedback
   Prompt: "Analyze this customer feedback:
   '{{$json.text}}'

   Return JSON:
   - sentiment: positive/neutral/negative
   - category: product/service/support/pricing/other
   - key_issue: one sentence summary
   - priority: high/medium/low
   - suggested_action: what we should do"
5. GOOGLE SHEETS: Add to feedback database
6. CLAUDE: Generate weekly summary
   Prompt: "From these {{$json.count}} reviews this week,
   create an executive summary with trends, top issues,
   and recommendations."
7. EMAIL: Send weekly report to team
```

---

## Connecting Claude to n8n

### Setting Up the Claude (Anthropic) Node

1. In n8n, search for the **"Anthropic"** or **"HTTP Request"** node
2. Add your Anthropic API key:
   - Go to [console.anthropic.com](https://console.anthropic.com)
   - Create an API key
   - In n8n: Settings → Credentials → Add "Anthropic API"
3. Configure the node:
   - **Model**: `claude-sonnet-4-20250514` (balanced) or `claude-opus-4-20250514` (quality)
   - **Max tokens**: 1024–4096 depending on task
   - **Temperature**: 0 for consistent results, 0.7 for creative tasks

### Prompt Engineering for Automation

When Claude runs inside a workflow, your prompts should be:

1. **Structured** — Always use a clear format
2. **Specific** — Tell Claude exactly what to return
3. **JSON-friendly** — Request structured output for easy processing

```
Example automation prompt:

Analyze the following customer support ticket and return
a JSON object with these exact fields:
{
  "category": "billing|technical|feature_request|complaint|other",
  "priority": "high|medium|low",
  "sentiment": "positive|neutral|negative",
  "summary": "one sentence summary",
  "suggested_response": "draft response under 100 words",
  "escalate": true/false
}

Ticket:
{{$json.ticket_content}}
```

---

## Building Your First Workflow

### Exercise: Email-to-Summary Workflow

**Goal**: Automatically summarize long emails and save key points.

1. Open n8n
2. Add these nodes:

```
[Gmail Trigger] → [Claude/Anthropic] → [Google Sheets]
```

3. Configure Gmail Trigger:
   - Event: "Message Received"
   - Label: "To Process" (create this label in Gmail)

4. Configure Claude node:
```
Prompt:
Summarize this email in 2-3 sentences. Extract:
- Main ask or information
- Any deadlines mentioned
- Required action from me (if any)

Email:
Subject: {{$json.subject}}
From: {{$json.from}}
Body: {{$json.body}}

Return as:
Summary: ...
Deadline: ... (or "none")
Action needed: ... (or "none")
```

5. Configure Google Sheets:
   - Spreadsheet: "Email Summaries"
   - Columns: Date, From, Subject, Summary, Deadline, Action

6. Activate the workflow

---

## Key Takeaways

- **n8n** is a visual workflow builder — connect apps without code
- **Claude API** adds intelligence to your automations
- Start with **simple workflows** (2-3 nodes) and build up
- Use **structured prompts** with JSON output for reliable automation
- **n8n MCP** lets Claude Code build entire workflows from descriptions
- Automations run 24/7 — set them up once, benefit forever

---

## Next Step

Ready for the most advanced topic? Head to **[Section 6: AI Agents](../06-agent-ia/README.md)** to build autonomous agents that can use tools and make decisions.
