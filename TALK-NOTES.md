# PGConf.EU 2026 — Hackorum talk

**Session:** Finally a Postgres Communication Hub for Experts and Newcomers
**When:** Thursday, October 22nd 2026, 09:25–10:15 (50 min), Room Audit 2, Level: Beginner
**Who:** Jack Bonatakis (Robin) · Kai Wagner (Percona)
**Abstract:** https://www.postgresql.eu/events/pgconfeu2026/schedule/session/8197-finally-a-postgres-communication-hub-for-experts-and-newcomers/

Slides: `slides/slides.md` (reveal.js markdown, speaker notes after `Note:` on every slide).
Press `S` in the browser for the speaker view.

**Run it locally:** `python3 -m http.server 8000` from the repo root, then
<http://localhost:8000/>. (`npm start` needs `npm install` first - this checkout's
`node_modules` predates the vite build.) Add `?print-pdf` to the URL for PDF export.

## Deck conventions

Follows the same conventions as `it-tage-frankfurt-2025` and the Berlin deck:

* `##` for slide headings, `###` for a subtitle under one, `#` for statement slides
* Body content is **bullet lists**, not centred prose - reveal left-aligns lists and
  they fill the slide width
* Reusable styling lives in the `<style>` block at the top of `slides.md`
  (`.highlight-box`, `.warning-box`, `.cols`, `.table`), never as inline styles
* `<!-- .element: class="fragment" -->` on the line *after* an item to reveal it on click
* Images: `<img src="..." style="height:NNNpx; width:auto; background:none; border:none; box-shadow:none;">`
  - sized by height because the canvas is 16:9; `data-preview-image` makes them
  zoomable during the talk. **Exception:** for very wide images (ratio above ~4:1,
  e.g. chat-log crops) set `width:NNNpx; height:auto` instead — a fixed height
  projects them wider than the 1843px canvas, and reveal's `max-width:100%` then
  squashes them vertically and destroys the aspect ratio.
* Two-column (image beside bullets) uses `<div class="cols">`, because `.reveal ul`
  is `display:inline-block` and would otherwise collide with the image
* Speaker notes: `Note:` then a blank line, then `*` bullets
* `index.html` is 1920x1080 with `maxScale: 1` (same as the IT-Tage deck). The Berlin
  deck was 4:3 1280x960 - switch back in `index.html` if Valencia projects 4:3.

## Structure / timing

