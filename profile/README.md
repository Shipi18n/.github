<div align="center">

# Shipi18n

### Instant Translation API for Developers

**Translate your app to 100+ languages in seconds, not weeks.**

<br />

[![Website](https://img.shields.io/badge/Website-shipi18n.com-blue?style=for-the-badge&logo=google-chrome&logoColor=white)](https://shipi18n.com)
[![Documentation](https://img.shields.io/badge/Docs-integrations-green?style=for-the-badge&logo=readthedocs&logoColor=white)](https://shipi18n.com/integrations)
[![Get API Key](https://img.shields.io/badge/Get_API_Key-Free-orange?style=for-the-badge&logo=key&logoColor=white)](https://shipi18n.com)

<br />

[Get Started Free](https://shipi18n.com) | [Documentation](https://shipi18n.com/integrations) | [API Reference](https://shipi18n.com/api) | [Pricing](https://shipi18n.com/pricing)

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
import { Shipi18n } from '@shipi18n/api';

const shipi18n = new Shipi18n({
  apiKey: process.env.SHIPI18N_API_KEY, // Get your free key at shipi18n.com
});

const result = await shipi18n.translateJSON({
  content: {
    greeting: 'Hello, {{name}}!',
    items_one: '{{count}} item',
    items_other: '{{count}} items',
  },
  sourceLanguage: 'en',
  targetLanguages: ['es', 'fr', 'de', 'ja'],
});

console.log(result.es);
// { greeting: 'Hola, {{name}}!', items_one: '{{count}} artículo', items_other: '{{count}} artículos' }
```

## Key Features

| Feature | Description |
|---------|-------------|
| **100+ Languages** | Translate to any language Google Translate supports |
| **Placeholder Preservation** | Keeps `{name}`, `{{value}}`, `%s`, `<0>` intact |
| **JSON-Smart** | Upload `en.json`, download `es.json`, `fr.json`, etc. |
| **API & CLI** | Use programmatically or from your terminal |
| **Batch Translation** | Translate hundreds of strings in one request |
| **i18next Pluralization** | Auto-generates CLDR-compliant plural forms for all languages |
| **ICU MessageFormat** | Preserves ICU syntax like `{count, plural, one {...} other {...}}` |
| **Namespace Awareness** | Auto-detects and organizes translations by namespace |

### Smart Caching & Progress Tracking

<table>
<tr>
<td width="50%">

**Translation Caching**

Save **30-50% on costs** with intelligent caching:
- Previously translated strings are served instantly
- Only new/changed content uses API quota
- Cache persists across builds and CI runs
- Automatic cache invalidation on source changes

</td>
<td width="50%">

**Real-time Progress**

Track translation progress in real-time:
- Live progress indicators for large files
- Per-language completion status
- Detailed logging for CI/CD pipelines
- Webhook notifications on completion

</td>
</tr>
</table>

## Packages

### Official SDK & Tools

| Package | npm | Description |
|---------|-----|-------------|
| **[@shipi18n/api](https://github.com/Shipi18n/shipi18n-api)** | [![npm](https://img.shields.io/npm/v/@shipi18n/api)](https://www.npmjs.com/package/@shipi18n/api) | Official Node.js API client |
| **[@shipi18n/cli](https://github.com/Shipi18n/shipi18n-cli)** | [![npm](https://img.shields.io/npm/v/@shipi18n/cli)](https://www.npmjs.com/package/@shipi18n/cli) | CLI for translating locale files |

### Framework Integrations

| Package | npm | Description |
|---------|-----|-------------|
| **[vite-plugin-shipi18n](https://github.com/Shipi18n/vite-plugin-shipi18n)** | [![npm](https://img.shields.io/npm/v/vite-plugin-shipi18n)](https://www.npmjs.com/package/vite-plugin-shipi18n) | Build-time translation for Vite |
| **[i18next-shipi18n-backend](https://github.com/Shipi18n/i18next-shipi18n-backend)** | [![npm](https://img.shields.io/npm/v/i18next-shipi18n-backend)](https://www.npmjs.com/package/i18next-shipi18n-backend) | i18next backend for dynamic loading |
| **[shipi18n-github-action](https://github.com/Shipi18n/shipi18n-github-action)** | [![Marketplace](https://img.shields.io/badge/Marketplace-v1-blue)](https://github.com/marketplace/actions/shipi18n-auto-translate) | GitHub Action for CI/CD |

### Examples

| Example | Framework | Description |
|---------|-----------|-------------|
| **[shipi18n-nodejs-example](https://github.com/Shipi18n/shipi18n-nodejs-example)** | Node.js | Basic usage with @shipi18n/api |
| **[shipi18n-react-example](https://github.com/Shipi18n/shipi18n-react-example)** | React | Vite + React + react-i18next |
| **[shipi18n-vue-example](https://github.com/Shipi18n/shipi18n-vue-example)** | Vue 3 | Vue 3 + vue-i18n integration |
| **[shipi18n-nextjs-example](https://github.com/Shipi18n/shipi18n-nextjs-example)** | Next.js | App Router + Server Components |

## Quick Start

### Option 1: Node.js SDK

```bash
npm install @shipi18n/api
```

```javascript
import { Shipi18n } from '@shipi18n/api';

const shipi18n = new Shipi18n({ apiKey: 'your-api-key' });

const result = await shipi18n.translateJSON({
  content: { greeting: 'Hello', farewell: 'Goodbye' },
  sourceLanguage: 'en',
  targetLanguages: ['es', 'fr', 'de'],
});
```

### Option 2: CLI

```bash
# Install globally
npm install -g @shipi18n/cli

# Configure your API key (free at shipi18n.com)
shipi18n config --api-key sk_live_xxx

# Translate your locale file
shipi18n translate en.json --languages es,fr,de,ja
```

### Option 3: GitHub Action

```yaml
- uses: Shipi18n/shipi18n-github-action@v1
  with:
    api-key: ${{ secrets.SHIPI18N_API_KEY }}
    source-file: 'locales/en.json'
    target-languages: 'es,fr,de,ja'
```

## i18next Support

Shipi18n is optimized for i18next with automatic plural form generation:

```json
// Input (English - 2 forms)
{ "item_one": "{{count}} item", "item_other": "{{count}} items" }

// Output (Russian - 4 forms auto-generated!)
{
  "item_one": "{{count}} предмет",
  "item_few": "{{count}} предмета",
  "item_many": "{{count}} предметов",
  "item_other": "{{count}} предметов"
}
```

## Pricing

| Tier | Price | Keys | Languages | Rate Limit |
|------|-------|------|-----------|------------|
| **Free** | $0/mo | 100 | 3 | 10 req/min |
| **Starter** | $9/mo | 500 | 10 | 60 req/min |
| **Pro** | $29/mo | 10,000 | 100+ | 300 req/min |
| **Enterprise** | Custom | Unlimited | Custom | 1000+ req/min |

**[Start free at shipi18n.com](https://shipi18n.com)** - no credit card required.

## Why Shipi18n?

- **Fast**: Translate 100+ strings in under 3 seconds
- **Accurate**: Powered by Google Cloud Translation API
- **Developer-First**: Built for CLI, CI/CD, and automation
- **Affordable**: Free tier with generous limits
- **Type-Safe**: Full TypeScript support

---

<div align="center">

<br />

[![Get Your Free API Key](https://img.shields.io/badge/Get_Your_Free_API_Key-shipi18n.com-blue?style=for-the-badge&logo=rocket&logoColor=white)](https://shipi18n.com)

<br />

**[shipi18n.com](https://shipi18n.com)** · [Documentation](https://shipi18n.com/integrations) · [API Reference](https://shipi18n.com/api) · [Pricing](https://shipi18n.com/pricing)

<br />

Built for developers who ship fast.

</div>
