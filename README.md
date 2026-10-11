<div align="center">

<a href="https://curlshot.com">
  <img src="https://curlshot.com/api/og-image?title=Paste+a+web+address.+Get+a+screenshot." alt="CurlShot" width="720" />
</a>

# 📸 CurlShot

### Paste a web address. Get a screenshot of the page.

**Screenshot any website from top to bottom, as an image or a PDF.**
**Free to try. Nothing to install. One API request for developers.**

<br/>

[![Website](https://img.shields.io/badge/website-curlshot.com-6366F1?style=for-the-badge&logo=googlechrome&logoColor=white)](https://curlshot.com)
[![Status](https://img.shields.io/badge/status-live-22C55E?style=for-the-badge)](https://curlshot.com)
[![Free Tier](https://img.shields.io/badge/free-100%20shots%2Fmo-F59E0B?style=for-the-badge)](https://curlshot.com/register)
[![License](https://img.shields.io/badge/license-MIT-6366F1?style=for-the-badge)](LICENSE)

[![Docs](https://img.shields.io/badge/docs-read%20the%20guide-0EA5E9?style=flat-square&logo=readthedocs&logoColor=white)](https://curlshot.com/docs)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-spec-6BA539?style=flat-square&logo=openapiinitiative&logoColor=white)](https://curlshot.com/openapi.json)
[![MCP](https://img.shields.io/badge/MCP-ready-000000?style=flat-square)](https://curlshot.com/docs/guides/ai-agents)
[![llms.txt](https://img.shields.io/badge/llms.txt-available-8B5CF6?style=flat-square)](https://curlshot.com/llms.txt)

</div>

---

## 📌 What Is CurlShot?

**CurlShot** turns any web page into a clean image or PDF. You give it a URL, it opens the page like a real browser would, and hands you back the screenshot. Whole page or just the top, as a computer, phone or tablet sees it.

No browser farm to babysit. No Puppeteer crashes at 3 AM. **One HTTP request in, one file out.**

> *"If you can curl it, you can shot it."*

---

## ⚡ Quick Start

The whole API is one address. Every option is one more word in the URL.

```bash
curl -G "https://curlshot.com/api/v1/screenshot" \
  -d access_key=YOUR_ACCESS_KEY \
  --data-urlencode "url=https://example.com" \
  -d full_page=true \
  --output example.png
```

That's it. You now have a full-page PNG of `example.com`.

<details>
<summary><b>Node.js</b></summary>

```js
import fs from "node:fs";

const params = new URLSearchParams({
  access_key: process.env.CURLSHOT_KEY,
  url: "https://example.com",
  full_page: "true",
});

const res = await fetch(`https://curlshot.com/api/v1/screenshot?${params}`);
fs.writeFileSync("example.png", Buffer.from(await res.arrayBuffer()));
```
</details>

<details>
<summary><b>Python</b></summary>

```python
import os, requests

r = requests.get("https://curlshot.com/api/v1/screenshot", params={
    "access_key": os.environ["CURLSHOT_KEY"],
    "url": "https://example.com",
    "full_page": "true",
})
open("example.png", "wb").write(r.content)
```
</details>

<details>
<summary><b>PHP</b></summary>

```php
$query = http_build_query([
    'access_key' => getenv('CURLSHOT_KEY'),
    'url'        => 'https://example.com',
    'full_page'  => 'true',
]);
file_put_contents('example.png', file_get_contents("https://curlshot.com/api/v1/screenshot?$query"));
```
</details>

More examples (Go, Ruby, more) in the **[docs →](https://curlshot.com/docs/examples/node)**

---

## ✨ Features

<table>
<tr>
<td width="50%" valign="top">

### 📄 Capture
- Full-page screenshots, top to bottom
- Just the visible viewport
- Single element screenshots
- High-resolution / retina output
- Dark mode rendering
- Scrolling video of a website

</td>
<td width="50%" valign="top">

### 📱 Devices & Formats
- Desktop, phone and tablet viewports
- PNG, JPEG, WebP
- Print-ready PDF
- HTML → image / PDF
- Markdown → PDF
- Open Graph image generation

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🧹 Clean Output
- Hides cookie banners
- Blocks ads
- Removes chat bubbles
- Capture pages behind a login (cookies, headers, auth)

</td>
<td width="50%" valign="top">

### 🛠️ Built for Developers
- One GET request, any language
- Signed links (embed without leaking your key)
- Caching built in
- Async jobs + webhooks
- Bulk screenshots
- MCP server for AI agents

</td>
</tr>
</table>

---

## 🎯 What People Use It For

| Use case | What it does |
| --- | --- |
| 🗄️ **Keep a record** | Save how a price, terms page or competitor offer looked today |
| 📱 **Mobile checks** | See your site on a phone or tablet without picking one up |
| 📑 **Page → PDF** | Articles, invoices, reports as tidy printable docs |
| 🖼️ **Link previews** | Thumbnails for directories, portfolios, newsletters |
| 🔗 **Social images** | Auto-generated OG cards with the right title on every page |
| 🤖 **AI agents** | Give your agent eyes: `take_screenshot` via MCP |

---

## 💰 Pricing

Fixed monthly price. **Failed screenshots don't count. You're never charged extra.**

| Plan | Screenshots / month | Price |
| --- | --- | --- |
| 🆓 **Free** | 100 | $0 (no card) |
| 🚀 **Starter** | 3,000 | $19/mo |
| 📈 **Growth** | 15,000 | $79/mo |
| 🏢 **Scale** | 60,000 | $249/mo |

**[See all plans →](https://curlshot.com/pricing)**

---

## 🤖 Made for AI Agents

CurlShot speaks agent out of the box:

```
✓ MCP server with a take_screenshot tool
✓ OpenAPI description      → curlshot.com/openapi.json
✓ llms.txt site map        → curlshot.com/llms.txt
✓ Markdown version of every docs page
```

**[AI agent guide →](https://curlshot.com/docs/guides/ai-agents)**

---

## 🧰 Free Online Tools

No API key? Use it right in the browser:

[Full-page screenshot](https://curlshot.com/tools/full-page-screenshot) ·
[Web page to PDF](https://curlshot.com/tools/website-to-pdf) ·
[URL to image](https://curlshot.com/tools/url-to-image) ·
[Mobile screenshot](https://curlshot.com/tools/mobile-screenshot) ·
[Website thumbnail](https://curlshot.com/tools/website-thumbnail) ·
[HTML to image](https://curlshot.com/tools/html-to-image) ·
[HTML to PDF](https://curlshot.com/tools/html-to-pdf) ·
[Markdown to PDF](https://curlshot.com/tools/markdown-to-pdf) ·
[OG image generator](https://curlshot.com/tools/open-graph-image-generator) ·
[Screenshot without cookie banners](https://curlshot.com/tools/screenshot-without-cookie-banners) ·
[Bulk screenshots](https://curlshot.com/tools/bulk-screenshots) ·
**[All tools →](https://curlshot.com/tools)**

---

## 📚 Docs

| Topic | Link |
| --- | --- |
| 🏁 60-second guide | [Getting started](https://curlshot.com/docs/getting-started) |
| ⚙️ All options | [Options reference](https://curlshot.com/docs/options) |
| 📜 Full-page | [Full-page screenshots](https://curlshot.com/docs/full-page) |
| 📱 Devices | [Devices](https://curlshot.com/docs/devices) |
| 📑 PDF | [PDF rendering](https://curlshot.com/docs/pdf) |
| 🧹 Blocking | [Ads & cookie banners](https://curlshot.com/docs/blocking) |
| 🔐 Caching | [Caching & signed links](https://curlshot.com/docs/caching) |
| 🔔 Async | [Async & webhooks](https://curlshot.com/docs/async-and-webhooks) |
| ❌ Errors | [Error codes](https://curlshot.com/docs/errors) |

---

## ⚙️ Tech Stack

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Chromium](https://img.shields.io/badge/Headless_Chromium-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)

---

## 🤝 Contributing

Found a site that renders weird? A cookie banner that slipped through? Help make CurlShot better:

- **Report** — open an issue with the URL and what went wrong
- **Suggest** — request an option or tool you're missing
- **Share** — tell a dev friend who's still running their own Puppeteer box

---

## 📬 Stay Connected

[![Website](https://img.shields.io/badge/🌐_Website-curlshot.com-6366F1?style=for-the-badge)](https://curlshot.com)
[![Docs](https://img.shields.io/badge/📚_Docs-curlshot.com%2Fdocs-0EA5E9?style=for-the-badge)](https://curlshot.com/docs)
[![Contact](https://img.shields.io/badge/✉️_Contact-Get_in_touch-EA4335?style=for-the-badge)](https://curlshot.com/contact)

---

## 📄 License

This repository is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

<div align="center">

**One request in. One screenshot out.**

*If CurlShot saved you from maintaining a headless browser, drop a star. It helps more devs find it.*

⭐ **Star this repo if you find it useful** ⭐

<br/>

[![Start Free](https://img.shields.io/badge/Start_Free-100_screenshots%2Fmonth-22C55E?style=for-the-badge)](https://curlshot.com/register)

</div>
