# Developer Lead Generation & Marketing Plan

**Date:** 2026-04-05
**Approach:** Two-Track (Quick Wins + Pipeline Building)
**Goal:** First paid engagement within 2 weeks; transition to inbound/qualified leads over 4-8 weeks.

---

## Context

Russell needs paid work. He has 8+ years of full-stack experience (Go, Laravel, Vue, TypeScript), deployed projects, a blog, and open-source work. He also has lead automation infrastructure being built (northops-waaseyaa for CRM/qualification, north-cloud for signal detection), but those aren't ready to replace manual prospecting yet.

**Strategy:** Front-load manual outbound effort now. Build compounding assets in parallel. Converge on automation as northops-waaseyaa matures.

**Work type:** Anything that pays, with a preference for quick-win projects at flexible rates to get cashflow moving, while pursuing higher-value contracts in parallel.

---

## Track 1: Immediate Outbound (Quick Wins)

### Channels

| Channel | Type | Action |
|---------|------|--------|
| Facebook dev groups (3-4 groups) | Post + respond | "Available for hire" posts + reply to job posts |
| Discord servers (2-3 servers) | Post + engage | #for-hire channels + participate in general chat for credibility |
| Reddit r/forhire | Post | Monthly [FOR HIRE] post |
| LinkedIn | Profile + posts | Optimize headline, post 2-3x/week about what you're building |
| Upwork | Profile + proposals | Set up profile, send 5-10 proposals/week on relevant gigs |

### Posting Template (adapt per channel)

- Who you are: Full-stack developer, 8+ years
- Stack: Go, Laravel, Vue, TypeScript, AI-augmented workflow
- What you do: APIs, web apps, data pipelines, DevOps
- Availability: Immediate, remote
- Link: GitHub + portfolio/blog

### Cadence

- **Daily 30-60 min block:** Scan channels, respond to posts, send proposals
- **Weekly:** One new "available" post in each Facebook group (most groups limit frequency)
- Track which posts/responses get engagement

---

## Track 2: Pipeline Building (Compounding Investment)

### Profile Polish (Week 1-2, parallel with Track 1)

| Asset | Action |
|-------|--------|
| GitHub profile README | Add a clear "Available for hire" section with stack + services |
| Blog | Add 2-3 project case studies with outcomes |
| LinkedIn | Rewrite headline, add "Open to Work", post consistently |
| Portfolio pieces | Screenshot + brief writeup for each deployed app, link from all profiles |

### Platform Applications (Week 2-3)

- Apply to **Toptal** (premium rates once vetted)
- Apply to **Contra** (commission-free, growing)
- Apply to **Gun.io** or **Lemon.io** (vetted dev marketplaces)

### Weekly Prospecting Block

- One **90-minute calendar block** per week dedicated to lead gen
- Agenda: review what converted last week, refresh posts, send 3-5 personalized outreach messages to startups/agencies, update tracking

### Integration with northops-waaseyaa

- As northops-waaseyaa matures, leads from manual channels get entered into the CRM
- Signal-crawler in north-cloud can eventually be pointed at job boards and Facebook groups for automated lead discovery
- Goal: manual daily scanning gradually gets replaced by automated signals feeding into the pipeline

### Content as Lead Gen

- Repurpose blog posts and Substack content as LinkedIn posts (content-mine workflow already surfaces this)
- "Building in public" posts about Waaseyaa, north-cloud, etc. attract inbound interest

---

## Coordination and Scheduling

### Calendar Blocks

| Block | When | Duration | Purpose |
|-------|------|----------|---------|
| Daily lead scan | Morning, after standup | 30-60 min | Scan channels, respond to posts, send proposals |
| Weekly prospecting | Pick one day (Monday or Friday suggested) | 90 min | Outreach, post refresh, review what's working, platform applications |
| Weekly content post | Tied to existing content pipeline | 30 min | Repurpose one piece for LinkedIn/social |

### GitHub Coordination

Track in `jonesrussell/jonesrussell` repo using issues and milestones:

**Milestones:**
- **Lead Gen Launch** (Week 1-2): Join channels, first posts, profile polish
- **Pipeline Maturity** (Week 3-6): Platform applications, northops integration, refine what converts
- **Steady State** (Week 6+): Reduce manual effort, lean on automation and inbound

**Issue labels:**
- `lead-gen` for tracking tasks
- `channel:{facebook,discord,linkedin,reddit,upwork}` for channel-specific tasks
- `lead` for actual opportunities/prospects (until northops-waaseyaa takes over)

### Relationship to Existing Work

- **northops-waaseyaa:** Continues in parallel; eventual destination for all leads
- **north-cloud signal-crawler:** Future automation layer, not a dependency for starting
- **Content pipeline (this repo):** Already feeds social posting; lead gen posts are a new content type in that same flow

### Success Metrics (track weekly)

- Posts made / responses sent
- Replies/conversations started
- Proposals submitted (Upwork etc.)
- First paid engagement
- Revenue per channel (once data exists)

---

## Channel Playbook

### Facebook Groups

- Join 3-4 active groups (developer hiring, freelance dev, remote work)
- Read group rules first: most limit self-promotion to specific days or threads
- "Available" posts: short, specific, include one portfolio link. No walls of text.
- Responding to "looking for a dev" posts: lead with relevant experience to their specific need. Ask one clarifying question to start a conversation.

### Discord Servers

- Join 2-3 with active #for-hire or #jobs channels
- Participate in general/help channels for a few days before posting in hire channels
- Keep server profile/bio updated with stack + availability

### Reddit

- r/forhire: one [FOR HIRE] post per month (rule enforced)
- Title format: `[FOR HIRE] Go/Laravel/Vue Full-Stack Dev | 8+ Years | Remote | APIs, Web Apps, Data Pipelines`
- Body: 3-4 bullet points of what you do, link to portfolio, rate range optional

### LinkedIn

- Headline: "Full-Stack Developer | Go, Laravel, Vue | Available for Contract Work"
- Turn on "Open to Work" (visible to recruiters or everyone, your call)
- Post 2-3x/week: what you're building, technical insights, project wins
- Direct outreach: personalized messages to CTOs/founders at 10-50 person companies

### Upwork

- Profile optimization matters more than proposal volume
- Niche down in profile
- First 2-3 jobs: compete on proposal quality, accept slightly lower rate to build reviews
- Once you have 3-5 five-star reviews, rates go up significantly

### General Rules

- Adapt the pitch to the audience (Laravel group gets Laravel emphasis, startup Discord gets full-stack + AI angle)
- Respond within the first hour when possible; early responses win
- Track which channels produce conversations vs. silence
