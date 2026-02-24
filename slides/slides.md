### Modernizing Postgres Communication with Hackorum

<hr>
<p>Kai Wagner · <a href="mailto:kai.wagner@percona.com">kai.wagner@percona.com</a></p>
<p style="font-size: 0.7em;">PostgreSQL Berlin Meetup · March 5th, 2026 · Zalando BHW</p>

---

## Who am I?

* **Kai Wagner** · Senior Engineering Manager at Percona
 * I "bleed" open and I do work with and in Open Source for about 17y now. 
 * I worked on a variaty of open source projects, including Ceph and the Linux Kernel at SUSE.
 * I'm a licensed handball coach for over 20y as well as an agility and movement coach for kids

---
### I joined the Postgres fun in 2022

<img src="img/postgres-github-search.png" style="background:none; border:none; box-shadow:none;">

--
### Where are the issues and PRs?
<img src="img/postgres-github.png" style="background:none; border:none; box-shadow:none;">

--
### I'm confused! How do I contribute?
<img src="img/how-to-contribute.png" style="background:none; border:none; box-shadow:none;">

--
### Back to the roots! Mailing lists!
<img src="img/postgres-mailinglists.png" style="background:none; border:none; box-shadow:none;">

--
### There are....54 active ML's!?
<img src="img/overview-mailinglists.png" style="background:none; border:none; box-shadow:none;">

--
### This is a joke, right?
<img src="img/unread-emails.png" width="70%" height="70%" style="background:none; border:none; box-shadow:none;">

--
### Can I request a 30h workday somehow?
<img src="img/large-threads.png" style="background:none; border:none; box-shadow:none;">

<img src="img/very-large-threads.png" style="background:none; border:none; box-shadow:none;">

---

### The PostgreSQL mailing lists are the heartbeat of development.

* `pgsql-hackers` - where PostgreSQL is actually built
* `pgsql-general`, `pgsql-docs`, `pgsql-bugs`
* **Almost 30 years of institutional knowledge** living in your inbox (yes since 1997)

> *"If it wasn't on -hackers, it didn't happen."*

--

### The Firehose Problem

<img src="img/messages-count-per-month.png" style="background:none; border:none; box-shadow:none;">

* **pgsql-hackers:** 50–100+ messages *per day* (only on -hackers)
* Complex patches generate threads with **200–500+ messages**
* Multiple parallel discussions referencing each other

--

## Pain Points 

* **Context switching**: patch discussion ↔ commitfest ↔ CI
* **Lost threads**: "where was that discussion about logical replication locking?"
* **Barrier to entry**: new contributors don't know where to start
* **No collaboration layer**: teams can't annotate, tag, or track threads together
* **Search is terrible**: archive search is keyword-only, no boolean logic

--

## Why We Can't Just Replace Email

* **Decentralized by design** - no corporate single point of failure
* **Almost 30 years of archival history** fully searchable
* **Neutral ground** - no vendor walled garden
* **Established contributor culture** and workflow expectations

> The goal: **evolve the interface, not the protocol**

> Email is the source of truth. Hackorum is the lens.

---
Introducing [Hackorum](https://hackorum.dev)

<img src="img/hackorum-landingpage.png" data-preview-image width="100%" height="100%" style="background:none; border:none; box-shadow:none;">

* **Forum-style UX** on top of the mailing lists

--
<!-- .slide: data-transition="slide" -->
<h3>Main features</h3>
<br>
<ul>
  <li>Visualized complex conversations without losing your mind</li>
  <li>Commitfest Integration</li>
  <li>Contributor Profiles</li>
  <li>Patch Management</li>
  <li>Read Status</li>
  <li>Starring/Tagging/Mentions/Notifications</li>
  <li>Team Support</li>
  <li>Stats and Insights</li>
  <li>Import of read status and tags via CSV</li>
  <li>Mobile support</li>
</ul>

<br><br>

<!-- .slide: data-transition="fade-in fade-out" -->
🔴 LIVE DEMO of <a href="https://hackorum.dev" target="_blank">hackorum.dev</a>

---

Did you have network issues? Click here!

<a href="#/backup-slides">Backup Slides</a>

... otherwise we can go on :-)

---

### What We Learned 

-- 

### Almost 30 Years of Email is Chaos

Modern standards don't apply to legacy archives. Replies arrive out of order, headers are missing (thanks for such great email clients in 2026), and some email clients marking all attachements as octet-stream...

-- 

### The Rails 8 Surprise

After skipping several versions, the "out of the box" experience (Turbo, etc.) is a massive productivity boost for non-web devs.

-- 

### Normalization is Too Slow

