# Google Stitch MCP for Windsurf

**🎨 Transform your design ideas into code instantly with Google Stitch and Windsurf!**

---

## 📖 What This Does

This setup connects Google Stitch (Google's AI design tool) directly to Windsurf IDE, giving you **36 powerful tools** to:

- ✨ **Generate UI screens** from simple text descriptions
- 🔄 **Convert designs to React/Tailwind code** automatically  
- 🎨 **Extract design tokens** (colors, fonts, spacing)
- 🌙 **Create dark mode** versions with one click
- 📱 **Make responsive designs** for mobile/tablet/desktop
- ♿ **Check accessibility** (WCAG 2.1 compliance)
- 📦 **Export design systems** and component libraries

---

## 🚀 Quick Start (3 Steps)

### Step 1: Install Stitch MCP Server
```bash
git clone https://github.com/oogleyskr/stitch-mcp-server.git
cd stitch-mcp-server
npm install
npm run build
```

### Step 2: Copy Config File
**Windows:**
```bash
copy mcp_config.json %USERPROFILE%\.codeium\windsurf\mcp_config.json
```

**Mac/Linux:**
```bash
cp mcp_config.json ~/.codeium/windsurf/mcp_config.json
```

### Step 3: Add Your API Key
1. Get your API key from [Google AI Studio](https://aistudio.google.com/apikey)
2. Open the config file and replace:
   - `<YOUR_STITCH_API_KEY>` with your actual API key
   - `<PATH_TO>/stitch-mcp-server/dist/index.js` with the full path to your server

### Step 4: Restart Windsurf
Close and reopen Windsurf. Look for the **MCPs** icon in the Cascade panel - Stitch should be there!

---

## 💡 How to Use

### Generate a UI Design
```
Create a modern e-commerce homepage with hero section, product grid, and shopping cart
```

### Convert to Code
```
Convert this design to React with Tailwind CSS and extract all design tokens
```

### Make Dark Mode
```
Create a dark mode version of this screen with high contrast
```

### Check Accessibility
```
Analyze this design for WCAG 2.1 AA compliance and fix any issues
```

---

## 🛠️ Available Tools (36 Total)

### Design Generation
- **Screen Generation** - Create screens from text
- **Templates** - Use pre-built layouts (dashboard, login, etc.)
- **Batch Generation** - Create multiple screens at once
- **Trending Designs** - Apply modern UI trends

### Code Conversion
- **React/TSX** - Convert to React components
- **Tailwind Config** - Extract complete Tailwind setup
- **CSS Variables** - Generate CSS custom properties
- **Design Tokens** - Export design system tokens

### Analysis & Optimization
- **Accessibility Audit** - WCAG compliance checking
- **Design Analysis** - Extract colors, typography, spacing
- **Responsive Testing** - Mobile/tablet/desktop variants
- **Performance Review** - Design optimization suggestions

### Export & Documentation
- **Style Guide** - Auto-generate design documentation
- **Component Library** - Export reusable components
- **Design System** - Complete design system export
- **Bulk Export** - Export all project screens

---

## 🔧 Troubleshooting

**❌ Stitch not showing up?**
- Check config is at `~/.codeium/windsurf/mcp_config.json`
- Verify the server path is correct
- Make sure you restarted Windsurf

**❌ Connection errors?**
- Run `npm run build` in the stitch-mcp-server folder
- Check your API key is valid
- Ensure Node.js 18+ is installed

**❌ Tools not working?**
- Restart Windsurf completely
- Check MCP panel for connection status
- Verify your API key permissions

---

## 🔒 Security

**⚠️ Important:** Never share your API key! The config file uses placeholders. Keep your secrets safe.

---

## 📚 Need Help?

- [Google Stitch Documentation](https://stitch.googleapis.com)
- [Windsurf MCP Guide](https://docs.windsurf.com/windsurf/cascade/mcp)
- [Report Issues](https://github.com/githubModern/stitch-mcp-windsurf/issues)

---

## 🤝 Contributing

Found bugs or want to improve? Open an issue or submit a pull request!

---

**🎉 Happy coding with AI-powered design!**
