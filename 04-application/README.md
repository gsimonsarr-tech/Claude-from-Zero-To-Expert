# Section 4: Use Case 3 — Build an Application

> Build functional applications with Claude Code — even if you've never written a line of code.

📺 **Video reference**: [2:40:56 – 3:53:22](https://www.youtube.com/watch?v=oS1RvuLPGbA&t=9656s)

---

## What You'll Build

By the end of this section, you'll understand how to:
- Use Claude Code to create full applications
- Build tools that solve real problems
- Go from idea to working product in hours, not months

---

## Claude Code: Your AI Developer

Claude Code is like having a senior developer working with you. You describe what you want in plain language, and Claude writes, tests, and debugs the code.

### What Claude Code Can Build

| Type | Examples |
|------|---------|
| **Web Apps** | Dashboards, calculators, booking systems, CRMs |
| **Tools** | Data processors, file converters, scrapers |
| **APIs** | Backend services, integrations, webhooks |
| **Automations** | Scripts, scheduled tasks, batch processors |
| **Mobile-Friendly Apps** | Progressive Web Apps (PWAs) |

### What Claude Code Needs From You

1. **Clear description** of what the app should do
2. **User stories** — who uses it and how
3. **Specific features** — what buttons, screens, and interactions
4. **Data** — what information the app handles

You do NOT need:
- Coding knowledge
- Technical vocabulary
- Framework expertise

---

## Step-by-Step: Build Your First App

### Example Project: Client Invoice Generator

Let's build a real app: a tool that generates professional invoices.

#### Step 1: Set Up

```bash
# Create project folder
mkdir invoice-generator
cd invoice-generator

# Start Claude Code
claude
```

#### Step 2: Describe the Application

```
Build a client invoice generator web application.

WHAT IT DOES:
A single-page app where I can:
1. Fill in my business info (saved locally)
2. Add client details
3. Add line items (description, quantity, unit price)
4. Auto-calculate subtotal, tax, and total
5. Generate a professional PDF invoice
6. Download the PDF

FEATURES:
- Auto-numbering invoices (INV-001, INV-002, etc.)
- Tax rate selector (0%, 5%, 10%, 20%)
- Due date calculator (Net 15, Net 30, Net 60)
- Currency selector (USD, EUR, GBP)
- Notes/terms section
- My business logo upload
- Save draft functionality (localStorage)
- Invoice history list

DESIGN:
- Clean, professional interface
- Print-friendly invoice layout
- Mobile responsive
- Light/dark mode toggle

TECH:
- HTML, CSS, JavaScript (no frameworks needed)
- Use localStorage for data persistence
- Generate PDF client-side (jsPDF or similar)
```

#### Step 3: Review and Iterate

Claude Code will create the files. Review the app and refine:

```
Good! Make these improvements:
1. The invoice template needs more visual polish —
   add subtle grid lines and better typography
2. Add a "Duplicate Invoice" button to quickly create
   similar invoices
3. Add input validation — amount fields should only
   accept numbers
4. Add a success animation when the PDF downloads
5. Store business info so I don't re-enter it each time
```

#### Step 4: Test the App

```bash
# Preview in browser
npx serve .
```

Open the browser, create a test invoice, and verify everything works.

---

## App Ideas You Can Build Today

### Idea 1: Habit Tracker
```
Build a daily habit tracker app.

FEATURES:
- Add/remove habits with custom names and icons
- Daily check-off with satisfying animations
- Weekly and monthly streak views
- Statistics dashboard (completion rate, best streaks)
- Data stored locally in the browser
- Export data as CSV

DESIGN: Minimal, calming colors, gamification elements
(streak badges, progress rings)
```

### Idea 2: Project Time Tracker
```
Build a time tracking app for freelancers.

FEATURES:
- Create projects with client names and hourly rates
- Start/stop timer with one click
- Manual time entry
- Daily/weekly/monthly reports
- Calculate earnings per project
- Export timesheet as PDF
- Dashboard with charts (hours per project, earnings trends)

DESIGN: Professional, dashboard-style layout with
data visualization
```

### Idea 3: Recipe Manager
```
Build a personal recipe management app.

FEATURES:
- Add recipes with ingredients, steps, and photos
- Categorize (breakfast, lunch, dinner, dessert, snack)
- Search and filter recipes
- Serving size adjuster (auto-recalculate ingredients)
- Shopping list generator from selected recipes
- Meal planner (drag recipes to calendar days)
- Import from URL (paste a recipe link)

DESIGN: Warm, food-inspired colors, card-based layout,
large readable text for kitchen use
```

### Idea 4: Client CRM (Customer Relationship Manager)
```
Build a simple CRM for a freelancer or small business.

FEATURES:
- Add contacts with name, company, email, phone, notes
- Deal pipeline (Lead → Contacted → Proposal → Won/Lost)
- Drag-and-drop Kanban board for deals
- Activity log (calls, emails, meetings)
- Reminders for follow-ups
- Search and filter contacts
- Dashboard: total pipeline value, conversion rate, monthly revenue
- Export contacts as CSV

DESIGN: Clean, business-focused, inspired by Trello/Notion
```

### Idea 5: Content Calendar
```
Build a social media content calendar.

FEATURES:
- Monthly calendar view with drag-and-drop
- Add posts with: platform, content type, caption, hashtags, image placeholder
- Platforms: Instagram, LinkedIn, Twitter/X, TikTok
- Status: Draft, Ready, Scheduled, Published
- Content library (save reusable templates)
- Analytics placeholder (manually input engagement data)
- Weekly view and list view options
- Color-coded by platform

DESIGN: Modern, clean, calendar-first layout
```

---

## The App Development Workflow

```
  ┌──────────────┐
  │   1. IDEA    │ ── What problem does it solve?
  └──────┬───────┘
         v
  ┌──────────────┐
  │  2. DESCRIBE │ ── Write a detailed prompt
  └──────┬───────┘
         v
  ┌──────────────┐
  │  3. BUILD    │ ── Claude Code creates the app
  └──────┬───────┘
         v
  ┌──────────────┐
  │  4. TEST     │ ── Try every feature, find issues
  └──────┬───────┘
         v
  ┌──────────────┐
  │  5. REFINE   │ ── Fix issues, add polish
  └──────┬───────┘
         v
  ┌──────────────┐
  │  6. DEPLOY   │ ── Put it online for users
  └──────────────┘
```

### Key Principles

1. **Start simple** — Get the core feature working first, then add extras
2. **Test early** — Don't wait until everything is built to test
3. **Be specific** — "Add a button" is vague; "Add a blue 'Download PDF' button in the top-right corner" is clear
4. **Iterate** — Plan for 3-5 rounds of refinement
5. **Save your work** — Use git to track changes

---

## Deploying Your App

### Free Hosting Options

| Platform | Best For | Steps |
|----------|----------|-------|
| **GitHub Pages** | Static sites | Push to GitHub, enable Pages |
| **Netlify** | Static sites with forms | Drag & drop or connect repo |
| **Vercel** | React/Next.js apps | Connect repo, auto-deploy |
| **Railway** | Apps with databases | Connect repo, add database |
| **Render** | Full-stack apps | Connect repo, configure |

### Quick Deploy with Netlify

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy (from your project folder)
netlify deploy --prod --dir .
```

You'll get a live URL like `https://your-app.netlify.app`.

---

## Debugging with Claude Code

When something doesn't work:

### Technique 1: Describe the Problem
```
The tax calculation is wrong. When I enter a subtotal
of $100 with 20% tax, it shows $125 instead of $120.
Fix the tax calculation.
```

### Technique 2: Share Error Messages
```
I'm getting this error in the browser console:
"TypeError: Cannot read property 'value' of null"
when I click the "Generate PDF" button.
```

### Technique 3: Compare Expected vs. Actual
```
Expected: When I click "Add Item", a new row appears
in the invoice table with empty fields.

Actual: Nothing happens when I click the button.
The button doesn't seem to be connected to any action.
```

---

## Exercise: Build an App

### Task: Build a Personal Dashboard

1. Start Claude Code in a new project folder
2. Use this prompt:

```
Build a personal dashboard app with these widgets:

1. TASK LIST: Add, complete, delete tasks with priorities
   (High/Medium/Low)
2. NOTES: Quick note-taking area with markdown support
3. POMODORO TIMER: 25-min work / 5-min break cycle
   with start/pause/reset
4. DAILY GOALS: 3 goals for the day with checkboxes
5. QUICK LINKS: Customizable bookmarks grid

LAYOUT: Dashboard grid layout, drag to rearrange widgets
DATA: All stored in localStorage
DESIGN: Modern, dark mode by default, clean typography
```

3. Test it in your browser
4. Iterate to add features or fix issues
5. Deploy to Netlify or GitHub Pages

---

## Key Takeaways

- Claude Code builds complete applications from natural language descriptions
- **Be detailed** in your descriptions — the more specific, the better the result
- **Test everything** — check each feature works as expected
- **Iterate in rounds** — first get it working, then make it good, then make it great
- **Free deployment** options exist for every type of app
- You don't need coding skills — just clear communication

---

## Next Step

Ready to connect systems and automate workflows? Head to **[Section 5: Automation](../05-automatisation/README.md)** to learn n8n + Claude.
