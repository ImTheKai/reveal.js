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

## Finally a Postgres<br>Communication Hub

### for Experts and Newcomers

Making 30 years of mailing list actually usable.

<p class="speakers">Jack Bonatakis <span class="org">Robin</span> &nbsp;&middot;&nbsp; Kai Wagner <span class="org">Percona</span></p>
<p class="venue">PGConf.EU 2026 &middot; Valencia &middot; October 22nd &middot; Audit 2</p>

Note:

* Good morning Valencia.
* Who here is subscribed to pgsql-hackers?
* Keep your hand up if your inbox is at zero.
* Keep it up if you have read every message from last week.
* That last one is the talk. Nobody's hand is up. That is not a personal failing, it is a structural one.
---

## Who are we?

* **Kai Wagner** - Senior Engineering Manager at Percona
    * I "bleed" open and have worked with and in Open Source for about 17y now
    * I worked on a variety of open source projects, including Ceph and the Linux Kernel at SUSE
    * I'm a licensed handball coach for over 20y as well as an agility and movement coach for kids
* **Jack Bonatakis** - Robin

> Two companies, one project.
> We are the people who got lost in the mailing lists and decided to build a map.

Note:

* I am not a Postgres hacker by trade. I came from Ceph and the Linux kernel, and I have been doing open source for about seventeen years.
* I remember exactly what it felt like to be confused by this project, because I was confused by it not long ago.
* Two companies, one side project. Jack is at Robin, I am at Percona, and this is not a Percona product.
* And yes, I am a handball coach. Twenty years of getting beginners good enough to play with the good players. That is the same problem.
---

## The brain behind Hackorum

<img src="img/hk-zsolt.png" style="height:420px; width:auto; background:none; border:none; box-shadow:none;">

* **Zsolt Parragi** - Staff Software Engineer at Percona, [`@dutow`](https://github.com/dutow)
* It started with a question at the **PGConf.dev 2025** unconference: *why has nobody built this yet?*
* First commit **9 December 2025** - and 279 of Hackorum's 378 commits since

> He built it. I mostly filed issues and complained about CSS :-)

Note:

* Before anything else, credit where it is due.
* This started at PGConf.dev 2025, in the unconference session on scaling PostgreSQL development. Zsolt asked the room why nobody had built this yet, and then spent the rest of the day talking it through with people in the hallway.
* Then he went home and built it. He and I went back and forth on the design around November. The first commit is dated the ninth of December, but it is twelve thousand lines: the whole initial development squashed into one commit. It went public on Discord at the end of December, and he has written about three quarters of the codebase since.
* This is his own profile, on the thing he built. Ninety-eight patches sent to the lists, ninety-five commit credits.
* He is not a web developer who wandered in. He is a Postgres hacker who got annoyed enough to build his own tooling.
---

## I joined the Postgres fun in 2022

<img src="img/postgres-github-search.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Quick replay of how I got here, because everything Hackorum does comes from this.
* 2022. New to Postgres. I do what every developer on Earth does in 2022. I go to GitHub.
--

## Where are the issues and PRs?

<img src="img/postgres-github.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* I find the repo. Beautiful repo, thirty years of history.
* Zero issues. Zero pull requests.
* For anyone who grew up on GitHub, this reads as a dead project.
* It is of course one of the most active open source projects on the planet. The activity is just somewhere else.
--

## I'm confused! How do I contribute?

<img src="img/how-to-contribute.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* So I read the docs. And the docs are good. Honest, thorough, and they tell you exactly what to do.
* They tell you to send an email.
--

## Back to the roots! Mailing lists!

<img src="img/postgres-mailinglists.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Mailing lists. Fine. I am old enough to remember mailing lists. I can do mailing lists.
--

## There are... 54 active lists!?

<img src="img/overview-mailinglists.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Fifty-four of them.
* Which one do I subscribe to? -hackers obviously, but also -bugs? -docs? -general? -patches?
* And what is the difference between -hackers and -patches in practice, in 2026?
* Nobody tells you. You learn it by being wrong in public.
--

## This is a joke, right?

<img src="img/unread-emails.png" style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* So I subscribed. To -hackers. One list.
* This is what my mailbox looked like after a holiday.
--

## The same thread, twice

<div class="cols">

<img src="img/mailclient-thread.png" data-preview-image style="width:870px; height:auto; background:none; border:none; box-shadow:none;">

<img src="img/hk-thread-compare.png" data-preview-image style="width:870px; height:auto; background:none; border:none; box-shadow:none;">

</div>

**504 messages. 503 of them called "Re: index prefetching". 21 people. Three years.**

Note:

