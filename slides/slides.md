<style>
.highlight-box {
  border: 2px solid #653df4;
  background: rgba(101, 61, 244, 0.10);
  padding: 18px;
  border-radius: 10px;
  margin-top: 14px;
}

.warning-box {
  border: 2px solid #ff4444;
  background: rgba(255, 68, 68, 0.15);
  padding: 18px;
  border-radius: 10px;
  margin-top: 14px;
}

.title-slide h2 {
  max-width: none;
  line-height: 1.1;
}

.speakers {
  color: #653df4;
  font-weight: 700;
  font-size: 1.05em;
  margin-top: 1.5em;
}

.speakers .org {
  color: #8a8a95;
  font-weight: 400;
  font-size: 0.78em;
}

.venue {
  font-size: 0.66em;
  color: #6b6b75;
  margin-top: 0.3em;
}

/* keep headings clear of the QR code in the top-right corner */
.reveal h1,
.reveal h2,
.reveal h3 {
  max-width: 1450px;
  margin-left: auto;
  margin-right: auto;
}

.cols {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 50px;
}

.cols ul {
  text-align: left;
}

.table {
  font-size: 0.7em;
}

.table table {
  width: 94%;
  margin: 0 auto;
  table-layout: fixed;
}

.table th,
.table td {
  padding: 10px 12px;
  vertical-align: top;
  word-break: break-word;
}
</style>
<!-- .slide: class="title-slide" -->

## Managing the Postgres<br>Developer Firehose

### with hackorum.dev

Making 30 years of mailing list actually usable.

<p class="speakers">Kai Wagner <span class="org">Percona</span></p>
<p class="venue">Barcelona (+Valencia) PostgreSQL User Group &middot; Valencia &middot; October 19th 2026</p>

Note:

* Good evening Valencia. (~0:30)
* Who here is subscribed to pgsql-hackers? Keep your hand up if you read every message from last week.
* Nobody. That is not a personal failing, it is a structural one. That is the next fifteen minutes.
---

## Who am I - and who built it

<div class="cols">

<img src="img/hk-zsolt.png" style="height:260px; width:auto; background:none; border:none; box-shadow:none;">

* **Kai Wagner** - Percona
    * ~17y open source: Ceph, Linux kernel, Postgres
* **Zsolt Parragi** - Percona, [`@dutow`](https://github.com/dutow)
    * Idea: **PGConf.dev 2025** unconference
    * First commit **9 Dec 2025**
    * 279 of 378 commits

</div>

> He built it. I mostly filed issues and complained about CSS :-)

Note:

* (~1:00) I am not a Postgres hacker by trade. Ceph, the kernel, seventeen years of open source. I remember being confused by this project, because it was not long ago.
* Credit first: Zsolt. At the PGConf.dev 2025 unconference, in the session on scaling Postgres development, he asked why nobody had built this yet. Then he built it. The December first commit is twelve thousand lines, the whole initial development squashed into one.
* This is a side project, not a Percona product.
---

## I joined the Postgres fun in 2022

<img src="img/postgres-github.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* (~0:30) 2022, new to Postgres, I go to GitHub like everyone else.
* Zero issues. Zero pull requests. For anyone who grew up on GitHub, that reads as a dead project.
* The docs are good and honest, and they tell you to send an email.
--

## There are... 54 active lists!?

<img src="img/overview-mailinglists.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* (~0:30) Mailing lists. Fine. Fifty-four of them.
* Which one? -hackers obviously, but -bugs? -general? -patches? Nobody tells you. You learn it by being wrong in public.
--

## This is a joke, right?

<img src="img/unread-emails.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* (~0:20) I subscribed to one list. This is my mailbox after a holiday.
--

## The same thread, twice

<div class="cols">

<img src="img/mailclient-thread.png" data-preview-image style="width:870px; height:auto; background:none; border:none; box-shadow:none;">

<img src="img/hk-thread-compare.png" data-preview-image style="width:870px; height:auto; background:none; border:none; box-shadow:none;">

</div>

**504 messages. 503 of them called "Re: index prefetching". 21 people. Three years.**

Note:

* (~1:30) Left: that thread in a mail client. Right: the same thread in Hackorum. Same messages, same archive.
* Real senders, real dates. Five hundred and four messages, five hundred and three with the identical subject. Started June 2023, still going.
* Where is the objection that changed the design? Let the silence answer.
* On the right, the reply structure recovered from headers that were in the mail all along.
* If you remember one slide from tonight, remember this one.
--

