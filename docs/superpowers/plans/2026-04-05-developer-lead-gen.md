# Developer Lead Generation Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Get Russell actively prospecting for paid dev work across multiple channels, with the first outbound posts live by end of week 1 and first paid engagement within 2 weeks.

**Architecture:** Two-track approach. Track 1 (Tasks 1-5) gets outbound posts live immediately using existing "Job Applications" calendar blocks. Track 2 (Tasks 6-9) builds compounding assets (polished profiles, platform applications, GitHub tracking). Calendar events and GitHub milestones coordinate everything.

**Tech Stack:** GitHub Issues/Milestones, Google Calendar, LinkedIn, Facebook, Discord, Reddit, Upwork

---

## Task 1: Set Up GitHub Tracking Infrastructure

**Files:**
- Repo: `jonesrussell/jonesrussell`

- [ ] **Step 1: Create issue labels**

```bash
gh label create "lead-gen" --description "Lead generation tasks" --color "0E8A16" --repo jonesrussell/jonesrussell
gh label create "lead" --description "Actual opportunity/prospect" --color "FBCA04" --repo jonesrussell/jonesrussell
gh label create "channel:facebook" --description "Facebook channel" --color "1877F2" --repo jonesrussell/jonesrussell
gh label create "channel:discord" --description "Discord channel" --color "5865F2" --repo jonesrussell/jonesrussell
gh label create "channel:linkedin" --description "LinkedIn channel" --color "0A66C2" --repo jonesrussell/jonesrussell
gh label create "channel:reddit" --description "Reddit channel" --color "FF4500" --repo jonesrussell/jonesrussell
gh label create "channel:upwork" --description "Upwork channel" --color "14A800" --repo jonesrussell/jonesrussell
gh label create "channel:direct" --description "Direct outreach" --color "6F42C1" --repo jonesrussell/jonesrussell
```

- [ ] **Step 2: Create milestones**

```bash
gh api repos/jonesrussell/jonesrussell/milestones -f title="Lead Gen Launch" -f description="Week 1-2: Join channels, first posts, profile polish" -f due_on="2026-04-19T00:00:00Z"
gh api repos/jonesrussell/jonesrussell/milestones -f title="Pipeline Maturity" -f description="Week 3-6: Platform applications, northops integration, refine what converts" -f due_on="2026-05-17T00:00:00Z"
gh api repos/jonesrussell/jonesrussell/milestones -f title="Steady State" -f description="Week 6+: Reduce manual effort, lean on automation and inbound" -f due_on="2026-06-14T00:00:00Z"
```

- [ ] **Step 3: Create initial tracking issues for channel setup**

```bash
gh issue create --title "Join and post in 3-4 Facebook developer groups" \
  --label "lead-gen,channel:facebook" \
  --milestone "Lead Gen Launch" \
  --body "## Groups to join
- [ ] Find and join 3-4 active Facebook groups (freelance dev, hiring developers, remote work)
- [ ] Read each group's rules for self-promotion
- [ ] Post 'available for hire' in each group (adapt template per group)
- [ ] Respond to any existing job posts

## Template (adapt per group)
Full-stack developer, 8+ years. Go, Laravel, Vue, TypeScript. APIs, web apps, data pipelines, DevOps. Available immediately, remote. [portfolio link]" \
  --repo jonesrussell/jonesrussell

gh issue create --title "Join and post in 2-3 Discord developer servers" \
  --label "lead-gen,channel:discord" \
  --milestone "Lead Gen Launch" \
  --body "## Servers to join
- [ ] Devs For Hire & Jobs
- [ ] The Programmer's Hangout (#jobs channel)
- [ ] One more niche server (Laravel or Go focused)
- [ ] Participate in general channels for credibility first
- [ ] Post in #for-hire channels after a few days of engagement" \
  --repo jonesrussell/jonesrussell

gh issue create --title "Post [FOR HIRE] on Reddit r/forhire" \
  --label "lead-gen,channel:reddit" \
  --milestone "Lead Gen Launch" \
  --body "## Post details
- [ ] Create post in r/forhire
- Title: [FOR HIRE] Go/Laravel/Vue Full-Stack Dev | 8+ Years | Remote | APIs, Web Apps, Data Pipelines
- Body: 3-4 bullet points, portfolio link, rate range optional
- Note: one post per month max (rule enforced)" \
  --repo jonesrussell/jonesrussell

gh issue create --title "Set up Upwork profile and send first proposals" \
  --label "lead-gen,channel:upwork" \
  --milestone "Lead Gen Launch" \
  --body "## Setup
- [ ] Create/optimize Upwork profile
- [ ] Niche the profile (don't try to be everything)
- [ ] Write 2-3 portfolio items with outcomes
- [ ] Send first 5 proposals on relevant gigs
- [ ] Track response rates

## Note
First 2-3 jobs: compete on proposal quality, accept slightly lower rate to build reviews. 5-star reviews unlock better rates." \
  --repo jonesrussell/jonesrussell

gh issue create --title "Optimize LinkedIn for contract work" \
  --label "lead-gen,channel:linkedin" \
  --milestone "Lead Gen Launch" \
  --body "## Profile updates
- [ ] Rewrite headline: 'Full-Stack Developer | Go, Laravel, Vue | Available for Contract Work'
- [ ] Turn on 'Open to Work'
- [ ] Update About section with services and availability
- [ ] Post first 'available for hire' update

## Ongoing (Track 2)
- Post 2-3x/week about what you're building
- Send 3-5 personalized outreach messages per week to CTOs/founders at 10-50 person companies" \
  --repo jonesrussell/jonesrussell
```