* On the left, that thread in a mail client. On the right, the same thread in Hackorum. Same messages, same archive, same protocol.
* These are the real senders and the real dates. Not a single invented row.
* Five hundred and four messages. Five hundred and three of them have the identical subject line. Twenty-one people. Started June 2023, still going this morning.
* Look at the left and tell me where the objection that changed the design is. Nobody can. The information is all there and none of it is visible.
* On the right, the same data, with the reply structure recovered from headers that were in the mail all along.
* If you remember one slide from this talk, remember this one.
--

## Can I request a 30h workday somehow?

<img src="img/large-threads.png" style="height:330px; width:auto; background:none; border:none; box-shadow:none;">

<img src="img/very-large-threads.png" style="height:330px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* It is not just volume, it is shape. Single threads with two hundred, three hundred, five hundred messages, spanning years.
* Forking into sub-discussions that reference each other.
* This is where most newcomers quietly stop. Not because they are not smart enough.
* Because they cannot find the thread, and once they find it they cannot find the end of it.
---

## To be clear: the lists are not the problem

* `pgsql-hackers` - where PostgreSQL is actually built
* `pgsql-general`, `pgsql-docs`, `pgsql-bugs`, `pgsql-patches`, `pgsql-committers`
* **Almost 30 years of institutional knowledge** - since 1997

> *"If it wasn't on -hackers, it didn't happen."*

Note:

* I need to be very clear about this. The mailing lists are not a legacy mistake. They are the heartbeat of this project.
* Decentralised, vendor-neutral, thirty years of searchable archive, and a contributor culture that works.
* The problem is not the protocol. The problem is that the only interface anyone ships for it is an email client.
* And email clients were not designed to help you follow a five-hundred-message technical argument across four years.
--

## The firehose, in numbers

<img src="img/hk-report-monthly.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

**August 2026 alone:** 3,076 messages &middot; 278 active people &middot; 364 new threads &middot; 47 newcomers

> That is a message **every 14 minutes**, day and night, for a month.
<!-- .element: class="fragment highlight-box" -->

Note:

* This is Hackorum's own monthly report. One month. Three thousand messages. Two hundred and seventy-eight people.
* That is a message every fourteen minutes, around the clock, including while you sleep. Nobody reads that.
* And the number I care about most, forty-seven people who had never posted before.
* Forty-seven newcomers a month is a healthy community.
* The question is how many of those forty-seven are still here in six months.
--

## Where it actually hurts

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

## Why we can't just replace email

* **Decentralised by design** - no corporate single point of failure
* **~30 years of archive** that must keep working
* **Neutral ground** - no vendor walled garden
* **An established contributor culture** with real expectations

> The goal: **evolve the interface, not the protocol.**
> Email stays the source of truth. Hackorum is the lens.
<!-- .element: class="fragment highlight-box" -->

Note:

* Every few years somebody proposes moving Postgres to GitHub, or GitLab, or Discourse.
* Every time the answer is no, and the answer is correct, for the reasons on this slide.
* So we did not build a replacement. We built a lens.
* Every message in Hackorum is a real message on a real mailing list.
* If Hackorum disappears tomorrow, the archive is untouched and everybody's workflow still works. We are strictly additive.
* Email stays the source of truth. Hackorum is the lens.
---

# Hackorum

<img src="img/hk-landing.png" data-preview-image style="height:760px; width:auto; background:none; border:none; box-shadow:none;">

<a href="https://hackorum.dev">hackorum.dev</a>

Note:

* This is it. A forum-style interface on top of the PostgreSQL mailing lists.
* The list you are looking at is a list of conversations, not messages. One mailing list thread is one topic.
* The icons under each title are state. Has a patch, has CI, has a note, partially read.
* On the left, six mailing lists. Hackers, patches, bugs, docs, general and committers.
* And at the bottom left, saved searches. Remember "Patch, no replies". It comes back, and it is my favourite thing in the product.
--

## What Hackorum gives you

* **Read** - threads as conversations, a branch outline, per-message read state
* **Find** - a real query language, saved searches, 30 years of archive
* **Track** - commitfest status, patchset versions, reviewers, commits, back-ports
* **Test** - CI on every patch, and a Docker image to try one in 90 seconds
* **Collaborate** - teams, shared notes, `@mentions` and `#tags`
* **Reply** - send to the list from the UI, with correct headers
* **Measure** - contributor profiles, weekly reports, 29 years of statistics

> Six mailing lists. One account. Your mail client keeps working.

Note:

* Everything on this list is built on top of real mailing list messages, and none of it asks the project to change anything.
* Six mailing lists, one account, and your mail client keeps working exactly as it does today.
--

