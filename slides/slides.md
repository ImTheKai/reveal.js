### Modernizing Postgres Communication with Hackorum

<hr>
<p>Zsolt Parragi · <a href="mailto:zsolt.parragi@percona.com">zsolt.parragi@percona.com</a></p>
<p>Kai Wagner · <a href="mailto:kai.wagner@percona.com">kai.wagner@percona.com</a></p>
<p style="font-size: 0.7em;">March 27th, 2026 · Online</p>

---

## Who are we?

* **Zsolt Parragi** · Staff Software Engineer at Percona
  * Joined Percona as a software developer in 2017 and has been working on Percona’s database products ever since 
  * Initially focusing on MySQL and later switching to PostgreSQL
  * Likes to focus on things that make life easier and safer: encryption, authentication, extensibility, testing, and tooling.

--

* **Kai Wagner** · Senior Engineering Manager at Percona
  * I "bleed" open and I do work with and in Open Source for about 17y now. 
  * I worked on a variaty of open source projects, including Ceph and the a hardened Linux Kernel at SUSE.
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
  <li>Multi Mailinglist Support</li>
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
* ~~**Lazy Loading** - for the messages~~
* **Notification system** - get pinged on patches you care about (Like Slack/GitHub)
* ~~**More lists** - `pgsql-general`, `pgsql-docs`~~
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

**kai.wagner@percona.com** / zsolt.parragi@percona.com · [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)

---
<img src="img/pgconf_de_2026_final.png" width="40%" height="40%" style="background:none; border:none; box-shadow:none;"><br> April 21-22 in Essen, Germany
