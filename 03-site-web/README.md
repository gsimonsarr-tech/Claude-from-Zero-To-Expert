# Section 3: Use Case 2 — Build a Website

> Create and deploy a professional website using Claude — no coding knowledge needed.

📺 **Video reference**: [1:38:11 – 2:40:56](https://www.youtube.com/watch?v=oS1RvuLPGbA&t=5891s)

---

## What You'll Build

By the end of this section, you'll have:
- A professional landing page designed by Claude
- Understanding of how to iterate on web designs
- Knowledge of how to deploy your site to the real internet

---

## Method 1: Claude Artifacts (Fastest)

Artifacts let you build web pages directly inside Claude's interface. The result appears in a live preview panel.

### Step 1: Describe Your Website

```
Create a professional landing page for a freelance AI
consultant named [Your Name].

SECTIONS:
1. Hero: Bold headline "I Help Businesses Save 20 Hours/Week
   with AI" + subtitle + CTA button "Book a Free Call"
2. Services: 3 cards (AI Strategy, Automation Setup, Training)
3. How It Works: 3 steps (Discovery Call → Custom Plan → Implementation)
4. Testimonials: 3 client quotes (you can invent realistic ones)
5. About: Brief bio with professional photo placeholder
6. Contact: Simple contact form + email + LinkedIn link
7. Footer: Copyright + social links

DESIGN:
- Modern, clean, professional
- Color scheme: Dark navy (#1a1a2e) + Electric blue (#4361ee) + White
- Typography: Clean sans-serif
- Fully responsive (mobile + desktop)
- Smooth scroll animations
- Dark mode support
```

Claude will generate a complete HTML/CSS page and show it in the Artifacts panel.

### Step 2: Iterate on the Design

Once you see the preview, refine it:

```
Good start! Please make these changes:
1. Make the hero section taller with a gradient background
2. Add hover effects on the service cards (slight lift + shadow)
3. Make the CTA button pulse gently to draw attention
4. Add a sticky navigation bar that appears on scroll
5. Improve spacing — add more whitespace between sections
```

### Step 3: Add Interactivity

```
Add these interactive features:
1. Smooth scrolling when clicking nav links
2. A mobile hamburger menu
3. Form validation on the contact form
4. A "back to top" button that appears after scrolling down
5. Animated counters in a stats section
   (e.g., "50+ Clients", "1000+ Hours Saved", "98% Satisfaction")
```

### Step 4: Export and Deploy

**Option A — Share the Artifact URL** (simplest)
- Click the share button on the Artifact
- Anyone with a Claude account can view it

**Option B — Copy the code and deploy** (for a real website)
1. Click "View Code" on the Artifact
2. Copy the entire HTML
3. Deploy using one of these free options:

| Platform | Steps | Custom Domain |
|----------|-------|---------------|
| **GitHub Pages** | Paste code into index.html, push to repo | Yes (free) |
| **Netlify** | Drag & drop HTML file | Yes (free) |
| **Vercel** | Connect repo, auto-deploy | Yes (free) |
| **Paperclip** | Paste code, instant deploy | Subdomain |

---

## Method 2: Claude Code (More Powerful)

For multi-page websites or more complex projects, use Claude Code.

### What Is Claude Code?

Claude Code is a command-line tool that lets Claude read, write, and manage files on your computer. It can build complete projects from scratch.

### Step 1: Install Claude Code

```bash
# Install via npm (Node.js required)
npm install -g @anthropic-ai/claude-code

# Or use without installing
npx @anthropic-ai/claude-code
```

If you don't have Node.js:
1. Download from [nodejs.org](https://nodejs.org)
2. Install it (click Next through the installer)
3. Open your terminal and run the command above

### Step 2: Start a Project

```bash
# Create a project folder
mkdir my-website
cd my-website

# Launch Claude Code
claude
```

### Step 3: Describe Your Website

In the Claude Code terminal, describe what you want:

```
Build a complete portfolio website with the following:

PAGES:
1. Home — hero section, featured work, brief about
2. Services — detailed service descriptions with pricing
3. Portfolio — grid of project showcases with filters
4. Blog — simple blog layout with article cards
5. Contact — contact form + map placeholder + social links

TECH STACK:
- HTML, CSS, JavaScript only (no frameworks)
- Responsive design (mobile-first)
- Modern CSS (Grid, Flexbox, custom properties)
- Smooth page transitions

DESIGN SYSTEM:
- Primary: #2563eb (blue)
- Secondary: #1e293b (dark slate)
- Accent: #f59e0b (amber)
- Background: #f8fafc (light gray)
- Border radius: 12px
- Shadows: Subtle, layered

Create all files with proper structure. Include a
README with setup instructions.
```

Claude Code will create all the files in your project folder.

### Step 4: Preview Locally

```bash
# Simple way to preview (in the project folder)
npx serve .

# Or open index.html directly in your browser
```

### Step 5: Deploy

```bash
# Deploy to Netlify (free)
npx netlify-cli deploy --prod --dir .

# Or deploy to GitHub Pages
git init
git add .
git commit -m "Initial website"
gh repo create my-website --public --push
# Then enable GitHub Pages in repo settings
```

---

## Method 3: Hosted Website Builder (Paperclip)

The video mentions [Paperclip](https://paperclip.ing/) as an option for building websites with AI assistance and hosting them.

### Steps

1. Go to [paperclip.ing](https://paperclip.ing/)
2. Describe the website you want
3. Claude-powered AI builds it for you
4. Deploy with included hosting


---

## Website Design Prompts: Copy-Paste Ready

### Landing Page for a Service Business
```
Create a conversion-optimized landing page for a
[your service] business.

Include: hero with value proposition, problem/solution
section, 3 service tiers with pricing, social proof
(testimonials + logos), FAQ accordion, and a strong
CTA section with urgency.

Design: Modern, trustworthy, fast-loading.
Mobile-first responsive layout.
```

### Portfolio Website
```
Build a minimalist portfolio website for a [your profession].

Include: Full-screen hero with name and title,
scrolling project showcase with images and descriptions,
skills/tools section, timeline of experience, contact form.

Style: Clean, lots of whitespace, elegant typography,
subtle animations on scroll.
```

### Restaurant / Local Business
```
Create a website for a restaurant called "[Name]".

Include: Hero with food photo background, menu section
organized by categories (starters, mains, desserts,
drinks) with prices, about section with story, hours
and location with embedded map placeholder, reservation
CTA, Instagram feed placeholder, footer with all info.

Style: Warm, inviting, food-focused color palette.
```

### SaaS Product
```
Build a SaaS landing page for "[Product Name]" —
a tool that [what it does].

Include: Hero with product screenshot mockup, feature
grid (6 features with icons), how it works (3 steps),
pricing table (Free/Pro/Enterprise), comparison with
competitors table, testimonial carousel, FAQ, CTA.

Style: Tech-forward, clean, professional. Use a
blue/purple gradient theme.
```

---

## Design Iteration Tips

### Tip 1: Reference Real Websites
```
I like the design style of [stripe.com / linear.app / notion.so].
Apply that same aesthetic to my landing page.
```

### Tip 2: Fix Specific Issues
```
The spacing between sections feels too tight. Add 80px
padding top and bottom on each section. Also, the font
size hierarchy doesn't feel right — make headings larger
and body text slightly smaller.
```

### Tip 3: Mobile-First
```
Show me the mobile version. Make sure:
- Navigation collapses into a hamburger menu
- Images stack vertically
- Touch targets are at least 44px
- Text is readable without zooming
```

### Tip 4: Add Polish
```
Add these finishing touches:
- Subtle entrance animations (fade-in on scroll)
- Loading state for the form button
- Smooth hover transitions (0.3s ease)
- A favicon
- Meta tags for SEO and social sharing
```

---

## Exercise: Build Your Website

### Task: Create a personal landing page

1. Open [claude.ai](https://claude.ai)
2. Use this prompt (customize the bracketed parts):

```
Create a single-page personal website for me:

NAME: [Your name]
TITLE: [Your role — e.g., "AI Consultant & Automation Expert"]
TAGLINE: [Your value proposition — e.g., "I help businesses
save 20+ hours per week with intelligent automation"]

SECTIONS:
1. Hero with name, title, tagline, and CTA
2. Three services I offer (with icons)
3. About me (2-3 paragraphs)
4. Contact section with email link

STYLE: Modern, professional, clean
COLORS: [Pick your preference or say "suggest a palette"]
```

3. Iterate 2-3 times to refine
4. Share the Artifact link or deploy to GitHub Pages

---

## Key Takeaways

- **Artifacts** = fastest way to build a single-page website (minutes)
- **Claude Code** = best for multi-page or complex projects
- **Iteration is key** — your first version won't be perfect, and that's fine
- **Be specific** about design (colors, spacing, typography)
- **Free deployment** is available through GitHub Pages, Netlify, or Vercel

---

## Next Step

Ready to build something more complex? Head to **[Section 4: Build an Application](../04-application/README.md)** to create functional apps with Claude Code.
