<style>
.warning-box {
  border: 2px solid #ff4444;
  background: rgba(255, 68, 68, 0.15);
  padding: 18px;
  border-radius: 10px;
  margin-top: 14px;
}

.table {
  font-size: 0.7em;
}

.table table {
  width: 100%;
  table-layout: fixed;
}

.table th,
.table td {
  padding: 10px 12px;
  vertical-align: top;
  word-break: break-word;
}
</style>

## False Labeling
### How "Open Source" is Your Database Really?

A journey through licenses, marketing traps, and true freedom.

<p>Kai Wagner | <a href="mailto:kai.wagner@percona.com">kai.wagner@percona.com</a></p>

---
## Quick Poll ✋

Who among you uses Open Source databases in production?

- ... MySQL? PostgreSQL? MongoDB? Redis?
<!-- .element: class="fragment" -->

Warning: At least two of those mentioned are often **no longer** Open Source.
<!-- .element: class="fragment warning-box" -->

---
## Who thinks they know what Open Source is? ✋

---
## What is "Open Source"?

If you ask 5 people, you get 6 answers.

1. "It costs nothing." (False)
<!-- .element: class="fragment" -->
2. "I can read the code." (Insufficient)
<!-- .element: class="fragment" -->
3. "I can find it on GitHub." (Dangerous)
<!-- .element: class="fragment" -->
--
## "Costs nothing?!"

<img src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none;">

Note:
The market is expected to grow to over 118 billion by 2032.

--
"Collaborating with a community is about more than developing code. Collaboration is about the freedom to ask questions and offer improvements - that’s the open source way and the power of the open organization."

https://www.redhat.com/en/topics/api

--
## Free Speech vs. Free Beer

> "Free software is a matter of liberty, not price. To understand the concept, you should think of 'free' as in 'free speech', not as in 'free beer'."
>
> -- Richard Stallman --

**Open Source (OSI Definition)** is about **freedoms**, not price.

---
## The OSI Definition (TL;DR)

For a label to be **genuine**, these conditions (among others) must be met:

- Free Redistribution: You may redistribute/sell it.
<!-- .element: class="fragment" -->
- Source Code: Must be included.
<!-- .element: class="fragment" -->
- Derived Works: You may modify it (Forks).
<!-- .element: class="fragment" -->
- No Discrimination: Against persons, groups, or fields of use.
<!-- .element: class="fragment" -->

Remember the last point ("Fields of Use"). That will be important in a moment.
<!-- .element: class="fragment" -->

---
## The License Jungle

We need to get technical for a moment. There are two main categories:

* Permissive
<!-- .element: class="fragment" -->
* Non-permissive
<!-- .element: class="fragment" -->

Actually, there are three main categories as non-permissive splits into:
<!-- .element: class="fragment" -->
* Weak Copyleft
<!-- .element: class="fragment" -->
* Strong Copyleft
<!-- .element: class="fragment" -->

--
## What is the Copyleft Effect?

* Core Principle: Improvements must be made available to the general public ("Give and Take").
* Viral Effect: Derived works strictly inherit the same license.
* Trigger: The obligation applies only upon distribution of the software.
* Internal Use: Private or internal corporate use (without distribution) triggers no obligation to share.

--
## Permissive

* Maximum Freedom: Allows almost anything – use, modification, and distribution (even in commercial/closed software).
* Minimal Obligations: Usually only the copyright notice and license text must be retained.
* No Copyleft: Changes do not have to be republished.

> Examples: MIT, Apache 2.0, BSD.

--
## Weak Copyleft (Limited)
* The Compromise: A bridge between strong copyleft and permissive licenses.
* File-based: Changes to *this specific* component/library must be disclosed.
* Linking Allowed: Can often be used alongside proprietary software (e.g., as a dynamic library) without "infecting" the main program.

> Examples: LGPL, Mozilla Public License (MPL).

--
## Strong Copyleft
* Viral Effect: If this software is used or integrated, the *entire* resulting work must be under the same license.
* No Mixing: Combining with proprietary (closed) code is generally not possible without disclosing that code as well.
* Focus: Protects software freedom most aggressively.

> Examples: GPL v2/v3, AGPL.

--
## License Jungle Overview

<div class="table">

| Permissive | Weak Copyleft | Strong Copyleft |
| --- | --- | --- |
| Do what you want.<br><br>MIT<br>Apache 2.0<br>BSD | Changes must be contributed back.<br><br>MPL<br>LGPL | Everything this touches must also be open.<br><br>GPL v2/v3<br>AGPL |

</div>

Note:
Permissive: Business-friendly. Copyleft: User-Freedom-friendly (viral). AGPL: Closes the cloud loophole.

---
## The Victory Lap

*According to db-engines.com, Open Source overtook commercial databases in popularity in 2021.*

<img src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none;">

--
## But this foreseeable success awakened greed.