- [ ] **Step 4: Commit**

```bash
cd /home/jones/dev/jonesrussell
git add docs/superpowers/specs/2026-04-05-developer-lead-gen-design.md docs/superpowers/plans/2026-04-05-developer-lead-gen.md
git commit -m "docs: add developer lead generation spec and implementation plan"
```

---

## Task 2: Repurpose "Job Applications" Block for Lead Scanning

The existing daily "Job Applications" block (9-10am) is the perfect home for Track 1 daily lead scanning. No new calendar event needed, just expand its scope.

- [ ] **Step 1: Update the existing "Job Applications" recurring event description**

Update the recurring event description to include lead gen scanning:

```
Daily Lead Gen & Job Applications (9:00-10:00am)

1. Scan Facebook groups for job posts — respond to any matching your stack
2. Check Discord #jobs channels — respond to relevant posts
3. Check Upwork for new gigs — send 1-2 proposals
4. Check LinkedIn notifications — respond to any inbound messages
5. Traditional job applications (if any active)
6. Log any promising leads as GitHub issues with 'lead' label
```

- [ ] **Step 2: Update the calendar event via API**

```
Update recurring event "Job Applications" with the new description above.
```

---

## Task 3: Create Weekly Prospecting Block on Calendar

The Saturday "Course & Business Dev" block (1-4pm) already exists and is the right place for the weekly deep-dive. Create a separate 90-min "Lead Gen Prospecting" block within that window.

- [ ] **Step 1: Create recurring calendar event**

Create: "Lead Gen Prospecting" every Saturday 1:00-2:30pm ET, recurring weekly.

Description:
```
Weekly Lead Gen Deep-Dive

1. Review the week: which channels produced conversations? which were silent?
2. Refresh "available" posts in Facebook groups (if allowed by group rules)
3. Send 3-5 personalized outreach messages (LinkedIn DMs to CTOs/founders)
4. Check platform application statuses (Toptal, Contra, etc.)
5. Update GitHub tracking issues with results
6. Plan next week's focus based on what's converting
```

- [ ] **Step 2: Create a GitHub issue for the first prospecting session**

```bash
gh issue create --title "First weekly prospecting session (2026-04-11)" \
  --label "lead-gen" \
  --milestone "Lead Gen Launch" \
  --body "## Agenda
- [ ] Review: which channels have I posted in? Any responses?
- [ ] Refresh posts where allowed
- [ ] Send 3-5 personalized LinkedIn outreach messages
- [ ] Check Upwork proposal statuses
- [ ] Log results and adjust plan for next week" \
  --repo jonesrussell/jonesrussell
```

---

## Task 4: Create Content-as-Lead-Gen Calendar Block

Your existing Tuesday "Social — LinkedIn + X/Bluesky" block (12:30-2pm) already covers LinkedIn posting. Add a lead gen angle to it.

- [ ] **Step 1: Update the Tuesday social block description**

Add to the existing description:
```
Lead Gen Angle:
- Include "available for contract work" or "DMs open" in at least one post per week
- When posting technical content, end with availability CTA
- Repurpose blog posts as proof of expertise (case studies > tutorials for lead gen)
```

---

## Task 5: Research and Join Specific Channels

This is the hands-on work Russell does during his first "Job Applications" block.

- [ ] **Step 1: Create a research issue with specific channels to investigate**

```bash
gh issue create --title "Research and join specific Facebook groups and Discord servers" \
  --label "lead-gen,channel:facebook,channel:discord" \
  --milestone "Lead Gen Launch" \
  --body "## Facebook Groups to investigate
Search Facebook for these types of groups and join the most active ones:
- [ ] 'Freelance Web Developers' (or similar name, 10k+ members)
- [ ] 'Remote Jobs for Developers'
- [ ] Laravel-specific hiring group
- [ ] WordPress/general dev freelance group
- [ ] The group Russell already found: facebook.com/groups/582843471750856

**Evaluation criteria:** Active posts in last 24h, allows self-promotion, has job posts not just spam.

## Discord Servers to investigate
- [ ] Search for 'Devs For Hire' or 'Freelance Developer' on Discord server lists (disboard.org, discord.me)
- [ ] The Programmer's Hangout (large, has #jobs)
- [ ] Any Go or Laravel-specific community with a jobs channel

**Evaluation criteria:** Active #jobs or #for-hire channel, posts in last week, not dead.

## Deliverable
Comment on this issue with the groups/servers joined and first impressions." \
  --repo jonesrussell/jonesrussell
```

---

## Task 6: Polish GitHub Profile README

- [ ] **Step 1: Read current README**

```bash
cat /home/jones/dev/jonesrussell/README.md
```

