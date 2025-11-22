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

| Framework | Repository | Description |
|-----------|------------|-------------|
| **React** | [shipi18n-react-example](https://github.com/Shipi18n/shipi18n-react-example) | Vite + React integration |
| **Next.js** | [shipi18n-nextjs-example](https://github.com/Shipi18n/shipi18n-nextjs-example) | App Router + Server Components |
| **CLI** | [shipi18n-cli](https://github.com/Shipi18n/shipi18n-cli) | Command-line tool |
| **Vue** | Coming soon | Vue 3 + vue-i18n |
| **Node.js** | Coming soon | Express/Fastify |

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