---
## The Bait-and-Switch
### (The Lure Trick)

How do you catch developers?

1. Build a cool database.
<!-- .element: class="fragment" -->
2. License it under Apache 2.0 (maximum adoption).
<!-- .element: class="fragment" -->
3. Wait until AWS/Google/Azure offer it as a service.
<!-- .element: class="fragment" -->
4. PANIC! "The cloud providers are stealing our revenue!"
<!-- .element: class="fragment" -->

---
## The Timeline of "Betrayal"
### Examples of databases that changed their license:

<div class="table">

| Year | Database | From | To |
|---|---|---|---|
| 2018 | **MongoDB** | AGPL | SSPL (Not Open Source) |
| 2019 | **CockroachDB** | Apache | BSL (Business Source) |
| 2021 | **Elastic** | Apache | SSPL / Elastic License |
| 2024 | **Redis** | BSD | RSALv2 / SSPL |

</div>

*Note: Elastic, CockroachDB, and Redis partially backtracked*

Note:

Why AGPL? -> Reason: To officially use the term "Open Source" again and regain trust.

CockroachDB:
* 2015 - June 2019 Apache 2.0
* June 2019 - BSL 1.1 (Business Source License) - Protection against Cloud - "Anti-AWS-Paragraph". Can be used, unless commercial SaaS services aka AWS
--> Specialty - After 3 years, every version automatically falls back to open Apache 2.0.
--> Additionally split into free version and Enterprise version with further features
* Nov 18, 2024 - No more free version, only CockroachDB Software License (proprietary), no longer Open Source - Free to use for individual developers and companies under $10M USD annual revenue.
Redis
* March 20, 2024 switch from BSD to SSPL and RSALv2 (Redis Source Available License).
* Backlash, kicked out of distributions, return with AGPLv3 on May 1, 2025 - Now 3 licenses
* AGPL is OSI recognized, but Strong Copyleft. Every change to the code must be disclosed. Thus hosting possible again.

--
## What is SSPL / BSL?
### They sound like Open Source, but they **are not**.

- **SSPL (Server Side Public License):** Discriminates against cloud providers. (Violates OSI points 6 & 9).
- **BSL (Business Source License):** "Source Available". You can look, but not use in production (under certain circumstances), until X years have passed.

> This is not "Open Source". This is **Proprietary Software** where you are allowed to read the code.

Note:
The "Poison Pill" SSPL: Whoever offers the software as a service (SaaS) must not only disclose the software code itself but also the code for the entire management system around it (backups, monitoring, user management, hosting infrastructure).

---
## Why should you care?

*"I'm not a cloud provider, so who cares?"*

❌ Wrong.
<!-- .element: class="fragment" -->

1. Vendor Lock-in: You are at the vendor's mercy. Price hikes? Bad luck.
<!-- .element: class="fragment" -->
2. License Compliance: Can I use this in my SaaS app? Do I need lawyers?
<!-- .element: class="fragment" -->
3. Death of the Community: External contributors stop. The ecosystem dies or splits.
<!-- .element: class="fragment" -->
> Redis lost its core developers to Valkey – development plummeted massively.
> * 37.5% of contributors (9 of 24) stopped contributing to Redis after the fork
> * Valkey grew from 18 to 49 contributors in 18 months
> * Valkey averages 80 PRs/month in 2025 vs Redis's 42
<!-- .element: class="fragment" -->

---
# The Reaction: Forks!
## The community won't stand for it.

- **Elasticsearch** ➔ License Change ➔ **OpenSearch** (AWS/Community)
- **Redis** ➔ License Change ➔ **Valkey** (Linux Foundation)
- **MySQL** ➔ Oracle Acquisition ➔ **MariaDB / Percona Server for MySQL**
- **MongoDB** ➔ License Change ➔ **Percona Server for MongoDB** (Enterprise Features and Backup Tools - SSPL remains active)

> Real Open Source always survives, but the name on the package changes.
<!-- .element: class="fragment" -->

---
## How do I recognize "real" Open Source?

**The Checklist:**

1. Is the license OSI-approved? (opensource.org)
2. Is there a "Commons Clause"? (🚩 Red Flag)
3. Does it say "Non-Commercial Use Only" anywhere? (🚩 Red Flag)
4. Who controls the project? A single company or a foundation (CNCF, Apache, Linux Foundation)?

---
## Conclusion

1. **Names are just smoke and mirrors.** Only the license counts.
2. **Source Available ≠ Open Source.**
3. **Avoid Lock-in.** Bet on true community standards (Postgres, Valkey, Percona Server for MySQL/MariaDB).

Stay critical. Stay free.
<!-- .element: class="fragment" -->

--
## Open Source Is Not Just Code: It's Integrity

https://www.percona.com/blog/open-source-is-not-just-code-its-integrity/

---
# Questions?

Thank you!
