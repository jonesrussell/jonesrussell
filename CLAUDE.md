# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

Russell Jones's umbrella project. GitHub profile repo (`jonesrussell/jonesrussell`) that serves as the hub for personal brand, social presence, and content operations across all projects. Contains the profile README, content mining pipeline, and issue templates. No build system, no application code.

## Content Pipeline

This repo doubles as the **content queue hub** for Russell's projects. The pipeline works in stages tracked by GitHub issue labels:

1. **Mining** (`stage:mined`) — `.github/workflows/content-mine.yml` runs daily at 8am ET (cron) scanning recent commits and closed issues across `waaseyaa/framework`, `waaseyaa/giiken`, and `jonesrussell/jonesrussell`. Creates GitHub issues with the `content-queue` label. Filters out: merge commits, chore/docs/bump commits, short messages (<25 chars), phpstan/namespace/typo fixes.
2. **Curation** (`stage:curated`) — manual or skill-driven review of mined items.
3. **Production** (`stage:ready`) — content copy generated for target channels.
4. **Distribution** — posted via Buffer API to target channels.

**Distribution channels:** x, linkedin, facebook, youtube, substack, devto, blog, gumroad, topmate.io

Issue template: `.github/ISSUE_TEMPLATE/content-queue.md`

Content types: `type:text-post`, `type:blog-post`, `type:video`, `type:newsletter`

## Working with the Content Pipeline

```bash
# List all content queue items
gh issue list --repo jonesrussell/jonesrussell --label content-queue

# List by stage
gh issue list --repo jonesrussell/jonesrussell --label stage:mined
gh issue list --repo jonesrussell/jonesrussell --label stage:curated
gh issue list --repo jonesrussell/jonesrussell --label stage:ready

# Manually trigger the mining workflow
gh workflow run content-mine.yml --repo jonesrussell/jonesrussell
```

## Repository Structure

- `README.md` — GitHub profile page content
- `.github/workflows/content-mine.yml` — daily content mining action
- `.github/ISSUE_TEMPLATE/content-queue.md` — template for content queue issues

## Notes

- The mining workflow requires `CROSS_REPO_TOKEN` secret for cross-repo API access.
- Mining targets are hardcoded in the workflow file; update the `REPOS` variable to scan additional repositories.
