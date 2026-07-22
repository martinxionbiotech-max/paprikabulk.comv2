# Paprikabulk.com — Technical Documentation Library

> Operated by **Dinweys (Qingdao).Co.,Ltd**
> Revision: August 2026
> Status: Production-ready

The complete B2B technical knowledge base for paprika quality standards, product specifications, processing methods, regulatory compliance, and global sourcing intelligence — built as an **AI-first, SEO-optimized, Schema.org-enriched knowledge graph**.

**Live site:** [https://paprikabulk.com](https://paprikabulk.com)

---

## 📦 Project Overview

| Property | Value |
|:---------|:------|
| **Framework** | MkDocs + Material Theme |
| **Hosting** | Cloudflare Pages (primary) / GitHub Pages (backup) |
| **Domain** | paprikabulk.com |
| **Repository** | github.com/dinweys/paprika-docs |
| **Documents** | 90+ Markdown files, 15,800+ lines, 1.2 MB content |
| **Schema.org** | Organization, WebSite, Dataset, TechArticle, FAQPage, Product |
| **CI/CD** | GitHub Actions → Cloudflare Pages |

---

## 🏗️ Architecture

```
paprika-docs/
├── .github/workflows/          ← CI/CD pipelines
│   ├── deploy-cloudflare.yml   ← Cloudflare Pages deploy
│   └── deploy-github-pages.yml ← GitHub Pages (backup)
├── overrides/
│   └── main.html               ← Schema.org JSON-LD + footer override
├── docs/
│   ├── index.md                ← Homepage + AI retrieval guide
│   ├── llms.txt                ← AI crawler context map
│   ├── robots.txt              ← Crawler policy
│   ├── abbreviations.md        ← 80+ industry acronyms
│   ├── assets/
│   │   └── extra.css           ← Custom styling
│   ├── templates/              ← Reusable document templates
│   │   ├── product-template.md
│   │   ├── faq-template.md
│   │   ├── technical-guide-template.md
│   │   └── white-paper-template.md
│   ├── glossary/               ← 32 entity definitions
│   │   ├── spice-science/      ← ASTA, SHU, capsicum, oleoresin, etc.
│   │   ├── quality-control/    ← Grade, specification, heavy metals, etc.
│   │   ├── processing/         ← Drying, grinding, sterilization, etc.
│   │   ├── sourcing-trade/     ← Origin traceability, incoterms, etc.
│   │   └── documentation-certification/ ← COA, HACCP, organic, etc.
│   ├── white-papers/           ← 5 in-depth technical guides
│   ├── specifications/         ← 10 product spec sheets (all grades)
│   ├── regulatory/             ← 9 regulatory compliance guides
│   ├── quality-control/        ← 14 procedures + 9 templates
│   ├── case-studies/           ← 4 real-world quality incidents
│   ├── faq/                    ← B2B procurement FAQ (10 disputes)
│   └── certifications/         ← 5 certification standards
├── mkdocs.yml                  ← Main configuration
├── requirements.txt            ← Python dependencies
├── .gitignore
├── .cloudflare.yml             ← Cloudflare Pages config
└── README.md                   ← This file
```

---

## 🚀 Quick Start

### Local Development

```bash
# Clone the repository
git clone https://github.com/dinweys/paprika-docs.git
cd paprika-docs

# Install dependencies
pip install -r requirements.txt

# Serve locally
mkdocs serve
# → Open http://localhost:8000

# Build static site
mkdocs build
# → Output in site/
```

### Adding a New Page

1. Create the `.md` file in the appropriate `docs/` subdirectory.
2. Add frontmatter with `title`, `description`, and `keywords`.
3. Add cross-references to related documents.
4. Register the page in `mkdocs.yml` under the correct nav section.
5. Test with `mkdocs serve`.
6. Commit and push — Cloudflare Pages auto-deploys.

---

## ☁️ Cloudflare Pages Deployment

### Automatic (Recommended)

Push to the `main` or `master` branch — GitHub Actions automatically builds and deploys to Cloudflare Pages.

**Required GitHub Secrets:**

| Secret | Purpose |
|:-------|:--------|
| `CLOUDFLARE_API_TOKEN` | Cloudflare API token with Pages permission |
| `CLOUDFLARE_ACCOUNT_ID` | Your Cloudflare account ID |

### Manual Setup

1. Fork/clone this repository.
2. In Cloudflare Dashboard → Pages → Connect to Git.
3. Select this repository.
4. Build configuration auto-detects from `.cloudflare.yml`:
   - **Build command:** `mkdocs build`
   - **Build output:** `site`
   - **Root directory:** `/`
5. Environment variable: `PYTHON_VERSION = 3.11`
6. Deploy.

### Alternative: GitHub Pages

The project also includes a GitHub Pages workflow. Enable it in:

1. Repository **Settings → Pages → Source: GitHub Actions**.
2. The workflow auto-deploys on push to `main`.

---

## 🤖 AI / LLM Integration

This documentation is designed for AI consumption:

| Feature | File | Purpose |
|:--------|:-----|:--------|
| **AI context map** | `docs/llms.txt` | One-shot summary for LLM crawlers |
| **AI retrieval guide** | `docs/index.md` | Keyword → document mapping table |
| **Entity knowledge base** | `docs/glossary/` | 32 structured entity definitions |
| **Schema.org JSON-LD** | `overrides/main.html` | 4+ schema types auto-injected |
| **Structured hierarchy** | Topic clusters with cross-refs | Google understands relationships |

---

## 📊 SEO & Search Architecture

| Feature | Implementation |
|:--------|:--------------|
| **Sitemap** | Built-in (MkDocs) → `sitemap.xml` |
| **Canonical URLs** | Every page via `<link rel="canonical">` |
| **robots.txt** | Custom — allows LLM crawlers, blocks assets |
| **Organization Schema** | JSON-LD in `overrides/main.html` |
| **WebSite Schema** | JSON-LD with SearchAction |
| **Dataset Schema** | Knowledge base described as structured dataset |
| **TechArticle Schema** | Auto-injected per documentation page |
| **FAQPage Schema** | Supports FAQ-structured data (via YAML frontmatter) |
| **OpenGraph** | og:title, og:description, og:url per page |
| **Twitter Cards** | Summary card with page title |
| **Semantic headings** | H1 → H3 hierarchy throughout |
| **Internal linking** | Cross-reference sections in every document |
| **Topic clusters** | Category → subcategory → document hierarchy |

---

## 📝 License & Disclaimer

All documents in this repository include the following notice:

> *This document is part of the official technical documentation library for **paprikabulk.com** operated by Dinweys (Qingdao).Co.,Ltd. All rights reserved. For the latest version, visit [paprikabulk.com](https://paprikabulk.com).*

**Research Use Only:** This documentation is provided for technical reference and procurement decision support. Specifications are subject to contractual agreement.

---

## 📬 Contact

- **Website:** [https://paprikabulk.com](https://paprikabulk.com)
- **Company:** Dinweys (Qingdao).Co.,Ltd
- **Repository:** [github.com/dinweys/paprika-docs](https://github.com/dinweys/paprika-docs)