## The firehose, in numbers

<img src="img/hk-report-monthly.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

**August 2026 alone:** 3,076 messages &middot; 278 active people &middot; 364 new threads &middot; 47 newcomers

> That is a message **every 14 minutes**, day and night, for a month.
<!-- .element: class="fragment highlight-box" -->

Note:

* (~0:45) One month. Three thousand messages. A message every fourteen minutes, around the clock. Nobody reads that.
* Forty-seven people posted for the first time. How many of them are still here in six months?
---

## The lists are not the problem

* `pgsql-hackers` is where PostgreSQL is actually built - **since 1997**
* **Decentralised**, **vendor-neutral**, ~30 years of archive, a contributor culture that works
* The only interface anyone ships for it is... an email client

> The goal: **evolve the interface, not the protocol.**
> Email stays the source of truth. Hackorum is the lens.
<!-- .element: class="fragment highlight-box" -->

Note:

* (~1:00) Very clear on this: the lists are the heartbeat of the project, not a legacy mistake.
* Every few years someone proposes GitHub or Discourse, and the answer is no, correctly.
* So we did not build a replacement. Every message in Hackorum is a real list message. If Hackorum disappears tomorrow, nothing happens to the archive. Strictly additive.
---

# Hackorum

<img src="img/hk-landing.png" data-preview-image style="height:760px; width:auto; background:none; border:none; box-shadow:none;">

<a href="https://hackorum.dev">hackorum.dev</a>

Note:

* (~0:45) A forum-style interface on top of the PostgreSQL mailing lists. One thread is one topic.
* Icons under each title are state: patch, CI, notes, partially read.
* Six lists on the left, saved searches below. Remember "Patch, no replies", it comes back.
* The QR code in the corner goes here, if you want to follow along.
--

## What Hackorum gives you

* **Read** - threads as conversations, a branch outline, per-message read state
* **Find** - a real query language, saved searches, 30 years of archive
* **Track** - commitfest status, patchset versions, reviewers, commits, back-ports
* **Test** - CI on every patch, and a Docker image to try one in 90 seconds
* **Collaborate** - teams, shared notes, `@mentions` and `#tags`
* **Reply** - send to the list from the UI, with correct headers

> Six mailing lists. One account. Your mail client keeps working.

Note:

* (~0:45) The map for the rest of the talk. I will show four of these; the rest are in the backup slides if you ask.
--

## The shape of a 501-message argument

<div class="cols">

<img src="img/hk-thread-outline.png" data-preview-image style="height:600px; width:auto; flex-shrink:0; background:none; border:none; box-shadow:none;">

* Reply branches from `In-Reply-To`
* *"#5...#20 to Tomas Vondra"*:<br>a sub-debate, read or skip
* Per-message read state

</div>

Note:

* (~1:00) Email is flat and chronological. Technical arguments branch.
* Somebody objects at message four, three people argue for fifteen messages, the main line carries on.
* The outline recovers that shape and lets you collapse what you do not care about. Zsolt still wants to rework this view, but even as it is, it shows the difference.
* Read state is per message, not per thread. On five hundred messages, unread-yes-or-no is useless.
--

## Search that is actually a query language

<img src="img/hk-search.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

```
from:andres[messages:>=10] has:patch
```

Note:

* (~0:45) Boolean logic, field selectors, dependent conditions.
* With the brackets: Andres himself posted ten or more messages in the thread. Without them: Andres posted, and the thread has ten messages from anyone. Different question.
* has:patch, unread:me, from:committer, commitfest status, dates. And you can save any of them.
--

## My favourite screen in the whole product

```
has:patch messages:1 first_after:6m
```

<img src="img/hk-newcomer.png" data-preview-image style="height:490px; width:auto; background:none; border:none; box-shadow:none;">

> **124** of the **1,450** patch threads started in the last six months have never had a reply &mdash; **one in twelve**.
> All time: **1,279**.
<!-- .element: class="fragment warning-box" -->

Note:

* (~1:30) Who here has sent a patch to a list and never heard anything back? This is that list.
* Every thread from the last six months with a patch and exactly one message. Nobody said anything at all.
* Somebody wrote each of those, tested it, wrote a cover letter, and refreshed their inbox for a week.
* Nobody's fault; reviewer time is the scarcest resource. But you cannot fix a queue you cannot see.
* One in twelve. It ships as a global saved search, "Patch, no replies". If you take one URL home tonight, take that one.
---