| Section | Slides | Minutes |
|---|---|---|
| Hook + who we are + Jack's story + joining forces + crediting Zsolt | 1–5 | 6 |
| The problem (Kai's 2022 story, the side-by-side, the firehose) | 6–17 | 9 |
| What Hackorum is, and the feature tour | 18–35 | 17 |
| The 90-second walkthrough video, narrated | 36 | 4 |
| What's next + the four questions | 37–42 | 8 |
| Community Day CTA, links, Q&A | 43–46 | 5 |
| Backup slides | 47–60 | — |

That is **49 minutes** of content in a 50-minute slot, including about two minutes
for Jack's story and the decision to join forces. The walkthrough is recorded,
so its timing is predictable.

On slide 2, Kai hands over to Jack for **"How did I end up here?"** (slide 3).
Jack tells the Robin → mailing lists → pginbox story, then explains the decision
to sunset pginbox and join Hackorum on **"From pginbox to Hackorum"** (slide 4).
He hands back to Kai for Zsolt's credit (slide 5) and Kai's own 2022 story (slide 6).

Slide 19 (*What Hackorum gives you*) is the signpost for the whole tour — if you are
running long, that slide plus the video carries the section on its own.

The red thread: **every Postgres conversation that matters already happened — you just
can't find it, follow it, or join it.** Hackorum turns the firehose into something you can
drink from — it reads, finds, tracks, tests, links and talks back; what happens next is a
community decision, and that decision happens on Friday.

## The walkthrough video

`img/hackorum-walkthrough.webm` — 91 seconds, 1600×1000, no audio, autoplays when you
reach slide 36 and has controls so you can pause and talk. Recorded against the live
site with a scripted Playwright session: a visible cursor and the caption strip are
injected, and **every non-GET request was blocked during recording**, so nothing in the
walkthrough touched real data.

Two things to know:

* it is a **webm** — fine in Chrome and Firefox, *not* in Safari. Present from Chrome
  or Firefox, or ask me to convert it.
* Playwright's webm has no seek cues, so **scrubbing does not work**. Pause and play
  are fine; dragging the scrubber is not. If you want to re-run a section, reload the
  slide.

To re-record after the UI changes, the script is in the scratchpad (`record.mjs`);
ask and I will regenerate it.

## Audience interaction

Four moments, spread through the talk — don't let them all bunch at the start:

1. **Slide 1, show of hands.** Subscribed to -hackers? Inbox at zero? Read everything
   from last week? The third question is the hook; nobody's hand stays up.
2. **Slide 12, "The same thread, twice."** Point at the left pane and ask "where is
   the objection that changed the design?" Let the silence answer.
3. **Slide 28, `docker run`.** "Anyone with Docker, paste this now." Give them fifteen
   seconds of quiet. People poking at a running Postgres during the next slide is a
   success, not a distraction.
4. **Slide 24, second show of hands**, *before* revealing the query: "who here has sent
   a patch to this list and never heard anything back?" Then: "this is that list."

The QR code for hackorum.dev now sits in the top-right corner of **every** slide (it is
in the theme, not the markdown), so anyone can open it and follow along at any point —
the same trick the Berlin deck used.

## Before the talk — TODO

- [x] **Jack's intro** on slide 2: role, newcomer perspective, and pginbox joining Hackorum.
- [ ] **Zsolt's credit slide (5)** — two things to confirm:
      - he is happy with his photo and profile stats on a conference slide
      - the origin story is now Zsolt's own version: he asked "why has nobody built
        this yet?" in the *Scaling PostgreSQL Development* unconference session at
        PGConf.dev 2025, then talked it through in the hallway track. The 9 Dec 2025
        first commit is a 12k-line squash of the initial development; design talks
        were around November, and it went public on Discord at the end of December.
        279 of 378 commits on `upstream/main` are his.
- [ ] **The testimonials slide (45)** names David Steele, Christoph Berg and
      Andrey Borodin. The first two are chat screenshots with avatars; Andrey's is
      a public `pgsql-hackers` message, attributed on the slide. Worth a quick word
      with all three before it goes on a conference screen.
- [ ] **Confirm the Community Day session** time/room and put it on the CTA slide (slide 43).
- [ ] **Re-count the no-reply numbers** on slide 24 before the talk. As of
      24 Sep 2026: **124** of **1,450** patch threads started in the last six months
      have no reply (one in twelve), and **1,279** all time. Queries:
      `has:patch messages:1 first_after:6m`, `has:patch first_after:6m`,
      `has:patch messages:1`. Hackorum does not show a result count, so these were
      counted by walking the cursor pagination — ask me and I will re-run it.
- [ ] **Re-shoot the screenshots.** Everything in `img/hk-*.png` was captured on
      2026-09-22 against live hackorum.dev. Numbers quoted in the slides and notes will
      have moved by October:
      - Slide 15 / notes: August 2026 = 3,076 messages · 278 people · 364 threads · 47 newcomers
      - Slide 27 / notes: 6,327 tracked patchsets · 1,744 CI runs in 24h · 22 in flight
      - Slide 52 (backup): 11,397 runs in 7d · 84.4% success · median build 2m50s
      - Slide 30 / notes: Michael Paquier 27,641 messages · 3,026 commit credits · 3 aliases
      - Slide 21: "index prefetching" = 501 messages
      - Backup teams slide: percona team 43% landed vs committer 71%
- [ ] **Decide on the team screenshot** (`img/hk-team.png`, backup slides) — it shows 11
      Percona colleagues' work email addresses. They are all public on the lists, but
      worth a heads-up to the team before it goes on a conference screen.
- [ ] **The mail-client image** (`img/mailclient-thread.png`, slide 12) is a rendering,
      not a literal screen capture of a mail client. The senders, subjects and
      timestamps are the real first 38 messages of topic 47973, pulled from Hackorum's
      API; only the chrome around them is drawn. Describe it that way if anyone asks —
      "this is what that thread looks like in a mail client", not "here is my Thunderbird".
      Regenerate with the script in the scratchpad if the thread grows.
- [ ] **Watch the walkthrough video once with the notes open** (slide 36). It is 91
      seconds and it cannot fail, but you need to know the beats well enough to talk
      over it without watching it yourself. The beat sheet is in that slide's notes.
- [ ] **Practice the demo path** (in the speaker notes on slide 28). The `docker run`
      line is the moment of the talk — have a terminal ready and a pre-pulled image.

## Re-shooting screenshots

The screenshots were taken with headless Chromium against the live site using a logged-in
session cookie, at 1600×1000 / DPR 2, light theme (plus one dark-mode shot and two mobile
shots at 430×932). Tall sidebar panels (`hk-thread-outline.png`, `hk-patchsets.png`) are
viewport-clipped to the left column; `hk-ci-banner.png` is cropped out of the full thread
screenshot. Keep them under 2000px wide so the deck stays a reasonable size.

## Lineage

Built on the Berlin meetup deck (branch `pgmeetup-berlin-march-2026-hackorum`) — the
"how I got lost in 2022" arc and several problem-statement images are reused deliberately,
since that opening worked. The feature tour is new and is written for an audience seeing
Hackorum for the first time: nothing in the slides or the notes refers back to the meetup,
or frames anything as "new since March".
