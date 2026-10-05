# ProFinda Prototype Agent

Turn ideas and screenshots into working ProFinda-looking prototypes using OpenCode and the IPS design system. No coding required.

---

## What this is

An **agent** — a set of instructions you load into OpenCode once. After that, you describe a screen or upload a screenshot, and the AI builds a running prototype that looks exactly like the real ProFinda platform.

The output is a single HTML file you can open in any browser or email to anyone.

---

## One-time setup (per machine)

### 1. Install OpenCode

Follow the instructions at [opencode.ai](https://opencode.ai).

### 2. Install the ProFinda prototyping skill

Copy the skill file to your OpenCode skills folder:

**Mac / Linux:**
```bash
mkdir -p ~/.config/opencode/skills/profinda-prototyping
curl -o ~/.config/opencode/skills/profinda-prototyping/SKILL.md \
  https://raw.githubusercontent.com/pedrorodrigopro/ProFindaComponents/main/skills/profinda-prototyping/SKILL.md
```

**Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Force "$env:APPDATA\opencode\skills\profinda-prototyping"
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/pedrorodrigopro/ProFindaComponents/main/skills/profinda-prototyping/SKILL.md" `
  -OutFile "$env:APPDATA\opencode\skills\profinda-prototyping\SKILL.md"
```

### 3. Add these instructions to your OpenCode config

Open (or create) `~/.config/opencode/opencode.json` and add the instructions URL:

```json
{
  "instructions": [
    "https://raw.githubusercontent.com/pedrorodrigopro/ProFindaComponents/main/ProFindaComponents.md"
  ]
}
```

If you already have an `opencode.json`, add the URL to the existing `instructions` array.

### 4. Ask your team lead for the IPS Design System path

The prototyping agent needs access to the IPS Design System on your machine (for components and styles). Ask your team lead — they'll give you the local path to add to your prototype's `package.json`.

---

## How to use it

### Starting a prototype

1. Create an empty folder anywhere on your machine
2. Open a terminal in that folder and run `opencode`
3. Say what you want:

> *"Build me a prototype of the Role screen — Overview tab. When I click a role in Workflow it should navigate here."*

Or upload a screenshot and say:

> *"Build this screen as a prototype."*

The agent will ask clarifying questions if needed, then build the prototype and tell you how to open it.

### Iterating

Keep the conversation going:

> *"Add a filter sidebar on the left"*
> *"Change the cards to a table view"*
> *"The Shortlist tab should have Approve and Reject buttons"*

### Sharing the prototype

Ask:

> *"Export this so I can share it"*

The agent runs a build and produces `dist/index.html` — a single file you can email or upload anywhere.

---

## What screens are available

The agent knows these ProFinda screens and can build them immediately:

| Screen | What it includes |
|---|---|
| **Workflow** | Engagements and Roles tabs with sortable tables |
| **Role** | Overview, Matches, Shortlist (with Approve/Reject), Vacancies, History |
| **Engagement** | Engagement detail view |
| **Booking Engine** | Gantt and Grid views, Projects and Workforce panels |
| **Analytics** | Reports list + Create Report flow |
| **Audit Planner** | Full audit planner layout |
| **Marketplace** | Home and Work Opportunities |
| **My Profile** | Three-column and single-column variants |
| **Profiles Directory** | Card view, Table view, Search states |
| **Admin** | Skills Frameworks, Manage Roles |

For anything not on this list, describe it and the agent will build it using the correct IPS components.

---

## Questions?

Ask your team lead or the person who gave you this link.