## One thread = one Topic

<img src="img/hk-thread.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Open a topic and you get everything about that conversation in one place.
* Down the left rail: CI status. The commitfest entry with its state, here "waiting on author", and its tags. The named reviewers. The participants, with their contributor tier as a small badge. The attachments, including a one-click download of the latest patchset.
* You did not open four tabs. You opened one page.
--

## The shape of a 501-message argument

<div class="cols">

<img src="img/hk-thread-outline.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

* Colour-coded reply branches, reconstructed from `In-Reply-To`
* *"#5...#20 to Tomas Vondra (#1)"* - a sub-debate you can read or skip as a unit
* Collapse what you don't care about, jump straight to any message

</div>

Note:

* This is the answer to "five hundred messages, where do I start". Zsolt still wants to rework this view, and he is probably right, but even in this state it shows the difference.
* Email is flat and chronological. Technical arguments are not. They branch.
* Somebody objects at message four, three people argue about it for fifteen messages, and meanwhile the main line carries on.
* The thread outline reconstructs that shape from the In-Reply-To headers, colour-codes each branch, and lets you collapse the ones you do not care about.
* The thread on screen is index prefetching. Five hundred and four messages, started June 2023.
* If you read one message a minute and never stopped, that thread is a full working day. Eight and a half hours.
* The latest patchset is plus seven and a half thousand lines, minus two thousand eight hundred.
* Try following that in Thunderbird.
--

## Read state that survives closing your laptop

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

## Search that is actually a query language

<img src="img/hk-search.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

```
from:andres[messages:>=10] has:patch
```

Note:

* Boolean logic, field selectors, and the part worth showing off, dependent conditions.
* "from:andres messages:>=10" means Andres posted here, and the thread has ten or more messages from anyone.
* "from:andres[messages:>=10]", with the brackets, means Andres specifically posted ten or more messages. Entirely different question, and it is the one you actually wanted to ask.
* You can also ask for has:patch, unread:me, starred:me, notes:me, from:committer, commitfest by status, tags from your team, anything after a date.
* And you can save any of them.
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

* Who here has sent a patch to this list and never heard anything back?
* This is that list.
* The query says: every thread from the last six months with a patch and exactly one message.
* One message means nobody replied. Not nobody merged it. Nobody said anything at all.
* ZSTD TOAST compression. Halve peak memory allocation for toast_flatten_tuple. Honor LC_NUMERIC on Windows.
* Somebody wrote each of those. Tested it, formatted a patch, wrote a cover letter, sent it to a mailing list, and then refreshed their inbox for a week.
* This is nobody's fault. Reviewer time is the scarcest resource this project has.
* But until now there was no way to even see this list, and you cannot fix a queue you cannot look at.
* One hundred and twenty-four patches in the last six months where nobody said anything at all, out of fourteen hundred and fifty. One in twelve.
* All time, one thousand two hundred and seventy-nine. That is the standing backlog of people who were ignored.
* We ship it as a global saved search called "Patch, no replies", and another called "No contributor or committer replies".
* If you take one URL home from this talk, take that one.
--

## Commitfest, reviewers and patchsets, inline

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
---

## It doesn't just read the lists

### It builds, tests, links and talks back.

Note:

* Everything so far is Hackorum as a better reader. Find the thread, follow it, know where you left off.
* The next few slides are the part that does work for you rather than just showing you things.
* It builds and tests every patch. It connects commits back to the threads that produced them. And it can send your reply to the list.
--

## We build and test every patch on the list

<img src="img/hk-ci-dashboard.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Not every commitfest submission. Every patch posted to the lists.
* Six thousand three hundred tracked patchsets, seventeen hundred CI runs in the last twenty-four hours, twenty-two in flight right now.
* For each patchset we work out the right base commit, apply it, build it, run the full test suite, and keep rebasing it as master moves.
* Applies, needs rebase, base too old, tests failed. All of it visible, all of it public.
* This is our own CI, not the project's, and it is explicitly marked beta.
* And it does less than cfbot. We run one single Linux job per patchset; the commitfest CI runs ten different ones. It is not a replacement for cfbot. It is an experiment in what happens if a basic build and test exists for everything, not just commitfest entries.
--

## One command to try somebody's patch

```bash
docker run --rm -p 5432:5432 ghcr.io/hackorum-dev/postgres-patch:t47973
psql -h localhost -U postgres
```

**Anyone with Docker: run it now. It'll be up before I finish this slide.**
<!-- .element: class="fragment highlight-box" -->

