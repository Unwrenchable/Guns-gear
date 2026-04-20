# Guns-gear

Epic, SEO-first guns and gear landing page upgrade for:
https://www.lrplongrangeprecision.com/

## Run locally

Open `index.html` in a browser.

## What was added

- SEO-focused metadata (title, description, canonical, Open Graph, Twitter)
- Structured data (`Organization`, `WebSite`, `SearchAction`)
- Semantic page layout for discoverability
- Built-in keyword search that filters featured guns and gear instantly
- Dedicated social links section and quick-access social links in footer
- Protected contact details with in-browser reveal + anti-spam contact form guardrails

## Agent Conventions

This repo uses GitHub Copilot custom agents to keep every area of the site under specialist oversight. Use the right agent for each type of task:

| Agent file | When to use |
|---|---|
| `.github/agents/LRP_Website_Builder.md` | General site planning, full-stack decisions, product page builds |
| `.github/agents/seo-content.agent.md` | Meta tags, structured data, headings hierarchy, keyword copy |
| `.github/agents/ui-ux.agent.md` | Layout, responsiveness, dark theme, WCAG accessibility |
| `.github/agents/catalog-data.agent.md` | Adding/updating product entries, search/filter logic |
| `.github/agents/trust-compliance.agent.md` | Age gates, legal disclaimers, restricted-item notices, copy review |
| `.github/agents/performance.agent.md` | Lighthouse scores, image optimization, Core Web Vitals |
| `.github/agents/qa-validator.agent.md` | HTML/CSS/JS validation, search regression, final QA gate |

### Rollout phases

- **Phase 1** — SEO + UI/UX + QA agents: highest immediate impact on search ranking and user experience.
- **Phase 2** — Catalog/data + performance: complete product catalog and optimize load speed.
- **Phase 3** — Compliance hardening: age gate, legal pages, jurisdictional notices, automation refinements.

### PR quality gate

Before merging any change to `index.html`, the `qa-validator` agent checks must pass:
1. `npx html-validate index.html` — zero errors
2. `npx axe http://localhost:3000 --exit` — zero WCAG AA violations
3. Structured data JSON-LD parses without errors
4. Keyword search regression (5 test queries)
5. Contact form honeypot blocks confirmed

### Governance

- Each agent file documents its own **Done Criteria** — a task is not complete until those criteria are met.
- Agents coordinate with each other via the **Coordination** section at the bottom of each file.
- Impact metrics to track over time: organic traffic (Google Search Console), Lighthouse mobile score, contact form conversions, bounce rate.
