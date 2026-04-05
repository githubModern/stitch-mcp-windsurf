# Google Stitch MCP for Windsurf

A complete setup guide for integrating Google Stitch's design-to-code capabilities with Windsurf IDE using the Model Context Protocol (MCP).

## 🎯 What This Enables

With Google Stitch MCP, you can:

- **Generate UI screens** from text prompts
- **Convert designs to React/Tailwind code**
- **Extract design tokens** (colors, typography, spacing)
- **Generate dark mode** variants automatically
- **Create responsive** variants (mobile/tablet/desktop)
- **Run accessibility audits** (WCAG 2.1 compliance)
- **Batch generate** multiple screens
- **Export design systems** and component libraries

**36 powerful tools** for design-to-code workflows, all available directly in Windsurf's Cascade AI.

## 📋 Prerequisites

- **Node.js 18+** — [Download](https://nodejs.org/)
- **Google Stitch API Key** — Get from [Google AI Studio](https://aistudio.google.com/apikey)
- **Windsurf IDE** — [Download](https://windsurf.com/)

## 🚀 Quick Setup

### 1. Install Stitch MCP Server

```bash
git clone https://github.com/oogleyskr/stitch-mcp-server.git
cd stitch-mcp-server
npm install
npm run build
```

> Move the cloned folder to a permanent location (e.g., `C:\Users\<you>\mcp-servers\stitch-mcp-server` on Windows or `~/mcp-servers/stitch-mcp-server` on Mac/Linux).

### 2. Configure Windsurf

Copy the `mcp_config.json` file to your Windsurf MCP config location:

**Windows:**
```bash
copy mcp_config.json %USERPROFILE%\.codeium\windsurf\mcp_config.json
```

**macOS / Linux:**
```bash
cp mcp_config.json ~/.codeium/windsurf/mcp_config.json
```

### 3. Add Your API Key

Open `~/.codeium/windsurf/mcp_config.json` and replace:

| Placeholder | Replace With |
|-------------|-------------|
| `<PATH_TO>/stitch-mcp-server/dist/index.js` | Full path to your built Stitch server |
| `<YOUR_STITCH_API_KEY>` | Your Google Stitch API key |

Example for Windows:
```json
{
  "mcpServers": {
    "stitch": {
      "command": "node",
      "args": ["C:\\Users\\YourName\\mcp-servers\\stitch-mcp-server\\dist\\index.js"],
      "env": {
        "STITCH_API_KEY": "<YOUR_STITCH_API_KEY>"
      }
    }
  }
}
```

### 4. Restart Windsurf

Close and reopen Windsurf. The Stitch MCP server will appear in the **MCPs** icon in the Cascade panel.

## 🎨 Usage Examples

### Generate a UI Screen
```
Create a modern e-commerce product page with a hero section, product gallery, and checkout button
```

### Convert Design to Code
```
Convert this design to React with Tailwind CSS and extract the design tokens
```

### Generate Dark Mode
```
Create a dark mode variant of this screen with high contrast
```

### Accessibility Audit
```
Check this screen for WCAG 2.1 AA compliance and suggest improvements
```

## 🛠️ Available Tools

### Design Generation
- `stitch_generate_screen_from_text` - Create screens from prompts
- `stitch_generate_from_template` - Use predefined templates
- `stitch_batch_generate_screens` - Generate multiple screens
- `stitch_suggest_trending_design` - Apply modern UI trends

### Code Generation  
- `stitch_screen_to_react` - Convert to React/TSX
- `stitch_screen_to_tailwind_config` - Extract Tailwind config
- `stitch_screen_to_css_variables` - Generate CSS variables
- `stitch_generate_design_tokens` - Export design tokens

### Analysis & Export
- `stitch_analyze_accessibility` - WCAG compliance check
- `stitch_extract_design_context` - Extract design DNA
- `stitch_export_all_screens` - Bulk export
- `stitch_generate_style_guide` - Create documentation

### Variants & Adaptation
- `stitch_generate_dark_mode` - Dark mode variants
- `stitch_generate_responsive_variant` - Responsive adaptations
- `stitch_generate_component_variants` - Component variations

## 🔧 Troubleshooting

**Stitch not appearing in Windsurf?**
- Verify config is at `~/.codeium/windsurf/mcp_config.json`
- Check that the server path is correct
- Ensure your API key is valid

**Server connection errors?**
- Make sure you ran `npm run build` in the stitch-mcp-server folder
- Check Node.js version (18+ required)
- Verify the API key format

**Tools not working?**
- Restart Windsurf completely
- Check the MCP panel for connection status
- Verify your Stitch API key has proper permissions

## 🔒 Security

> **Never commit your real API keys to Git.** The included `mcp_config.json` uses placeholder values. Always keep your secrets local.

## 📚 Resources

- [Google Stitch Documentation](https://stitch.googleapis.com)
- [Windsurf MCP Guide](https://docs.windsurf.com/windsurf/cascade/mcp)
- [Model Context Protocol](https://modelcontextprotocol.io/)

## 🤝 Contributing

Found issues or improvements? Open an issue or submit a pull request.

## 📄 License

MIT License - feel free to use and modify for your projects.