We tried for a "normalized" DB, but a feature-rich UI on a large dataset requires denormalization or caching for fast loads.

-- 

### Agents are Force Multipliers

Coding agents have evolved rapidly and they are a speedup/help for modern web development.

> I still hate CSS ;-)

-- 

### The "POC" Gap

There is a massive difference between a "working demo" and a UI that actually handles the high-velocity activity of hackers.

---

## Roadmap

* **Email reply from Hackorum** - close the loop (send replies back to the list)
* **Lazy Loading** - for the messages
* **Notification system** - get pinged on patches you care about (Like Slack/GitHub)
* **More lists** - `pgsql-general`, `pgsql-docs` 
* **Git history parsing** - to collect merge info, to link to the actual commit in the thread

---

## Get Involved

* **Use it:** [hackorum.dev](https://hackorum.dev)
* **Code:** [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)
* **Issues / Feature requests:** [GitHub Issues](https://github.com/hackorum-dev/hackorum/issues)
* **Feedback/Conversation:** [PostgreSQL Hacking Discord](https://discordapp.com/channels/1258108670710124574/1471524461374083186)
<img src="img/hackorum-discord.png" data-preview-image width="70%" height="70%" style="background:none; border:none; box-shadow:none;">
<img src="img/hackorum-usefulness.png" data-preview-image width="100%" height="100%" style="background:none; border:none; box-shadow:none;">

---

# Questions?

### Find me after the talk or online:

**kai.wagner@percona.com** · [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)

*Slides: [https://imthekai.github.io/pgmeetup-berlin-march-2026/](https://imthekai.github.io/pgmeetup-berlin-march-2026/)*

---
<img src="img/pgconf_de_2026_final.png" width="40%" height="40%" style="background:none; border:none; box-shadow:none;"><br> April 21-22 in Essen, Germany

---
<div id="backup-slides"></div>
<br><br><br><br><br><br>

# Backup Slides :-)

---

### Feature Tour: Forum-Style Threads

<img src="img/hackorum-topic-view.png" data-preview-image width="35%" height="35%" style="background:none; border:none; box-shadow:none;">
<img src="img/hackorum-thread-view.png" data-preview-image width="25%" height="25%" style="background:none; border:none; box-shadow:none;">

* Each mailing list thread = one **Topic**
* Messages displayed as nested threads (not flat chronological)
* **Per-message read tracking** - come back, pick up exactly where you left
* Thread merge for when discussions split/recombine

---

### Feature Tour: Commitfest Integration

<img src="img/hackorum-commitfest.png" data-preview-image width="40%" height="40%" style="background:none; border:none; box-shadow:none;">

* **Live sync** with commitfest.postgresql.org (one a day)
* Patch status inline with the thread discussion:
  * `Ready for Committer` · `Needs Review` · `Committed` · `Rejected`
* CI scores + CI status visible per patch
* Reviewer and committer attribution
* Direct links from patch → discussion thread → commitfest

---

### Feature Tour: Advanced Search

<img src="img/filter-andres-100-messages.png" data-preview-image width="50%" height="50%" style="background:none; border:none; box-shadow:none;">

* Full **boolean search**: `AND`, `OR`, `NOT`
* Field-specific queries:
  `from:andres[messages:>=100] has:patch` 
  -> (More than 100 messages from Andres and has a patch attached)
* Filter by contributor tier, message count, participant count

---

### Feature Tour: Teams & Collaboration

<img src="img/teams-notes-mentions.png" data-preview-image width="80%" height="80%" style="background:none; border:none; box-shadow:none;">

* **Teams** with private/public/open visibility
* Shared **notes** per topic - annotate discussions for your team
* `@mention` teammates and teams inside notes
* Note visibility scoped: author, mentioned users, mentioned teams
* Great for review assignments, patch tracking, onboarding

---

### Feature Tour: Contributor Profiles

<img src="img/contributor-profile.png" data-preview-image width="60%" height="60%" style="background:none; border:none; box-shadow:none;">

* **6-tier contributor hierarchy:**
  * Core Team · Committer · Major Contributor · Significant Contributor
  * Past Major or Significant Contributor
* Person identity resolution across **multiple email aliases**
* Per-alias send counts 

---

## Under The Hood: Tech Stack

```
┌──────────────────────────────────────────────┐
│  Rails 8.0.2 · Ruby 3.4.4 · Hotwire/Turbo    │
│  Propshaft · ImportMap · Slim templates      │
├──────────────────────────────────────────────┤
│  PostgreSQL 18   (primary + 3 side DBs)      │
│  Solid Queue  ·  Solid Cache  ·  Solid Cable │
├──────────────────────────────────────────────┤
│  IMAP IDLE  →  EmailIngestor  →  PG          │
│  Commitfest HTTP poller → PG                 │
├──────────────────────────────────────────────┤
│  Kamal · Docker · Caddy · PgHero             │
└──────────────────────────────────────────────┘
```

**No Redis. No Elasticsearch. No Sidekiq. All PostgreSQL.**

---

## Deep Dive: Person Identity Resolution

```
Email Alias A (kai@example.com)  ─┐
Email Alias B (kai@percona.com)  ─┼── Person #42 (Kai Wagner)
Email Alias C (kaiwo@github.com) ─┘
     │
     └── Contributor Membership → tier: :committer
```

```ruby
# PersonIdPropagationJob: runs when alias → person assignment changes
class PersonIdPropagationJob < ApplicationJob
  def perform(person_id, old_person_id)
    ActiveRecord::Base.transaction do
      Message.where(sender_person_id: old_person_id)
             .update_all(sender_person_id: person_id)
      TopicParticipant.where(person_id: old_person_id)
                      .update_all(person_id: person_id)
      # cleanup orphaned person record
      Person.find(old_person_id).destroy if old_person_id
    end
  end
end
```

* One person, many aliases - deduplicated at query time and at ingest
* Merge is atomic - background job, single transaction
* Affects contributor tier computation and search filters

---

### Observability: PgHero + Rails Pulse

<img src="img/pghero.png" data-preview-image width="50%" height="50%" style="background:none; border:none; box-shadow:none;">

* **PgHero** - mounted at `/admin/pghero`
  * Slow query detection via `pg_stat_statements`
  * Index hit rates and bloat estimates
  * Live connection monitoring
* **Rails Pulse** - real-time performance monitoring dashboard

---

### Deployment: Kamal + Docker

```yaml
# deploy/config.yml (simplified)
service: hackorum
image: hackorum-dev/hackorum

servers:
  web:
    hosts: [production-host]
    cmd: bundle exec puma -C config/puma.rb

accessories:
  db:
    image: postgres:18
    volumes: [/data/postgres:/var/lib/postgresql/data]
  caddy:
    image: caddy:2
    volumes: [./Caddyfile:/etc/caddy/Caddyfile]
  backups:
    image: prodrigestivill/postgres-backup-local
```

* **Kamal** handles zero-downtime deploys (blue/green containers)
* Postgres 18 in Docker with volume-mounted data
* Caddy as reverse proxy with automatic TLS
* Automated PG backups via sidecar container
* `pg_stat_statements` preloaded via Docker init script

---

### What We Learned 

-- 

### Almost 30 Years of Email is Chaos

Modern standards don't apply to legacy archives. Replies arrive out of order, headers are missing (thanks for such great email clients in 2026), and some spam filters marking all attachements as octet-stream...

-- 

### The Rails 8 Surprise

After skipping several versions, the "out of the box" experience (Turbo, etc.) is a massive productivity boost for non-web devs.

-- 

### Normalization is Too Slow

We tried for a "normalized" DB, but a feature-rich UI on a large dataset requires denormalization and caching for fast loads.

-- 

### Agents are Force Multipliers

Coding agents have evolved rapidly and they are a speedup/help for modern web development.

> I still hate CSS ;-)

-- 

### The "POC" Gap

There is a massive difference between a "working demo" and a UI that actually handles the high-velocity activity of hackers.

---

## Roadmap

* **Email reply from Hackorum** - close the loop (send replies back to the list)
* **Lazy Loading** - for the messages
* **Notification system** - get pinged on patches you care about (Like Slack/GitHub)
* **More lists** - `pgsql-general`, `pgsql-docs` 
* **Git history parsing** - to collect merge info, to link to the actual commit in the thread

---

## Get Involved

* **Use it:** [hackorum.dev](https://hackorum.dev)
* **Code:** [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)
* **Issues / Feature requests:** [GitHub Issues](https://github.com/hackorum-dev/hackorum/issues)
* **Feedback/Conversation:** [PostgreSQL Hacking Discord](https://discordapp.com/channels/1258108670710124574/1471524461374083186)
<img src="img/hackorum-discord.png" data-preview-image width="70%" height="70%" style="background:none; border:none; box-shadow:none;">
<img src="img/hackorum-usefulness.png" data-preview-image width="100%" height="100%" style="background:none; border:none; box-shadow:none;">

---

# Questions?

### Find me after the talk or online:

**kai.wagner@percona.com** · [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)

*Slides: [https://imthekai.github.io/pgmeetup-berlin-march-2026/](https://imthekai.github.io/pgmeetup-berlin-march-2026/)*