## Every patch, built and tested

```bash
docker run --rm -p 5432:5432 ghcr.io/hackorum-dev/postgres-patch:t47973
psql -h localhost -U postgres
```

<img src="img/hk-ci-banner.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* (~1:00) Not just commitfest entries, every patch posted to the lists. Around seventeen hundred CI runs a day.
* We pick the base commit, apply, build, run the tests, and keep rebasing as master moves.
* And every patch becomes a Docker image. That line is a running Postgres built from that thread's latest patch. No checkout, no toolchain.
* "Could you try this?" used to cost an afternoon. Now it is a Docker pull. Try it on the train home.
* It is our own CI, marked beta, and it does less than cfbot: one Linux job per patchset, where the commitfest CI runs ten. The point is breadth, not depth.
--

## Reply to the list, from Hackorum

<img src="img/hk-composer.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* (~0:45) The loop closes. Write a reply in Hackorum and it goes to the real list, from your own address, with correct In-Reply-To and References.
* Confirmation before sending, and we do not call it sent until the list echoes it back.
* Plus teams and shared notes on threads, with at-mentions and tags. That is the collaboration layer email never had.
---

## What's next? We don't know yet

* **AI thread summaries** - re-entry into a 500-message thread. But who is accountable when a summary is wrong?
<!-- .element: class="fragment" -->
* **Contributor profiles** - we already resolve aliases and compute commit credits by role. Integrate with the community effort, don't duplicate it
<!-- .element: class="fragment" -->
* **Bug tracking from threads** - a thread already *is* an issue. Missing: state. **Who sets it?**
<!-- .element: class="fragment" -->
* **Topic grouping** - AIO, logical replication: dozens of threads, found today by remembering they exist
<!-- .element: class="fragment" -->

> What must **never** change, no matter how nice the UI gets?
<!-- .element: class="fragment highlight-box" -->

Note:

* (~1:30) Open questions, not a roadmap.
* Summaries: the risk is putting words in a committer's mouth at scale. Every claim must link to a message.
* Profiles: two half-good datasets that disagree would be the worst outcome.
* Bug tracking: if anyone can set state it is meaningless, if only committers can we made more work for the busiest people. And reporting a bug must never need a login.
* Grouping: same question, differently dressed. Automatic or curated, and curated by whom?
* The last one is what I most want answered by people who have been around for twenty years.
* All of this is on the table at PGConf.EU this week: our talk Thursday morning and a Hackorum session at Friday's Community Events Day.
--

## People are actually using it

<img src="img/quote-david-steele.png" data-preview-image style="width:1150px; height:auto; background:none; border:none; box-shadow:none;">

<img src="img/hackorum-discord.png" data-preview-image style="width:1150px; height:auto; background:none; border:none; box-shadow:none;">

<img src="img/hackorum-usefulness.png" data-preview-image style="width:1700px; height:auto; background:none; border:none; box-shadow:none;">

*&mdash; Andrey Borodin, on `pgsql-hackers`*

Note:

* (~0:40) All Postgres contributors, none of them asked for a quote.
* David Steele: a pinned tab, following hackers without losing his mind.
* Christoph Berg set up the hackorum channel on the PostgreSQL Hacking Discord when we asked.
* Andrey Borodin apologising for bumping a thread that was exactly ten years old, which he only knew because Hackorum told him.
---

# Questions?

