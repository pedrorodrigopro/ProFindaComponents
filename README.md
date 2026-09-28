# ProFinda Components — Prototype Agent

Turn any idea into a ProFinda-looking prototype in minutes. No coding required.

## Setup (one-time, 2 minutes)

Add this to your `~/.config/opencode/opencode.json` under the root level:

```json
{
  "instructions": [
    "https://raw.githubusercontent.com/pedrorodrigopro/ProFindaComponents/main/ProFindaComponents.md"
  ]
}
```

If you already have an `opencode.json`, just add the `"instructions"` key alongside your existing config.

That's it. Every OpenCode session you open from now on automatically knows how to build ProFinda-looking prototypes.

## How to use

1. Open OpenCode in **any empty folder** on your machine
2. Upload a screenshot of a ProFinda screen you want to replicate — or just describe your idea
3. OpenCode builds and runs the prototype for you at `http://localhost:5173`
4. Keep chatting to make changes: "add a filter here", "change this to a table", "add a new card"

## What you get

- A running app that looks exactly like the real ProFinda platform
- Same font, same colours, same components
- Export with `npm run build` to get a shareable file

## Requirements

- [OpenCode](https://opencode.ai) installed
- The `communities-storybook` MCP in your OpenCode config (ask your team lead)
