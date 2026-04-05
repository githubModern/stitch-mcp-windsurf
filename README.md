# Google Stitch MCP for Windsurf

**🎨 Generate UI designs and get code — directly from Windsurf's Cascade AI.**

Uses the official [`@_davideast/stitch-mcp`](https://github.com/davideast/stitch-mcp) package by Google.

---

## 🌍 Language / اللغة

**English:** [README_EN.md](./README_EN.md)  
**العربية:** [README_AR.md](./README_AR.md)

---

## � Quick Start (2 Minutes)

### Step 1: Get Your API Key

Go to [stitch.withgoogle.com/settings](https://stitch.withgoogle.com/settings) and copy your API key.

### Step 2: Add Config to Windsurf

Open this file:
- **Windows:** `%USERPROFILE%\.codeium\windsurf\mcp_config.json`
- **Mac/Linux:** `~/.codeium/windsurf/mcp_config.json`

Add this inside the `"mcpServers"` object (or copy the full `mcp_config.json` from this repo):

```json
"stitch": {
  "command": "npx",
  "args": ["-y", "@_davideast/stitch-mcp", "proxy"],
  "env": {
    "STITCH_API_KEY": "<YOUR_STITCH_API_KEY>"
  }
}
```

### Step 3: Restart Windsurf

Close and reopen Windsurf. Stitch will appear as green in the **MCPs** panel.

### Step 4: Start Designing

Open Cascade and type:
```
Use Stitch to build a dark mode dashboard with charts and sidebar navigation.
```

---

## 📋 Prerequisites

- **Node.js 18+** — [Download](https://nodejs.org/)
- **Stitch API Key** — [Get from Stitch Settings](https://stitch.withgoogle.com/settings)
- **Windsurf IDE** — [Download](https://windsurf.com/)
- **A Stitch project** — Create one at [stitch.withgoogle.com](https://stitch.withgoogle.com)

---

## 🎨 What You Can Do

| Feature | Example Prompt |
|---------|---------------|
| Generate UI | *"Create a modern e-commerce homepage"* |
| Get screen code | *"Get the HTML/CSS code for this screen"* |
| Extract design DNA | *"Extract the design context from my dashboard"* |
| Build a site | *"Build an Astro site from my Stitch project"* |
| Browse designs | *"List all my Stitch projects and screens"* |

---

## 🛠️ Available MCP Tools

| Tool | Description |
|------|-------------|
| `generate_screen_from_text` | Create a screen from a text prompt |
| `get_screen_code` | Get HTML/CSS code for a screen |
| `get_screen_image` | Get screenshot of a screen |
| `list_projects` | List all your Stitch projects |
| `list_screens` | List screens in a project |
| `extract_design_context` | Extract colors, fonts, layout patterns |
| `build_site` | Generate an Astro site from screens |

---

## 🔐 Authentication Options

### Option A: API Key (Easiest)
Set `STITCH_API_KEY` in the MCP config — no gcloud needed.

### Option B: OAuth via gcloud
```bash
gcloud auth application-default login
gcloud config set project YOUR_PROJECT_ID
gcloud beta services mcp enable stitch.googleapis.com --project=YOUR_PROJECT_ID
```

Then use this config:
```json
"stitch": {
  "command": "npx",
  "args": ["-y", "@_davideast/stitch-mcp", "proxy"],
  "env": {
    "STITCH_USE_SYSTEM_GCLOUD": "1"
  }
}
```

---

## 🔧 Troubleshooting

| Problem | Fix |
|---------|-----|
| Stitch not appearing | Check config is at `~/.codeium/windsurf/mcp_config.json` |
| Connection errors | Run `npx @_davideast/stitch-mcp doctor --verbose` |
| Auth errors | Verify your API key at [stitch.withgoogle.com/settings](https://stitch.withgoogle.com/settings) |
| Tools not working | Restart Windsurf completely |
| Full reset | `npx @_davideast/stitch-mcp logout --force --clear-config` |

---

## 🔒 Security

**Never commit your real API keys.** The `mcp_config.json` in this repo uses `<YOUR_STITCH_API_KEY>` as a placeholder.

---

## 📚 Resources

- [Google Stitch](https://stitch.withgoogle.com)
- [stitch-mcp GitHub](https://github.com/davideast/stitch-mcp)
- [Stitch MCP Setup Docs](https://stitch.withgoogle.com/docs/mcp/setup)
- [Windsurf MCP Guide](https://docs.windsurf.com/windsurf/cascade/mcp)

---

## 📄 License

MIT