<img src="img/hk-ci-banner.png" data-preview-image style="height:600px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* That is a running PostgreSQL, built from that thread's latest patch. No checkout, no toolchain, no build, no twenty minutes of your life.
* Think about what that does to the review queue. "Could you try this?" used to cost somebody an afternoon. Now it costs ninety seconds and a Docker pull.
* Anyone with Docker, paste that now.
* And if you want the source, every patchset is also pushed as a branch to our Postgres fork. One git fetch puts you on exactly the tree CI built. Not a tree you hope is the same. The same one.
--

## Commits and threads, finally connected

<img src="img/hk-person-commits.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* We parse the entire Postgres git history and link commits back to the threads that produced them.
* Via commit trailers and Discussion links. Older commits without a proper link are simply not associated. Matching on the patch files themselves was tried, and it was too unreliable to ship.
* So a thread now tells you this landed, here is the commit, and here are the branches it was back-patched to.
* And a person shows their commit credits split by role. Author, committer, reviewer, reported-by, co-author.
* That last breakdown matters, and it comes back in a few minutes.
--

## Contributor profiles &amp; identity resolution

<img src="img/hk-person.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Twenty-seven and a half thousand messages. Three thousand commit credits. Seventeen years.
* And three email aliases, resolved into one person. That is the panel on the left.
* Identity resolution is unglamorous and absolutely essential. People change jobs, change addresses, send from their phone. Without merging aliases, every statistic you compute is wrong.
* Contributor tiers, core team, committer, major and significant contributor, are mirrored from the main postgresql.org website, and you can filter search by them.
* And look at "patch threads that landed", seventy-one percent. That is a metric nobody had before.
--

## Teams, notes, @mentions and #tags

<img src="img/hk-note.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* This is the collaboration layer that email does not have.
* Teams can be private, public or open. Inside a team you get shared notes on any topic, at-mentions of people and teams, and hash-tags that become searchable.
* Visibility is scoped properly. The author, the mentioned users, the mentioned teams. Nothing leaks.
* The use case that sold it for us internally was simply "who on our team is reviewing what, and what did we conclude last time we looked at this".
* That conversation used to live in Slack, disconnected from the thread. Now it lives on the thread.
--

## Reply to the list, from Hackorum

<img src="img/hk-composer.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* And here is the loop closing.
* You can write a reply in Hackorum and send it to the mailing list. Properly. Correct In-Reply-To, correct References, reply-all recipients, Thunderbird-style selective quoting if you highlight text first.
* It goes out through your own account with a narrowly scoped send permission.
* It is your email, from your address, on the real list. We are not a proxy and we do not rewrite your From header.
* There is a drafts view, a confirmation step before anything leaves, and a pending badge until we see the message come back from the list.
* Until the list echoes it, we do not claim it was sent.
* This took longer than everything else combined, and every hour of it went on making sure we never send something you did not mean to send.
--

## Weekly and monthly community reports

<img src="img/hk-report-weekly.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Automatically generated digests. Message volume, active people, new threads, newcomers, week over week.
* Activity rankings split by type of contribution. Started a thread, replied to their own, replied to somebody else, sent a first patch, sent a follow-up patch.
* Because "posted a hundred and thirty-nine messages" and "reviewed a hundred and thirty-nine patches" are very different things, and we should stop conflating them.
* On the left, the most active, most diverse and longest running thread of the period.
* A decent five-minute Monday morning read for what you missed.
--

## 29 years of a mailing list, as charts

<img src="img/hk-stats.png" data-preview-image style="height:800px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Public, no login needed. Message volume since 1997. New versus retained participants. Retention cohorts. Topic longevity.
* Some of these exist because we were curious, not because anyone asked.
* But a couple of them are genuinely uncomfortable to look at, the retention ones especially, and I think this community should be looking at them.
* If you are into community metrics, come and find me afterwards. There is a whole talk in this screen alone.
--

## It also works on the train

<img src="img/hk-mobile.png" data-preview-image style="height:400px; width:auto; background:none; border:none; box-shadow:none;">
<img src="img/hk-landing-dark.png" data-preview-image style="height:400px; width:auto; background:none; border:none; box-shadow:none;">

Note:

* Mobile, and dark mode.
* The mobile one is not a joke feature. A lot of keeping up with -hackers happens on a phone, in a queue, at an airport.
* If the only way to read the list is a desktop mail client, you have already lost those minutes.
* Dark mode is here because I was asked for it approximately nine hundred times.
---

## Hackorum in 90 seconds

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
---

## So what's next?

### This is where we stop presenting and start asking.

Note:

* Everything up to here was what we built. Everything after this is what we are not sure about, and I mean that.
* These are open questions, not a roadmap I am pretending to consult you about.
* Four ideas, and the objection I already know about for each one.
* Then on Friday we have a whole session to argue about them properly.
--

