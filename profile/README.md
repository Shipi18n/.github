<div align="center">

# Shipi18n

### Instant Translation API for Developers

**Translate your app to 100+ languages in seconds, not weeks.**

[Get Started Free](https://shipi18n.com) | [Documentation](https://shipi18n.com/#/integrations) | [Pricing](https://shipi18n.com/#/pricing)

</div>

---

## The Problem

Localizing your app is painful:
- Copy-pasting strings into Google Translate
- Managing JSON files manually
- Broken placeholders like `{name}` or `{{count}}`
- Hours spent on what should take minutes

## The Solution

Shipi18n is a translation API built for developers. Upload your locale files, get translations back instantly.

```javascript
import { translate } from 'shipi18n'

const result = await translate({
  text: 'Hello, {{name}}! You have {{count}} messages.',
  targetLanguages: ['es', 'fr', 'de', 'ja'],
})

// Placeholders preserved automatically!
// es: "Hola, {{name}}! Tienes {{count}} mensajes."
```

## Key Features

| Feature | Description |
|---------|-------------|
| **100+ Languages** | Translate to any language Google Translate supports |
| **Placeholder Preservation** | Keeps `{name}`, `{{value}}`, `%s`, `<0>` intact |
| **JSON-Smart** | Upload `en.json`, download `es.json`, `fr.json`, etc. |
| **API & CLI** | Use programmatically or from your terminal |
| **Key Management** | Store and manage your translation keys |
| **Batch Translation** | Translate hundreds of strings in one request |
| **i18next Pluralization** | Auto-generates CLDR-compliant plural forms for all languages |
| **ICU MessageFormat** | Preserves ICU syntax like `{count, plural, one {...} other {...}}` |
| **Namespace Awareness** | Auto-detects and organizes translations by namespace |
| **Key Validation** | Warns about anti-patterns and suggests best practices |

## i18next Best Practices

Shipi18n is optimized for i18next and follows industry best practices:

### ✅ Automatic Plural Forms

Different languages have different plural rules. Shipi18n automatically generates the correct plural forms for each target language:

- **English/Spanish**: `_one`, `_other` (2 forms)
- **Russian**: `_one`, `_few`, `_many`, `_other` (4 forms)
- **Arabic**: `_zero`, `_one`, `_two`, `_few`, `_many`, `_other` (6 forms)

```json
// Input (English)
{
  "item_one": "{{count}} item",
  "item_other": "{{count}} items"
}

// Output (Russian) - 4 forms auto-generated!
{
  "item_one": "{{count}} предмет",
  "item_few": "{{count}} предмета",
  "item_many": "{{count}} предметов",
  "item_other": "{{count}} предметов"
}
```

### ✅ ICU MessageFormat Support

Shipi18n detects and preserves ICU MessageFormat syntax:

```json
{
  "greeting": "{gender, select, male {Hello Mr. {name}} female {Hello Ms. {name}} other {Hello {name}}}",
  "count": "{count, plural, =0 {no items} one {# item} other {# items}}"
}
```

The syntax structure is preserved while the translatable text is translated.

### ✅ Namespace Organization

Organize translations by feature or domain:

```json
{
  "common": { "save": "Save", "cancel": "Cancel" },
  "auth": { "login": "Login", "logout": "Logout" },
  "checkout": { "total": "Total", "pay": "Pay Now" }
}
```

Shipi18n auto-detects namespaces and returns organized output.

### ✅ Key Validation

Shipi18n warns about common anti-patterns:

- ❌ Avoid numeric-only keys: `"1": "First"` → Use `"step_1": "First"`
- ❌ Avoid spaces in keys: `"my key": "Value"` → Use `"my_key": "Value"`
- ❌ Avoid all-caps keys: `"BUTTON": "Click"` → Use `"button_click": "Click"`
- ❌ Avoid deeply nested structures (3+ levels)

## Quick Start

```bash
# Install the CLI
npm install -g shipi18n-cli

# Configure your API key (free at shipi18n.com)
shipi18n config --api-key sk_live_xxx

# Translate your locale file
shipi18n translate en.json --languages es,fr,de,ja
```

## Integration Examples

| Framework/Tool | Repository | Description |
|----------------|------------|-------------|
| **React** | [shipi18n-react-example](https://github.com/Shipi18n/shipi18n-react-example) | Vite + React integration |
| **Next.js** | [shipi18n-nextjs-example](https://github.com/Shipi18n/shipi18n-nextjs-example) | App Router + Server Components |
| **Vue** | [shipi18n-vue-example](https://github.com/Shipi18n/shipi18n-vue-example) | Vue 3 + vue-i18n integration |
| **CLI** | [@shipi18n/cli](https://github.com/Shipi18n/shipi18n-cli) | Command-line tool for translating locale files |
| **Node.js API** | [@shipi18n/api](https://github.com/Shipi18n/shipi18n-api) | Official Node.js API client |
| **Vite Plugin** | [vite-plugin-shipi18n](https://github.com/Shipi18n/vite-plugin-shipi18n) | Automatic build-time translation for Vite |
| **GitHub Action** | [shipi18n-github-action](https://github.com/Shipi18n/shipi18n-github-action) | Automate translations in CI/CD pipelines |

## Pricing

| Tier | Price | Translation Keys | Languages |
|------|-------|------------------|-----------|
| **Free** | $0/mo | 100 | 3 |
| **Starter** | $9/mo | 500 | 10 |
| **Pro** | $29/mo | 10,000 | 100+ |
| **Enterprise** | Custom | Unlimited | Custom |

[Start free](https://shipi18n.com) - no credit card required.

## Why Shipi18n?

- **Fast**: Translate 100+ strings in under 3 seconds
- **Accurate**: Powered by Google Cloud Translation API
- **Developer-First**: Built for CLI, CI/CD, and automation
- **Affordable**: Free tier with generous limits
- **Secure**: API keys never exposed to browsers (with proper setup)

---

<div align="center">

**[Get Your Free API Key](https://shipi18n.com)**

Built for developers who ship fast.

</div>
