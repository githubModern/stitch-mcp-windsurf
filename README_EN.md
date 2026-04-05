# Google Stitch MCP for Windsurf (English)

**🎨 Generate UI designs and get code — directly from Windsurf's Cascade AI.**

Uses the official [`@_davideast/stitch-mcp`](https://github.com/davideast/stitch-mcp) package by Google.

---

## 📖 What This Does

[Google Stitch](https://stitch.withgoogle.com) is an AI tool powered by Gemini 2.5 Pro. It generates UI designs + HTML/CSS from text prompts.

This repo helps you connect Stitch to **Windsurf IDE** via MCP (Model Context Protocol), so you can generate designs and grab code without leaving your editor.

---

## 🚀 Setup (2 Minutes)

### Step 1: Get Your API Key

1. Go to [stitch.withgoogle.com](https://stitch.withgoogle.com) and sign in
2. Go to [Settings](https://stitch.withgoogle.com/settings) and copy your **API key**
3. Create at least one project in Stitch

### Step 2: Add to Windsurf

Open the Windsurf MCP config file:

- **Windows:** `%USERPROFILE%\.codeium\windsurf\mcp_config.json`
- **Mac/Linux:** `~/.codeium/windsurf/mcp_config.json`

Add this inside the `"mcpServers"` block:

```json
"stitch": {
  "command": "npx",
  "args": ["-y", "@_davideast/stitch-mcp", "proxy"],
  "env": {
    "STITCH_API_KEY": "<YOUR_STITCH_API_KEY>"
  }
}
```

Or copy the full `mcp_config.json` from this repo and replace `<YOUR_STITCH_API_KEY>`.

### Step 3: Restart Windsurf

Close and reopen Windsurf. Stitch should appear **green** in the MCPs panel (top right of Cascade).

---

## 💡 How to Use

Open Cascade in Windsurf and try these prompts:

```
Use Stitch to create a modern dashboard with sidebar navigation and charts.
```

```
List all my Stitch projects and screens.
```

```
Get the HTML code for screen X in my project.
```

```
Extract the design DNA from my existing dashboard screen,
then generate a settings page matching the same style.
```

---

## 🛠️ Available MCP Tools

| Tool | What It Does |
|------|-------------|
| `generate_screen_from_text` | Create UI from a text prompt |
| `get_screen_code` | Get HTML/CSS for a screen |
| `get_screen_image` | Get a screenshot of a screen |
| `list_projects` | List all your Stitch projects |
| `list_screens` | List screens in a project |
| `extract_design_context` | Extract colors, fonts, layout patterns |
| `build_site` | Generate an Astro site from screens |

---

## 🔐 Authentication

### Option A: API Key (Easiest)
Just set `STITCH_API_KEY` in your MCP config. No gcloud needed.

### Option B: OAuth via gcloud
```bash
gcloud auth application-default login
gcloud config set project YOUR_PROJECT_ID
gcloud beta services mcp enable stitch.googleapis.com --project=YOUR_PROJECT_ID
```

Config:
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
| Stitch not showing | Config must be at `~/.codeium/windsurf/mcp_config.json` |
| Connection errors | `npx @_davideast/stitch-mcp doctor --verbose` |
| Auth errors | Check API key at [stitch.withgoogle.com/settings](https://stitch.withgoogle.com/settings) |
| Tools not working | Restart Windsurf completely |
| Full reset | `npx @_davideast/stitch-mcp logout --force --clear-config` |

---

## 🔒 Security

**Never commit your real API keys.** This repo uses `<YOUR_STITCH_API_KEY>` as a placeholder.

---

## 📚 Resources

- [Google Stitch](https://stitch.withgoogle.com)
- [stitch-mcp GitHub](https://github.com/davideast/stitch-mcp)
- [Stitch MCP Docs](https://stitch.withgoogle.com/docs/mcp/setup)
- [Windsurf MCP Guide](https://docs.windsurf.com/windsurf/cascade/mcp)
- [Report Issues](https://github.com/githubModern/stitch-mcp-windsurf/issues)

---

## 📄 License

MIT
