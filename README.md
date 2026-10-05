# IPS Prototyping Agent

Build ProFinda-looking HTML prototypes from screenshots and ideas using OpenCode and the IPS design system. No coding required.

---

## What you get

Describe a screen or upload a screenshot → OpenCode builds a running prototype that looks exactly like the real ProFinda platform → you get a single HTML file to share.

---

## Setup (one time per machine)

### 1. Install OpenCode
Follow the instructions at [opencode.ai](https://opencode.ai).

### 2. Install the IPS skill

**Mac / Linux:**
```bash
mkdir -p ~/.config/opencode/skills/IPS
curl -o ~/.config/opencode/skills/IPS/SKILL.md \
  https://raw.githubusercontent.com/pedrorodrigopro/ProFindaComponents/main/IPS.md
```

**Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Force "$env:APPDATA\opencode\skills\IPS"
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/pedrorodrigopro/ProFindaComponents/main/IPS.md" `
  -OutFile "$env:APPDATA\opencode\skills\IPS\SKILL.md"
```

### 3. Get the IPS Design System path
Ask your team lead for the local path to the IPS Design System repo on your machine. You'll need it when you start your first prototype.

That's it.

---

## How to use it

### Start a prototype

1. Create an empty folder anywhere on your machine
2. Open a terminal in that folder and run `opencode`
3. Say what you want — for example:

> *"Build me a prototype of the Role screen. When I click a role in the Workflow table it should navigate here."*

> *"Here's a screenshot — build this as a prototype."*

> *"I want to show a new Shortlist review flow where managers can approve or reject candidates."*

OpenCode will ask for your IPS Design System path the first time, then build the prototype and tell you where to open it.

### Keep iterating

> *"Add a filter sidebar"*
> *"Change these cards to a table"*
> *"The Approve button should be primary"*

### Share it

> *"Export this so I can share it"*

You get `dist/index.html` — one file, email it or upload it anywhere.

---

## What screens are already built

The agent knows these ProFinda screens and can use them directly:

| Screen | What it includes |
|---|---|
| **Workflow** | Engagements and Roles tabs with sortable tables |
| **Role** | Overview, Matches, Shortlist (Approve/Reject), Vacancies, History |
| **Engagement** | Engagement detail |
| **Booking Engine** | Gantt and Grid views, Projects and Workforce panels |
| **Analytics** | Reports list + Create Report wizard |
| **Audit Planner** | Full audit layout |
| **Marketplace** | Home and Work Opportunities |
| **My Profile** | Three-column and single-column variants |
| **Profiles Directory** | Card view, Table view, Search states |
| **Admin** | Skills Frameworks, Manage Roles |

For anything not on this list — just describe it and the agent builds it using the correct IPS components.

---

## Questions?
Ask your team lead or the person who sent you this link.
