# Section 2: Use Case 1 — AI Assistant

> Master prompt engineering and build custom AI assistants that save you hours every day.

📺 **Video reference**: [24:16 – 1:38:11](https://www.youtube.com/watch?v=oS1RvuLPGbA&t=1456s)

---

## From Prompts to Results

The difference between a beginner and an expert Claude user comes down to one skill: **how you communicate with the AI**. This section teaches you the proven frameworks.

---

## The Prompt Engineering Framework

### The RICE Method

Every great prompt has four elements:

| Letter | Element | What It Means |
|--------|---------|---------------|
| **R** | Role | Who should Claude be? |
| **I** | Instructions | What exactly should Claude do? |
| **C** | Context | What background information is needed? |
| **E** | Examples | What does good output look like? |

### Example: Bad vs. Good Prompt

**Bad prompt:**
```
Write me a LinkedIn post
```

**Good prompt (RICE method):**
```
ROLE: You are a LinkedIn content strategist who specializes
in B2B tech companies.

INSTRUCTIONS: Write a LinkedIn post announcing our new
AI-powered customer service tool. The post should:
- Hook the reader in the first line
- Include a personal anecdote about customer service frustrations
- Present 3 key benefits with specific metrics
- End with a clear call to action
- Be 150-200 words

CONTEXT: Our company (TechFlow) just launched "ServiceAI",
an AI tool that reduces customer response time by 73%.
Our audience is CTOs and customer service managers at
companies with 50-500 employees.

EXAMPLE OF TONE I LIKE:
"Last week, I watched a customer wait 47 minutes for a
simple password reset. That's when I knew something had
to change..."
```

---

## Structured Prompting with XML Tags

Claude responds exceptionally well to structured prompts using XML-style tags. This technique is used by advanced practitioners:

### Basic Structure

```xml
<role>
You are a senior marketing strategist with 15 years of
experience in e-commerce growth.
</role>

<task>
Create a 90-day marketing plan for launching a new
organic skincare brand online.
</task>

<constraints>
- Budget: $5,000 total for 90 days
- Channels: Instagram, TikTok, Email only
- No paid ads in the first 30 days (organic growth first)
- Target audience: Women 25-40, health-conscious, urban
</constraints>

<output_format>
Organize by month (Month 1, 2, 3), with:
- Weekly action items
- Expected metrics/KPIs
- Tools needed (prefer free/low-cost)
- Budget allocation
Present in a clear table format.
</output_format>
```

### Why XML Tags Work

Claude's training makes it particularly responsive to structured markup:
- **Clear boundaries** — Claude knows exactly where each instruction starts and ends
- **No ambiguity** — Role, task, constraints, and format are clearly separated
- **Reusable** — Change one section without rewriting the whole prompt
- **Scalable** — Add more sections as needed

---

## The Mega-Prompt Technique

A mega-prompt is a comprehensive, highly detailed prompt that produces professional-quality output in a single shot. Think of it as a complete creative brief.

### Mega-Prompt Template

```
# IDENTITY
You are [specific role with years of experience and specialization].

# MISSION
[One clear sentence about what you need to accomplish]

# CONTEXT
- Industry: [your industry]
- Company stage: [startup/growth/enterprise]
- Target audience: [detailed description]
- Current situation: [relevant background]
- Goal: [what success looks like]

# DETAILED INSTRUCTIONS
1. [First major task with specifics]
2. [Second major task with specifics]
3. [Third major task with specifics]

# CONSTRAINTS
- Must: [non-negotiable requirements]
- Must not: [things to avoid]
- Tone: [communication style]
- Length: [word/page count]

# OUTPUT FORMAT
[Exactly how you want the result structured]
- Headers, sections, formatting
- Tables vs. paragraphs vs. bullet points
- Any specific templates to follow

# QUALITY CRITERIA
- [How to measure if the output is good]
- [Specific standards to meet]

# EXAMPLES (optional)
[Good output example]
[Bad output example — what to avoid]
```

### Real-World Mega-Prompt Example

```
# IDENTITY
You are a business strategist specializing in helping solopreneurs
launch AI-powered service businesses. You've helped 200+ clients
go from idea to first paying customer.

# MISSION
Create a complete business launch plan for an AI consulting
service targeting small local businesses.

# CONTEXT
- I have strong AI skills but no business experience
- Budget: $500 to start
- Time: Can dedicate 20 hours/week alongside my day job
- Location: Medium-sized city, lots of small businesses
- Strengths: Prompt engineering, automation, content creation
- Weakness: Sales, networking, pricing

# DETAILED INSTRUCTIONS
1. Define the service offering (what exactly I sell)
2. Create a pricing strategy (packages, not hourly)
3. Build a client acquisition plan (first 5 clients)
4. Design a simple service delivery process
5. List tools and setup I need (keep costs minimal)

# CONSTRAINTS
- No paid advertising — organic outreach only
- Must be operational within 2 weeks
- Deliverables should be templateable (repeatable for each client)
- Include exact scripts for cold outreach

# OUTPUT FORMAT
Organize as a 14-day action plan:
- Day-by-day tasks with time estimates
- Templates ready to use (outreach messages, proposals)
- Pricing table with 3 tiers
- One-page service description I can share with prospects

# QUALITY CRITERIA
- Every task must be specific and actionable (no vague advice)
- Include real examples, not generic placeholders
- Must work for someone with zero sales experience
```

---

## Multi-Turn Conversations: The Chain Technique

For complex tasks, break the work into steps across multiple messages:

### Step 1: Set Context
```
I'm building a content strategy for my fitness coaching business.
Before we create anything, I need you to understand my brand.

Here's my brand document: [paste or upload]

Confirm you understand my brand voice, target audience,
and key differentiators.
```

### Step 2: Strategy
```
Now create a content calendar for the next 4 weeks.
I post 5x/week on Instagram and 2x/week on LinkedIn.

For each post, include:
- Platform
- Content type (carousel, reel, story, text)
- Topic/hook
- Key message
- Call to action
```

### Step 3: Execution
```
Now write the full content for Week 1, Day 1 — the
Instagram carousel. Include:
- Slide-by-slide text (8 slides)
- Caption with hashtags
- Alt text for accessibility
```

### Step 4: Refinement
```
Good, but adjust the tone — it's too formal for Instagram.
Make it more conversational, like I'm talking to a friend
at the gym. Keep the same structure.
```

### Why This Works Better Than One Prompt

- Claude can focus on one thing at a time
- You can course-correct at each step
- The context builds naturally
- Each step's output informs the next

---

## Building Specialized Assistants

### Assistant 1: Email Writer

**Project setup:**
```
ROLE: You are my email communication specialist.

RULES:
- Every email must have: clear subject line, greeting,
  body (3 paragraphs max), CTA, professional signature
- Match the formality level to the recipient
- Never use "I hope this email finds you well"
- Keep emails under 200 words unless I specify otherwise

WHEN I SAY:        YOU DO:
"cold outreach"     → Sales prospecting email
"follow-up"         → Follow-up to previous conversation
"proposal"          → Formal business proposal email
"update"            → Project status update to client
"internal"          → Team communication
```

### Assistant 2: Meeting Analyzer

**Project setup:**
```
ROLE: You are my meeting analyst.

WHEN I PASTE MEETING NOTES OR TRANSCRIPTS, ALWAYS:
1. Start with a 3-sentence executive summary
2. List all action items with:
   - What needs to be done
   - Who is responsible
   - Deadline (if mentioned)
3. Identify key decisions made
4. Flag any unresolved questions or risks
5. Suggest follow-up actions

FORMAT: Use clear headers, bullet points, and bold text
for names and deadlines.
```

### Assistant 3: Social Media Manager

**Project setup:**
```
ROLE: You are my social media content manager.

BRAND: [Upload brand guidelines]
VOICE: Friendly, expert, slightly humorous
AUDIENCE: Entrepreneurs aged 25-45

CAPABILITIES:
- Create posts for: LinkedIn, Instagram, Twitter/X, TikTok scripts
- Repurpose: Turn one piece of content into 5 platform-specific posts
- Hashtag strategy: Research and suggest relevant hashtags
- Scheduling: Suggest optimal posting times

TEMPLATES I USE:
- Carousel: Hook → Problem → Solution → Steps → CTA
- Reel/TikTok: Hook (3s) → Value (20s) → CTA (5s)
- LinkedIn: Story → Lesson → Question for engagement
```

---

## Advanced Techniques

### Technique 1: Chain of Thought
Ask Claude to think step by step:
```
I need to decide whether to hire a full-time employee
or use contractors for my design work.

Think through this step-by-step:
1. List the costs of each option
2. Compare flexibility vs. consistency
3. Consider my situation: 15-20 hours of design work
   per month, variable workload
4. Give me your recommendation with reasoning
```

### Technique 2: Role Reversal
Make Claude interview you:
```
I want to create a business plan for an AI agency.
Instead of writing it for me, interview me with the
10 most important questions you'd need answered to
write a great business plan. Ask one question at a time.
```

### Technique 3: Perspective Analysis
Get multiple viewpoints:
```
Analyze my startup idea from three perspectives:
1. An excited investor who sees the potential
2. A skeptical competitor who knows the market
3. A practical customer who would use the product

My idea: [describe it]
```

### Technique 4: Output Iteration
Progressively refine:
```
Write version 1: A rough draft focusing on getting all
the key points down.

[After receiving v1]

Write version 2: Tighten the language, improve flow,
make it more persuasive. Keep the structure.

[After receiving v2]

Write version 3: Final polish. Every sentence must earn
its place. Cut anything that doesn't add value.
```

---

## Exercise: Build Your First Custom Assistant

### Task: Create a "Business Strategist" Assistant

1. Create a new Project called **"Business Strategist"**
2. Add these custom instructions:

```
You are my business strategy advisor. You combine
analytical thinking with practical, actionable advice.

ABOUT MY BUSINESS:
[Fill in your details — even if hypothetical]

YOUR APPROACH:
- Start with the strategic "why" before the tactical "how"
- Use frameworks (SWOT, Porter's 5 Forces, etc.) when relevant
- Always quantify when possible (time, money, percentages)
- End every analysis with "Recommended Next Steps"

CONSTRAINTS:
- Assume I'm a solopreneur with limited budget
- Prefer strategies that can be executed in under a week
- Focus on revenue-generating activities first
```

3. Test it with these prompts:
   - "What should I focus on this week to grow my revenue?"
   - "A competitor just launched a similar product at half my price. What should I do?"
   - "I have $1,000 to invest in marketing. Where does it go?"

---

## Key Takeaways

- Use the **RICE method** (Role, Instructions, Context, Examples) for every important prompt
- **XML tags** make complex prompts clearer and more effective
- **Mega-prompts** produce professional results in a single shot
- **Multi-turn conversations** work better for complex, evolving tasks
- **Specialized Projects** turn Claude into domain-specific assistants
- The time you invest in prompt quality pays back exponentially

---

## Next Step

Ready to build something visual? Head to **[Section 3: Build a Website](../03-site-web/README.md)** to create your first website with Claude — no coding required.
