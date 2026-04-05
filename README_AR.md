# Google Stitch MCP لبرنامج Windsurf (عربي)

**🎨 أنشئ تصاميم واجهات المستخدم واحصل على الكود — مباشرةً من Cascade AI في Windsurf.**

يستخدم الحزمة الرسمية [`@_davideast/stitch-mcp`](https://github.com/davideast/stitch-mcp) من Google.

---

## 📖 ماذا يفعل هذا الإعداد

[Google Stitch](https://stitch.withgoogle.com) أداة ذكاء اصطناعي تعمل بـ Gemini 2.5 Pro. تولّد تصاميم واجهات المستخدم + كود HTML/CSS من أوصاف نصية.

هذا المستودع يساعدك على ربط Stitch ببرنامج **Windsurf IDE** عبر بروتوكول MCP، لتتمكن من توليد التصاميم والحصول على الكود بدون مغادرة المحرر.

---

## 🚀 الإعداد (دقيقتان)

### الخطوة 1: الحصول على مفتاح API

1. اذهب إلى [stitch.withgoogle.com](https://stitch.withgoogle.com) وسجّل الدخول
2. اذهب إلى [الإعدادات](https://stitch.withgoogle.com/settings) وانسخ **مفتاح API** الخاص بك
3. أنشئ مشروع واحد على الأقل في Stitch

### الخطوة 2: الإضافة إلى Windsurf

افتح ملف إعدادات MCP في Windsurf:

- **Windows:** `%USERPROFILE%\.codeium\windsurf\mcp_config.json`
- **Mac/Linux:** `~/.codeium/windsurf/mcp_config.json`

أضف هذا داخل كتلة `"mcpServers"`:

```json
"stitch": {
  "command": "npx",
  "args": ["-y", "@_davideast/stitch-mcp", "proxy"],
  "env": {
    "STITCH_API_KEY": "<YOUR_STITCH_API_KEY>"
  }
}
```

أو انسخ ملف `mcp_config.json` من هذا المستودع واستبدل `<YOUR_STITCH_API_KEY>` بمفتاحك.

### الخطوة 3: إعادة تشغيل Windsurf

أغلق وأعد فتح Windsurf. سيظهر Stitch **باللون الأخضر** في لوحة MCPs (أعلى يمين Cascade).

---

## 💡 كيفية الاستخدام

افتح Cascade في Windsurf وجرّب هذه الأوامر:

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

## 🛠️ أدوات MCP المتاحة

| الأداة | الوصف |
|--------|-------|
| `generate_screen_from_text` | إنشاء شاشة من وصف نصي |
| `get_screen_code` | الحصول على كود HTML/CSS لشاشة |
| `get_screen_image` | الحصول على لقطة شاشة |
| `list_projects` | عرض جميع مشاريع Stitch |
| `list_screens` | عرض شاشات مشروع معين |
| `extract_design_context` | استخراج الألوان والخطوط وأنماط التخطيط |
| `build_site` | توليد موقع Astro من الشاشات |

---

## 🔐 خيارات المصادقة

### الخيار أ: مفتاح API (الأسهل)
فقط عيّن `STITCH_API_KEY` في إعدادات MCP. لا حاجة لـ gcloud.

### الخيار ب: OAuth عبر gcloud
```bash
gcloud auth application-default login
gcloud config set project YOUR_PROJECT_ID
gcloud beta services mcp enable stitch.googleapis.com --project=YOUR_PROJECT_ID
```

الإعدادات:
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

## 🔧 استكشاف الأخطاء

| المشكلة | الحل |
|---------|------|
| Stitch لا يظهر | تأكد من أن الإعدادات في `~/.codeium/windsurf/mcp_config.json` |
| أخطاء في الاتصال | `npx @_davideast/stitch-mcp doctor --verbose` |
| أخطاء في المصادقة | تحقق من مفتاح API في [stitch.withgoogle.com/settings](https://stitch.withgoogle.com/settings) |
| الأدوات لا تعمل | أعد تشغيل Windsurf بالكامل |
| إعادة ضبط كاملة | `npx @_davideast/stitch-mcp logout --force --clear-config` |

---

## 🔒 الأمان

**لا تشارك مفاتيح API الحقيقية أبداً.** هذا المستودع يستخدم `<YOUR_STITCH_API_KEY>` كعنصر نائب.

---

## 📚 مصادر

- [Google Stitch](https://stitch.withgoogle.com)
- [stitch-mcp على GitHub](https://github.com/davideast/stitch-mcp)
- [وثائق إعداد Stitch MCP](https://stitch.withgoogle.com/docs/mcp/setup)
- [دليل Windsurf MCP](https://docs.windsurf.com/windsurf/cascade/mcp)
- [الإبلاغ عن مشاكل](https://github.com/githubModern/stitch-mcp-windsurf/issues)

---

## 📄 الرخصة

MIT