- [ ] **Step 2: Add "Available for Hire" section**

Add a prominent section near the top of README.md (after the intro, before project details):

```markdown
## Available for Contract Work

Full-stack developer with 8+ years of experience. I build APIs, web applications, data pipelines, and infrastructure.

**Stack:** Go, Laravel, PHP, Vue.js, TypeScript, Tailwind CSS, PostgreSQL, Redis, Elasticsearch, Docker

**What I do:**
- Backend APIs and microservices (Go, PHP/Laravel)
- Full-stack web applications (Laravel + Vue/Inertia)
- Data pipelines and content processing systems
- DevOps and deployment automation (Docker, GitHub Actions, Caddy)

**Availability:** Immediate, remote

[Send me a message](mailto:jonesrussell42@gmail.com) | [LinkedIn](https://linkedin.com/in/jonesrussell42) | [Blog](https://jonesrussell.github.io)
```

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "docs: add available for hire section to profile README"
```

---

## Task 7: Apply to Vetted Developer Platforms

- [ ] **Step 1: Create tracking issue**

```bash
gh issue create --title "Apply to vetted developer platforms (Toptal, Contra, Gun.io)" \
  --label "lead-gen" \
  --milestone "Pipeline Maturity" \
  --body "## Platforms to apply
- [ ] **Toptal** — toptal.com/developers/apply. Rigorous vetting (coding test + live interview). Premium rates once in. Apply by Week 2.
- [ ] **Contra** — contra.com. Commission-free. Create profile, add portfolio items. Apply by Week 2.
- [ ] **Gun.io** — gun.io. Vetted dev marketplace, decent quality clients. Apply by Week 3.
- [ ] **Lemon.io** — lemon.io. European-focused but accepts remote. Apply by Week 3.

## Notes
- Each requires a polished profile. Use the same base pitch adapted per platform.
- Toptal has the highest barrier but the best ROI. Prioritize it.
- Track application status and update this issue." \
  --repo jonesrussell/jonesrussell
```

---

## Task 8: Create Lead Tracking Issue Template

- [ ] **Step 1: Create the issue template file**

Create `.github/ISSUE_TEMPLATE/lead.md`:

```markdown
---
name: Lead
about: Track a potential client or project opportunity
title: "Lead: [Client/Project Name]"
labels: lead
assignees: jonesrussell
---

## Source
<!-- Where did this lead come from? -->
- Channel: <!-- facebook / discord / linkedin / reddit / upwork / direct -->
- Link: <!-- URL to the original post or conversation -->
- Date found: <!-- YYYY-MM-DD -->

## Details
<!-- What are they looking for? -->
- Project type: <!-- web app / API / mobile / consulting / other -->
- Tech stack: <!-- What technologies are involved? -->
- Budget/rate: <!-- If mentioned -->
- Timeline: <!-- If mentioned -->

## Status
- [ ] Initial response sent
- [ ] Conversation started
- [ ] Requirements discussed
- [ ] Proposal/quote sent
- [ ] Accepted / Declined / No response

## Notes
<!-- Any additional context, red flags, or observations -->
```

- [ ] **Step 2: Commit**

```bash
git add .github/ISSUE_TEMPLATE/lead.md
git commit -m "feat: add lead tracking issue template"
```

---

## Task 9: Create Weekly Review Checklist Issue

- [ ] **Step 1: Create the recurring review template**

```bash
gh issue create --title "Weekly lead gen review template" \
  --label "lead-gen" \
  --milestone "Lead Gen Launch" \
  --body "## Use this checklist every Saturday during Lead Gen Prospecting block

### Channel Performance
- [ ] Facebook groups: posts made / responses received / conversations started
- [ ] Discord: engagement level / any leads
- [ ] Reddit: post status (monthly limit)
- [ ] LinkedIn: profile views / connection requests / DM responses
- [ ] Upwork: proposals sent / interviews / hires

### Metrics
- Total posts/responses this week: ___
- Conversations started: ___
- Proposals sent: ___
- Revenue this week: \$___

### Adjustments
- Which channels are working? Double down.
- Which channels are dead? Drop or reduce effort.
- Any new channels to try?
- Update GitHub issues with status.

### Next Week Focus
- [ ] Identify top 3 channels to focus on
- [ ] Plan outreach targets
- [ ] Any profile/portfolio updates needed?" \
  --repo jonesrussell/jonesrussell
```

---

## Summary: Execution Order

| Task | When | Depends On |
|------|------|-----------|
| Task 1: GitHub tracking setup | Now (today) | Nothing |
| Task 2: Update Job Applications block | Now (today) | Nothing |
| Task 3: Create weekly prospecting event | Now (today) | Nothing |
| Task 4: Update Tuesday social block | Now (today) | Nothing |
| Task 5: Research and join channels | Tomorrow (first Job Applications block) | Task 1 |
| Task 6: Polish GitHub README | This week | Nothing |
| Task 7: Apply to platforms | Week 2-3 | Task 6 |
| Task 8: Lead tracking template | This week | Nothing |
| Task 9: Weekly review checklist | Before first Saturday session | Task 1 |
