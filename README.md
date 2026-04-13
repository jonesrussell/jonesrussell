# Ahnii!

I'm Russell Jones, an Ojibwe developer from Sagamok Anishnawbek in Northern Ontario.

I build the infrastructure Indigenous communities actually own.

## Available for Contract Work

Full-stack developer with 8+ years of experience. I build APIs, web applications, data pipelines, and infrastructure.

**Stack:** Go, Laravel, PHP, Vue.js, TypeScript, Tailwind CSS, PostgreSQL, Redis, Elasticsearch, Docker

**What I do:**
- Backend APIs and microservices (Go, PHP/Laravel)
- Full-stack web applications (Laravel + Vue/Inertia)
- Data pipelines and content processing systems
- DevOps and deployment automation (Docker, GitHub Actions, Caddy)

**Availability:** Immediate, remote

[Send me a message](mailto:russell@web.net) | [LinkedIn](https://linkedin.com/in/jonesrussell42) | [Blog](https://jonesrussell.github.io/blog)

## What I'm Building

- **[Waaseyaa](https://github.com/waaseyaa/framework)** -- PHP framework for Indigenous governance. Entity system, access control, AI-native.
- **[Minoo](https://minoo.live)** -- Language and cultural preservation platform. Dictionary, teachings, community, data sovereignty.
- **[OIATC](https://oiatc.waaseyaa.org)** -- Ontario Indigenous Technology Council. Governance, digital sovereignty, infrastructure stewardship.
- **[NorthOps](https://northops.ca)** -- Consulting for non-profits and First Nations organizations.
- **[North Cloud](https://github.com/jonesrussell/north-cloud)** -- Content intelligence pipeline: crawls, classifies, and routes articles in real time.
- **[GoFormX](https://goformx.com)** -- Modular form builder and backend.

## Automated Content Pipeline

This repo is the control plane for an automated content pipeline that turns development activity into published posts and social content.

```
Mine (GitHub Actions, daily)
  Scans commits + issues across repos
  Produces mined-seed.json items
  Creates GitHub Issues (content queue)
        |
Curate (human review)
  Filters, angles, sequences items
  Produces curated-item.json
        |
Produce (MCP skill)
  Generates Hugo blog draft + social copy
  Lands in jonesrussell/blog as PR
        |
Distribute (Buffer API)
  Posts to Facebook, X, LinkedIn
  Date-driven Hugo publish triggers deploy
```

**Stage contracts:** JSON Schemas in [`jonesrussell/blog/schemas/`](https://github.com/jonesrussell/blog/tree/main/schemas) enforce boundaries between stages. Each schema validates the output of one stage and the input of the next.

**Mining targets:** The workflow scans `waaseyaa/framework`, `waaseyaa/giiken`, and this repo. It filters out merge commits, chore/docs/bump commits, short messages, and noise like phpstan/namespace fixes.

**Content queue:** [GitHub Issues on this repo](https://github.com/jonesrussell/jonesrussell/issues?q=label%3Acontent-queue) are the browser-visible interface to the entire pipeline. Every item passes through as an issue, labeled by stage (`stage:mined`, `stage:curated`, `stage:ready`) and type (`type:text-post`, `type:blog-post`, `type:video`, `type:newsletter`). Filter by label to see items at any stage.

## Repository Structure

- `.github/workflows/content-mine.yml` -- Daily mining action (scans repos, creates issues)
- `.github/ISSUE_TEMPLATE/content-queue.md` -- Template for content queue issues
- `docs/` -- Pipeline documentation and specs

Schemas, blog drafts, and published posts live in [`jonesrussell/blog`](https://github.com/jonesrussell/blog).

## Related Repositories

| Repository | Role |
|---|---|
| [`jonesrussell/blog`](https://github.com/jonesrussell/blog) | Hugo site, schemas, published posts, Dev.to sync |
| [`waaseyaa/framework`](https://github.com/waaseyaa/framework) | PHP framework (mining target) |
| [`waaseyaa/giiken`](https://github.com/waaseyaa/giiken) | Waaseyaa package (mining target) |
| [`jonesrussell/north-cloud`](https://github.com/jonesrussell/north-cloud) | Content intelligence pipeline |

## Writing

I write about AI-augmented development, building open source infrastructure, and what digital sovereignty looks like in code.

[Blog](https://jonesrussell.github.io/blog) · [Newsletter](https://jonesrussell42.substack.com) · [russell@web.net](mailto:russell@web.net)