## Idea 1 - AI summaries of threads

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

## Idea 2 - Community contributor profiles

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

## Idea 3 - Bug and feature tracking, from threads

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

## Idea 4 - Topic grouping

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

## The questions we cannot answer alone

1. **Who is allowed to set state** on anything - a bug, a patch, a group?
<!-- .element: class="fragment" -->
2. **Where should this data live** long-term? Who owns it?
<!-- .element: class="fragment" -->
3. **Opt-in or default** for anything generated - summaries, groupings, tiers?
<!-- .element: class="fragment" -->
4. **What must never change**, no matter how nice the UI gets?
<!-- .element: class="fragment" -->

Note:

* These are the four that keep me up.
* The fourth one is the one I would most like answered by the people in this room who have been here twenty years.
* There are things about this project's workflow that look like friction to a newcomer and are actually load-bearing.
* I would much rather be told which ones those are than find out by breaking one.
---

## Community Day: Friday

### A dedicated Hackorum session at the Community Events Day.

**Come and argue with us.**

Bug tracking &middot; contributor profiles &middot; thread grouping &middot; AI summaries &middot; governance

Note:

* Friday. Community Events Day. A session dedicated to exactly those four questions.
* I am not asking you to come and be told things. I am asking you to come and disagree with us while it is still cheap to change our minds.
* Right now every one of those ideas is a paragraph in a design doc. In six months one of them will be a database migration.
* Especially if you are a committer, if you triage bugs, if you are working on contributor profiles, or if you have strong feelings about what should not change.
--

## Get involved

* **Use it:** [hackorum.dev](https://hackorum.dev)
* **Code:** [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)
* **Issues / ideas:** [GitHub Issues](https://github.com/hackorum-dev/hackorum/issues)
* **Chat:** [PostgreSQL Hacking Discord](https://discordapp.com/channels/1258108670710124574/1471524461374083186)
* **Public DB dumps:** [dumps.hackorum.dev](https://dumps.hackorum.dev)

<img src="img/hackorum-qrcode.png" style="background:none; border:none; box-shadow:none; width:300px;">

Note:

* Everything is open source and on GitHub.
* The database dumps, schema plus public data, are published so you can run your own copy or do your own analysis without asking us for anything.
* If you only do one thing, sign in and set your read state. The whole thing gets dramatically more useful the moment it knows what you have already seen.
--

## People are actually using it

<img src="img/quote-david-steele.png" data-preview-image style="width:1150px; height:auto; background:none; border:none; box-shadow:none;">

<img src="img/hackorum-discord.png" data-preview-image style="width:1150px; height:auto; background:none; border:none; box-shadow:none;">

<img src="img/hackorum-usefulness.png" data-preview-image style="width:1700px; height:auto; background:none; border:none; box-shadow:none;">

*&mdash; Andrey Borodin, on `pgsql-hackers`*

Note:

* All three are Postgres contributors, and nobody was asked for a quote.
* David Steele. A pinned tab in my browser, so great to be able to follow hackers without losing my mind. That is the entire value proposition in one sentence, and it is not mine.
* Christoph Berg set up a hackorum channel on the PostgreSQL Hacking Discord when we asked him.
* And this last one is my favourite. Andrey Borodin apologising for bumping a ten-year-old thread, who only knew it was exactly ten years old because Hackorum told him.
* That is the whole point. The archive always had that information. Nobody could see it.
---

# Questions?

### Find us after the talk, or online:

**kai.wagner@percona.com**

[hackorum.dev](https://hackorum.dev) &middot; [github.com/hackorum-dev/hackorum](https://github.com/hackorum-dev/hackorum)

### And on **Friday** at the Community Events Day.

Note:

* The question I get asked most is whether this is trying to replace the mailing lists. No, and the architecture makes it impossible. Every message is a real list message.
* Who pays for this? Percona sponsors the development and the hosting today. That is exactly why the governance question matters, and it is a fair thing to be uncomfortable about.
* What about the archives at postgresql.org? Untouched. We consume, we never write there.
* Can I delete my data? There is a delete-account flow. The mailing list archive is not ours to delete from, and we are clear about that.
* Why not just fix the commitfest app? Different problem. That tracks patches. This tracks conversations, and most conversations never become a commitfest entry.
* Can I self-host? Yes. Docker Compose, Postgres 18, and the public dumps to seed it.
* And on Friday, Community Events Day.
---

<div id="backup-slides"></div>

# Backup slides :-)

Note:

* Everything past here is for a question that deserves a picture.
---

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
---

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
---

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
---

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