* **Use it:** [hackorum.dev](https://hackorum.dev) &middot; **Code:** [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)
* **Chat:** [PostgreSQL Hacking Discord](https://discordapp.com/channels/1258108670710124574/1471524461374083186) &middot; **Dumps:** [dumps.hackorum.dev](https://dumps.hackorum.dev)
* **kai.wagner@percona.com**

### PGConf.EU this week: Thursday talk &middot; Friday Community Events Day

Note:

* (~0:20, then 5 min Q&A)
* If you do one thing: sign in and set your read state.
* Likely questions:
    * Replace the lists? No, and the architecture makes it impossible. Every message is a real list message.
    * Who pays? Percona sponsors development and hosting today, which is why the governance question matters.
    * postgresql.org archives? Untouched. We consume, never write.
    * Delete my data? Delete-account flow exists; the list archive is not ours to delete from.
    * Why not fix the commitfest app? It tracks patches; this tracks conversations, most of which never become a CF entry.
    * Self-host? Docker Compose, Postgres 18, seeded from the public dumps.
    * Stack? Rails 8, and Postgres for search, queue and cache. See backup slides.
---

<div id="backup-slides"></div>

# Backup slides :-)

Note:

* Everything past here is for a question that deserves a picture.
--

## Backup: Where it actually hurts

* **Context switching**: patch discussion &harr; commitfest &harr; CI &harr; git log
<!-- .element: class="fragment" -->
* **Lost threads**: *"where was that discussion about logical replication locking?"*
<!-- .element: class="fragment" -->
* **Barrier to entry**: newcomers don't know where to start - or whether anyone read their patch
<!-- .element: class="fragment" -->
* **No collaboration layer**: teams can't annotate, tag, or track threads together
<!-- .element: class="fragment" -->
* **Search**: keyword-only, no boolean logic, no "show me patches nobody replied to"
<!-- .element: class="fragment" -->

Note:

* To review one patch today you need the thread in your mail client, the commitfest entry in a browser tab, the CI result in a third tab, and a local checkout to apply it.
* Four systems, zero links between them. Four opportunities to give up.
* And there is no collaboration layer at all. If you and a colleague both want to track the same patch, your only option is forwarding each other emails.
--

## Backup: Hackorum in 90 seconds

<video data-autoplay muted playsinline controls
       src="img/hackorum-walkthrough.webm"
       style="height:790px; width:auto; background:none; border:none; box-shadow:none;"></video>

<p class="venue"><a href="#/backup-slides">Backup slides</a> &middot; <a href="https://hackorum.dev">hackorum.dev</a></p>

Note:

* 0:00 Every thread on six mailing lists, as a conversation. The icons are state. Patch, CI, notes, unread.
* 0:12 A saved search. Every one of these has a patch and nobody has answered. Anyone can use it.
* 0:24 One thread. Index prefetching. Five hundred and four messages over three years.
* 0:36 The thread outline. That structure was in the mail headers all along. Nobody was showing it to you.
* 0:48 CI on every patch, and that docker line gives you a running Postgres built from this patch.
* 0:56 Search is a real query language. Andres, ten or more messages of his own, in threads with a patch.
* 1:04 Shared notes on a thread, with at-mentions and hash-tags your team can search.
* 1:12 And you can answer the list from here. Your address, correct headers, real mail.
* 1:20 Thousands of patch builds a day.
* 1:28 That is hackorum.dev. It is open, go and break it.
--

## Backup: One thread = one Topic

<img src="img/hk-thread.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Open a topic and you get everything about that conversation in one place.
* Down the left rail: CI status. The commitfest entry with its state, here "waiting on author", and its tags. The named reviewers. The participants, with their contributor tier as a small badge. The attachments, including a one-click download of the latest patchset.
* You did not open four tabs. You opened one page.
--

## Backup: Read state that survives closing your laptop

* **Per-message** read tracking - not per-thread
* Come back in three weeks, pick up at exactly the right message
* "Jump to unread" &middot; "Mark all read" &middot; "Collapse all"
* **Ignore a thread** so it stops shouting at you
* Import your existing read state from CSV

Note:

* Small feature, enormous difference.
* It is what turns "I'll catch up on -hackers this weekend" from a fantasy into a plan.
* Per-message, not per-thread, is the key detail. On a five-hundred-message thread, unread as a yes-or-no is useless.
* And you can ignore a thread entirely. Sometimes the healthiest thing you can do for a mailing list relationship is to mute one argument. No judgement.
--

## Backup: Commitfest, reviewers and patchsets, inline

<div class="cols">

<img src="img/hk-patchsets.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

* **Daily** sync with **commitfest.postgresql.org**, status inline
* Commitfest tags, reviewer and committer attribution
* Every **patchset version** in the thread, with diffstat and one-click download

</div>

Note:

* The commitfest app and the mailing list have always been two halves of the same conversation that could not see each other. We sync them once a day.
* Patchsets are the other half. A long thread might carry twenty-five versions of a patch, scattered across two years of messages.
* We detect which messages are patch submissions, group them into versions, and show you a v1 to v25 history with diffstats.
* You can answer "what did v12 look like" in about four seconds.
--

## Backup: We build and test every patch on the list

<img src="img/hk-ci-dashboard.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Not every commitfest submission. Every patch posted to the lists.
* Six thousand three hundred tracked patchsets, seventeen hundred CI runs in the last twenty-four hours, twenty-two in flight right now.
* For each patchset we work out the right base commit, apply it, build it, run the full test suite, and keep rebasing it as master moves.
* Applies, needs rebase, base too old, tests failed. All of it visible, all of it public.
* This is our own CI, not the project's, and it is explicitly marked beta.
* And it does less than cfbot. We run one single Linux job per patchset; the commitfest CI runs ten different ones. It is not a replacement for cfbot. It is an experiment in what happens if a basic build and test exists for everything, not just commitfest entries.
--

## Backup: Commits and threads, finally connected

<img src="img/hk-person-commits.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* We parse the entire Postgres git history and link commits back to the threads that produced them.
* Via commit trailers and Discussion links. Older commits without a proper link are simply not associated. Matching on the patch files themselves was tried, and it was too unreliable to ship.
* So a thread now tells you this landed, here is the commit, and here are the branches it was back-patched to.
* And a person shows their commit credits split by role. Author, committer, reviewer, reported-by, co-author.
* That last breakdown matters, and it comes back in a few minutes.
--

## Backup: Contributor profiles &amp; identity resolution

<img src="img/hk-person.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Twenty-seven and a half thousand messages. Three thousand commit credits. Seventeen years.
* And three email aliases, resolved into one person. That is the panel on the left.
* Identity resolution is unglamorous and absolutely essential. People change jobs, change addresses, send from their phone. Without merging aliases, every statistic you compute is wrong.
* Contributor tiers, core team, committer, major and significant contributor, are mirrored from the main postgresql.org website, and you can filter search by them.
* And look at "patch threads that landed", seventy-one percent. That is a metric nobody had before.
--

## Backup: Teams, notes, @mentions and #tags

<img src="img/hk-note.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* This is the collaboration layer that email does not have.
* Teams can be private, public or open. Inside a team you get shared notes on any topic, at-mentions of people and teams, and hash-tags that become searchable.
* Visibility is scoped properly. The author, the mentioned users, the mentioned teams. Nothing leaks.
* The use case that sold it for us internally was simply "who on our team is reviewing what, and what did we conclude last time we looked at this".
* That conversation used to live in Slack, disconnected from the thread. Now it lives on the thread.
--

## Backup: Weekly and monthly community reports

<img src="img/hk-report-weekly.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Automatically generated digests. Message volume, active people, new threads, newcomers, week over week.
* Activity rankings split by type of contribution. Started a thread, replied to their own, replied to somebody else, sent a first patch, sent a follow-up patch.
* Because "posted a hundred and thirty-nine messages" and "reviewed a hundred and thirty-nine patches" are very different things, and we should stop conflating them.
* On the left, the most active, most diverse and longest running thread of the period.
* A decent five-minute Monday morning read for what you missed.
--

## Backup: 29 years of a mailing list, as charts

<img src="img/hk-stats.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Public, no login needed. Message volume since 1997. New versus retained participants. Retention cohorts. Topic longevity.
* Some of these exist because we were curious, not because anyone asked.
* But a couple of them are genuinely uncomfortable to look at, the retention ones especially, and I think this community should be looking at them.
* If you are into community metrics, come and find me afterwards. There is a whole talk in this screen alone.
--

## Backup: It also works on the train

<img src="img/hk-mobile.png" data-preview-image style="height:400px; width:auto; background:none; border:none; box-shadow:none;">
<img src="img/hk-landing-dark.png" data-preview-image style="height:400px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Mobile, and dark mode.
* The mobile one is not a joke feature. A lot of keeping up with -hackers happens on a phone, in a queue, at an airport.
* If the only way to read the list is a desktop mail client, you have already lost those minutes.
* Dark mode is here because I was asked for it approximately nine hundred times.
--

## Backup: Idea 1 - AI summaries of threads

> *"500 messages. What happened, what was decided, what is blocking?"*

* The biggest cost of a long thread is **re-entry**
* Summaries are cheap to regenerate as the thread grows

But: a wrong summary is worse than no summary. Who is accountable when it misrepresents somebody's position?
<!-- .element: class="fragment warning-box" -->

Note:

* This is the one people ask for most often, and the one I am most cautious about.
* The use case is specific. Not "read the list for me". It is "I am about to join a four-year-old thread and I need to not re-litigate something that was settled at message sixty".
* My worry is attribution. If a summary says Tom rejected this approach, and Tom actually said something more nuanced, we have just put words in a committer's mouth at scale.
* Any implementation has to link every claim back to a specific message number, and it has to be obviously machine-generated.
* So the question for Friday is opt-in or default, and whether it needs to be visibly separated from human content the way the CI banner already is.
--

## Backup: Idea 2 - Community contributor profiles

The community is building contributor profiles right now.

* Hackorum already resolves aliases and computes commit credits by role and patch-thread landing rate
* That data belongs to the community, not to us

**We should integrate, not duplicate.** What is the right interface - an API, a dump, upstreaming the computation?
<!-- .element: class="fragment highlight-box" -->

Note:

* This is not a feature request, it is a governance question, which is why I want it discussed on Community Day rather than decided by us.
* We have accidentally built a fairly rich contributor dataset. Alias resolution, commit credits split by role, and what fraction of the patch threads somebody started actually landed.
* There is separate community-driven work on contributor profiles. The worst possible outcome is two half-good datasets that disagree with each other.
* So what do you need from us? An API? A periodic dump? Should the computation live somewhere more neutral than a Percona-sponsored side project?
* We already publish public database dumps. I genuinely do not know if that is the answer or the lazy version of it.
--

## Backup: Idea 3 - Bug and feature tracking, from threads

*The idea from PGConf.dev in Vancouver.*

A thread already **is** an issue. It has a reporter, a discussion, and sometimes a fix.

* We already link threads to patchsets, CI, commits and branches
* What's missing is **state**, and the ability to ask *"what is still broken?"*

The hard part isn't technical. It's: **who sets the state?**
<!-- .element: class="fragment warning-box" -->

Note:

* This is the big one, and it came out of the unconference discussions in Vancouver.
* Look at what a topic already has. A reporter, a discussion, attached patches, CI results, the commit that fixed it, and the branches it was back-ported to.
* That is structurally an issue tracker. We are about two fields short.
* The two fields are state and ownership, and that is exactly where it stops being a software problem.
* If anyone can set a bug to confirmed, the states are meaningless. If only committers can, we have invented more work for the people with the least time. If we derive it automatically, we are back to the accountability problem from the AI slide.
* I do not have an answer. I have a strong feeling the answer exists, and that it is a community decision rather than a product decision.
* One thing I will say out loud. Nothing here should require a bug reporter to create an account anywhere. The moment reporting a Postgres bug requires a login, we have made this project worse.
--

## Backup: Idea 4 - Topic grouping

Big work is never one thread.

* AIO. Logical replication. Incremental sort. Each is *dozens* of threads over years
* Threads split, get renamed, get resurrected two years later
* Today you find them by remembering that they exist

What if a group of threads could be a first-class thing?
<!-- .element: class="fragment highlight-box" -->

Note:

* Call it an epic, a project, a topic group. The name matters less than the idea.
* Right now the knowledge that these fourteen threads are all the same piece of work lives in the heads of maybe four people.
* When those people are on holiday, that work is effectively invisible to everyone else.
* We can already do some of this automatically. Shared patch files, shared participants, commit trailers pointing at several threads.
* The question is whether automatic grouping is good enough, or whether it needs curation, and if it is curated, by whom.
* Same question as the bug tracker, differently dressed.
--

## Backup: the topic index, in detail

<img src="img/hk-landing.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* The icons under each title, left to right: notes on this topic with a count, commitfest entry, attachment, patch submission, CI state, unread count.
* The coloured bar down the left of each row is your personal read state. New, partially read, fully read.
--

## Backup: a thread, in detail

<img src="img/hk-thread-big.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Index prefetching, five hundred and four messages.
* Note the commits panel in the left rail. This thread has already produced several commits on master and on REL_19_STABLE, each one shown with its branch badges.
--

## Backup: per-topic CI history

<img src="img/hk-ci-topic.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Per patchset: the base commit we picked, when it was applied, when it was last rebased, where it was pushed, and every CI run against it.
* A line like "v23, superseded, stale ten months, pg 19" tells you at a glance that an old version was tested against a Postgres generation that no longer matters.
--

## Backup: CI is an infrastructure problem

Building **every patch on the list** is not a feature, it's a fleet.

* Rebase every patchset every time master moves
* Per-major-version build images ("eras")
* An orchestrator deciding what is worth building next
* 11,397 runs in 7 days &middot; 84.4% success &middot; median build 2m50s

Note:

* Just running CI on the patches sounds like a weekend project. It is not.
* The hard part is not building a patch. The hard part is deciding, continuously, which of six thousand patchsets are worth a runner right now, because master moves and every patchset silently rots.
* Zsolt has been living inside this for months.
--

## Backup: CI statistics

<img src="img/hk-ci-stats.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Success rate, median build and test time, queue wait, infrastructure errors.
* The corpus tab does something slightly mad. It lays today's patchsets out over PostgreSQL's history to ask how far behind the average patch actually is.
--

## Backup: teams

<img src="img/hk-teams-settings.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Create a team, invite members, set it private, public or open, and share saved searches across the team.
--

## Backup: a team profile

<img src="img/hk-team.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* A team gets an aggregate profile. Combined messages, patches, commit credits by role, and the patch threads that landed rate.
* For us that number is forty-three percent. For an individual committer it is seventy-one.
* That gap is roughly what being new costs you, and it is the kind of thing this data can now make visible.
--

## Backup: notifications

<img src="img/hk-activities.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Activity feed for mentions, for replies on threads you participate in, and for team events.
--

## Backup: drafts and sent mail

<img src="img/hk-drafts.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Every outgoing message has a state. Draft, sending, pending, sent, failed.
* Pending means the mail was accepted but the list has not echoed it back yet. We do not claim success until we have seen the message arrive on the list like everybody else's.
* Drafts stuck in sending for more than ten minutes get reset automatically.
--

## Backup: the help pages

<img src="img/hk-help.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Search syntax and account linking.
* The search guide is worth reading even if you never use Hackorum. It is a decent taxonomy of the questions you might want to ask a mailing list.
--

## Backup: under the hood

```
+----------------------------------------------+
|  Rails 8 - Ruby 3.4 - Hotwire/Turbo - Slim   |
|  Propshaft - ImportMap - Stimulus            |
+----------------------------------------------+
|  PostgreSQL 18  (primary + side DBs)         |
|  Solid Queue  -  Solid Cache  -  Solid Cable |
+----------------------------------------------+
|  IMAP / own mailserver -> EmailIngestor -> PG|
|  Commitfest poller -> PG                     |
|  git history importer -> PG                  |
|  Patch CI orchestrator -> GitHub Actions     |
+----------------------------------------------+
|  Docker Compose - Caddy - PgHero             |
+----------------------------------------------+
```

**No Redis. No Elasticsearch. No Sidekiq. It's Postgres all the way down.**

Note:

* Why Rails in 2026? Because we are not web developers, and Rails 8 out of the box gave us queues, cache, cable and websockets without adding a single piece of infrastructure.
* Full-text search is Postgres. The job queue is Postgres. The cache is Postgres.
* We run our own mail server for list ingestion rather than depending on an IMAP label in a Gmail account, which was exactly as fragile as it sounds.
--

## Backup: identity resolution

```ruby
# kai@example.com  +
# kai.wagner@percona.com  +--> Person #42 (Kai Wagner) - tier: contributor
# kaiwo@github.com  +

# PersonIdPropagationJob: runs when an alias -> person mapping changes
class PersonIdPropagationJob < ApplicationJob
  def perform(person_id, old_person_id)
    ActiveRecord::Base.transaction do
      Message.where(sender_person_id: old_person_id)
             .update_all(sender_person_id: person_id)
      TopicParticipant.where(person_id: old_person_id)
                      .update_all(person_id: person_id)
      Person.find(old_person_id).destroy if old_person_id
    end
  end
end
```

* One person, many aliases - merged atomically in a background job
* Feeds tiers, search filters, stats and commit credits
* Admins can preview a merge before committing to it

Note:

* The preview step exists because we once merged two people who were not the same person. Once was enough.
--

## Backup: why not just a forum?

<div class="table">

| | Mailing list | Forum (Discourse) | Hackorum |
|---|---|---|---|
| Source of truth | Email | The forum DB | **Email** |
| Works if it dies | n/a | Everything is lost | **Nothing is lost** |
| Offline / your client | yes | no | **yes (still email)** |
| Threading UI | no | yes | yes |
| Search | weak | yes | yes |
| Vendor neutral | yes | depends | yes |

</div>

Note:

* The row that matters is the second one.
* If Discourse is your source of truth and Discourse goes away, thirty years of Postgres history goes with it.
* If Hackorum goes away tomorrow, absolutely nothing happens to the archive, and everybody's mail client keeps working exactly as it did.
* That asymmetry is the entire design.
