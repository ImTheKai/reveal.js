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
## Where can I find the presentation?

<img src="img/qr-code-to-presentation.png" style="background:none; border:none; box-shadow:none;">

Note:

* German and English available depending on browser locale

--

<img src="img/who-we-are.png" style="background:none; border:none; box-shadow:none;">

--

<img src="img/number-of-database-environments.png" style="background:none; border:none; box-shadow:none;">

--

<img src="img/customer-base.png" style="background:none; border:none; box-shadow:none;">

---
## Quick Poll ✋

Who among you uses Open Source databases in production?

- ... MySQL? PostgreSQL? MongoDB? Redis?
<!-- .element: class="fragment" -->

Warning: At least two of those mentioned are often **no longer** or were **not always** Open Source.
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

Note:
* Who here has ever tried to pay for "Open Source" and had to go to their boss or finance team? That process basically doesn't exist.
--
## "Costs nothing?!"

<img src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none;">

Note:
* The market is expected to grow to over 118 billion by 2032.

--

## The Victory Lap

*According to db-engines.com, Open Source overtook commercial databases in popularity in 2021.*

<img src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none;">

--

## Community and Freedom

--
"Collaborating with a community is about more than developing code. Collaboration is about the freedom to ask questions and offer improvements - that’s the open source way and the power of the open organization."

https://www.redhat.com/en/topics/api

Note:
* SUSE/RedHat were among the first to ship open source software on media and put a support phone number on the box.

--
## Free Speech vs. Free Beer

> "Free software is a matter of liberty, not price. To understand the concept, you should think of 'free' as in 'free speech', not as in 'free beer'."
>
> -- Richard Stallman --

In the **Open Source (OSI Definition)** it is about **freedoms**, not the price.

Note:
* How free is a free beer? Pretty limited to the current moment. No taking it with you, reselling it, or saving it for later.

---
## The OSI Definition (TL;DR)

For a label to be **genuine**, these conditions (among others) must be met:

- Free Redistribution: You may redistribute/sell it.
<!-- .element: class="fragment" -->
- Source Code: Must be included.
<!-- .element: class="fragment" -->
- Derived Works: You may modify it (Forks).
<!-- .element: class="fragment" -->
- No Discrimination: Against persons, groups, or fields of use (Field of Use).
<!-- .element: class="fragment warning-box"-->

Note:
* The Open Source Initiative (OSI) is the certification body for licenses. They wrote the Open Source Definition (OSD), which consists of 10 criteria.

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

Note:
* Permissive aka liberal or allowing
* Non-permissive aka restrictive or limiting

--
## Permissive (Generous)

* Maximum freedom: Allows almost anything—use, modification, and distribution (also in commercial/closed software).
* Minimal obligations: Usually only the copyright notice and license text must be retained.
* No Copyleft: Changes do not have to be republished.

> Examples: MIT, BSD, Apache 2.0

Note:

* MIT: Massachusetts Institute of Technology
* BSD: University of California, Berkeley - Berkeley Software Distribution
* Apache 2.0: Special patent clause protects users from being sued by the copyright holder for patent infringement

    * Apache 2.0 explicitly states:

    "If I give you this code, I automatically give you a license for all of my patents needed to run this code."

    This makes the patent trap impossible. Anyone publishing under Apache 2.0 cannot later sue users for patents contained in the software.

    2. The "Retaliation Clause" (Peace Clause)
    If you (the user) sue someone for patent infringement who uses this software, your Apache license terminates immediately.

    It deters patent trolls and prevents aggressive patent action against the community while using the software.

--
## What is the Copyleft Effect?

* Core principle: Improvements must be made available to the general public ("Give and Take").
* Scope: This applies to direct changes to the source code and to products in which the code is integrated.
* Exception: Private or internal company use (without distribution) requires no obligation to share.
* Variability: How strictly it applies depends on the respective license (Weak vs. Strong).

--
## Weak Copyleft (Limited)

* The compromise: A bridge between strong copyleft and permissive licenses.
* File-based: Changes to *this specific* component/library must be disclosed.
* Linking allowed: Can often be used alongside proprietary software (e.g., as a dynamic library) without "infecting" the main program.

> Examples: LGPL, Mozilla Public License (MPL).

Note:
* Generally for Weak Copyleft, specifically MPL: The "Lego Principle"
    * Imagine building a spaceship out of Lego.
    * Your spaceship is your proprietary software (secret).
    * The standard motor you plug in is a Weak Copyleft library (e.g., MPL).
    * The principle: As long as you just use the motor (plug it in), your spaceship can stay secret. The motor remains its own building block.
    * The obligation (the Copyleft part): If you open the motor and improve it (make it faster), you must publish the blueprint for the improved motor. But the blueprint for the rest of the spaceship remains your secret.
* Fun fact about LGPL: It originally stood for "Library General Public License."
    * The Free Software Foundation (FSF) renamed it intentionally to send a political message:
    * Library (old): The name sounded too "recommended"—as if this were the default license for all libraries.
    * Lesser (new): "Lesser" signals that this license protects user freedom less than the full GPL.
* With LGPL things get more specific: Dynamic linking is allowed. Static linking is trickier because you'd need to ship the object files so users can relink the library. Under LGPL, it must remain possible for the user to swap the LGPL file (e.g., .dll or .so). If that's impossible because the code is fused into an .EXE or binary, you'd have to provide your compiled object files (.o/.obj), which greatly eases reverse engineering—something no company wants with proprietary code.

--
## Strong Copyleft

* Viral effect: If this software is used or integrated, the *entire* resulting work must be under the same license.
* No mixing: Combining with proprietary (closed) code is generally not possible without disclosing that code as well.
* Focus: Protects software freedom most aggressively.

> Examples: GPL v2/v3, AGPL.

Note:
* GPL: Triggers the "everything must be disclosed" obligation only upon distribution (EXE, ISO, Docker image, etc.) which creates a SaaS loophole because there's no distribution.
* AGPL: Closes the SaaS loophole because the obligation triggers on "interaction over a network"—after access, the cloud provider must disclose the source code.

--
## License Jungle Overview

<style>
.license-box {
  text-align: left;
  padding: 15px;
  margin-bottom: 15px !important;
  border-radius: 8px;
  font-size: 0.8em !important;
  display: flex;
  align-items: center;
}
.license-icon {
  font-size: 1.5em;
  margin-right: 20px;
  min-width: 50px;
  text-align: center;
}
.license-content {
  flex-grow: 1;
}
.l-green { background: rgba(46, 204, 113, 0.15); border-left: 8px solid #2ecc71; }
.l-yellow { background: rgba(241, 196, 15, 0.15); border-left: 8px solid #f1c40f; }
.l-orange { background: rgba(230, 126, 34, 0.15); border-left: 8px solid #e67e22; }
.l-red { background: rgba(231, 76, 60, 0.15); border-left: 8px solid #e74c3c; }
</style>

<!-- GREEN: PERMISSIVE -->
<div class="license-box l-green fragment fade-up">
  <div class="license-icon">🟢</div>
  <div class="license-content">
    <strong>Permissive (Green Light)</strong><br>
    "Do what you want." No restriction for proprietary use.<br>
    <em>MIT, BSD, Apache 2.0</em>
  </div>
</div>

<!-- YELLOW: WEAK COPYLEFT -->
<div class="license-box l-yellow fragment fade-up">
  <div class="license-icon">🟡</div>
  <div class="license-content">
    <strong>Weak Copyleft (Shoulder Check)</strong><br>
    "Keep files separate." Return changes to libs.<br>
    <em>MPL, LGPL</em>
  </div>
</div>

<!-- ORANGE: STRONG COPYLEFT -->
<div class="license-box l-orange fragment fade-up">
  <div class="license-icon">🟠</div>
  <div class="license-content">
    <strong>Strong Copyleft (Yield)</strong><br>
    "Viral effect." Infects the entire project on contact.<br>
    <em>GPL v2/v3, AGPL</em>
  </div>
</div>

Better get through before the light turns **red**!
<!-- .element: class="fragment warning-box"-->

--
## How many OSI-approved Open Source licenses are there? ✋

- ... fewer than 10?
<!-- .element: class="fragment" -->
- ... between 10 and 50?
<!-- .element: class="fragment" -->
- ... between 50 and 86?
<!-- .element: class="fragment" -->
- ... more than 122?
<!-- .element: class="fragment" -->

Note:
There are 123 approved licenses as of 27.11.2025.

---
## Do you remember the Open Source market?

<section>
<img width="50%" height="100%" src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none;"><img width="50%" height="100%" src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none;">
</section>

--
## But this foreseeable success awakened greed.

---
## The Bait-and-Switch
### (The Lure Trick)

<!-- Flex container for 2 columns -->
<div style="display: flex; align-items: center; justify-content: space-between; gap: 40px; margin-top: 50px;">

  <!-- Left column: Text (55% width) -->
  <div style="width: 55%; text-align: left;">
    <p>How do you catch developers?</p>
    <ol>
      <li class="fragment" style="margin-bottom: 15px;">
        Build a cool database.
      </li>
      <li class="fragment" style="margin-bottom: 15px;">
        License it under <b>Apache 2.0</b> (maximum adoption).
      </li>
      <li class="fragment" style="margin-bottom: 15px;">
        Wait until AWS/Google/Azure offer it as a service.
      </li>
      <!-- Last item red and bold for drama -->
      <li class="fragment" style="color: #ff4444; font-weight: bold; margin-top: 25px;">
        PANIC! "The cloud providers are stealing our revenue!"
      </li>
    </ol>
  </div>

  <!-- Right column: Image (40% width) -->
  <div style="width: 40%;">
    <img src="img/aws-surfing.webp" 
         class="fragment" 
         style="width: 70%; border-radius: 15px; box-shadow: 0 10px 30px rgba(0,0,0,0.5); transform: rotate(2deg);">
  </div>

</div>

---
## The Timeline of "Betrayal"
### Examples of databases that changed their license:

<div class="table">

| Year | Database | From | To |
|---|---|---|---|
| 2018 | **MongoDB** | AGPLv3 | SSPL (Not Open Source) |
| 2019 | **CockroachDB** | Apache | BSL (Business Source) |
| 2021 | **Elasticsearch** | Apache | SSPL / Elastic License |
| 2024 | **Redis** | BSD | RSALv2 / SSPL |

</div>

*Note: Elastic, CockroachDB, and Redis partially backtracked*

Note:

* Why AGPL? -> Reason: To officially use the term "Open Source" again and regain trust.
* AGPL is OSI-approved but strong copyleft. Every change to the code must be disclosed—hosting becomes possible again.

Mongo:
* 2009 to Oct 15, 2018 AGPLv3
* Oct 16, 2018 SSPL

CockroachDB:
* 2015 - June 2019 Apache 2.0
* June 2019 - BSL 1.1 (Business Source License) - not Open Source per OSI - protection against cloud - "Anti-AWS paragraph". Usable except as commercial SaaS like AWS.
    * After 3 years, every version automatically falls back to open Apache 2.0.
    * Split into free version and Enterprise version with additional features.
* Nov 18, 2024 - No free version anymore, only CockroachDB Software License (proprietary), no longer Open Source - Free to use for individual developers and companies under $10M USD annual revenue.

Elastic:
* 2010 - Jan 14, 2021 -> Apache 2.0
* Jan 14, 2021 -> Dual license SSPL + Elastic License (No longer Open Source)
* Aug 29, 2024 -> Third license with AGPL

Redis: 
* Mar 20, 2024 switch from BSD to SSPL and RSALv2 (Redis Source Available License).
* Backlash, kicked out of distributions, return with AGPLv3 on May 1, 2025 - Now 3 licenses
* AGPL is OSI-recognized, but strong copyleft. Every change to the code must be disclosed. Hosting becomes possible again.

--

<img src="img/aws-instance-running.png" style="background:none; border:none; box-shadow:none;">

--
## What is SSPL / BSL?
### They sound like Open Source, but they **are not**.

- **SSPL (Server Side Public License):** Discriminates against cloud providers. (Violates OSI points 6 & 9).
- **BSL (Business Source License):** Proprietary on a timer. Highly restricted today (Source Available), only becomes real Open Source in the future.

> This is not "Open Source". This is **Proprietary Software** where you are allowed to read the code.

Note:
* The SSPL was created and introduced by MongoDB itself in 2018.

* GPL / AGPL: "Show me the application code." (AWS: "No problem, here's the unmodified DB.")
* SSPL: "Show me the code of your entire cloud infrastructure." (AWS: "Never!")

* SSPL: The "poison pill" SSPL: Anyone offering the software as a service (SaaS) must not only disclose the software code itself but also the code for the entire management system around it (backups, monitoring, user management, hosting infrastructure).
* BSL: The newest, best version stays proprietary. The old version is gifted to the community (Open Source). The "change date" is crucial. Classic: You may use the software, but you may not offer it as a managed service (SaaS) that competes with the vendor.

--

## The License Jungle (including Red Light)
<style>
.license-box {
  text-align: left;
  padding: 15px;
  margin-bottom: 15px !important;
  border-radius: 8px;
  font-size: 0.8em !important;
  display: flex;
  align-items: center;
}
.license-icon {
  font-size: 1.5em;
  margin-right: 20px;
  min-width: 50px;
  text-align: center;
}
.license-content {
  flex-grow: 1;
}
.l-green { background: rgba(46, 204, 113, 0.15); border-left: 8px solid #2ecc71; }
.l-yellow { background: rgba(241, 196, 15, 0.15); border-left: 8px solid #f1c40f; }
.l-orange { background: rgba(230, 126, 34, 0.15); border-left: 8px solid #e67e22; }
.l-red { background: rgba(231, 76, 60, 0.15); border-left: 8px solid #e74c3c; }
</style>

<!-- GREEN: PERMISSIVE -->
<div class="license-box l-green">
  <div class="license-icon">🟢</div>
  <div class="license-content">
    <strong>Permissive (Free Ride)</strong><br>
    "Do what you want." No restriction for proprietary use.<br>
    <em>MIT, BSD, Apache 2.0</em>
  </div>
</div>

<!-- YELLOW: WEAK COPYLEFT -->
<div class="license-box l-yellow">
  <div class="license-icon">🟡</div>
  <div class="license-content">
    <strong>Weak Copyleft (Shoulder Check)</strong><br>
    "Keep files separate." Return changes to libs.<br>
    <em>MPL, LGPL</em>
  </div>
</div>

<!-- ORANGE: STRONG COPYLEFT -->
<div class="license-box l-orange">
  <div class="license-icon">🟠</div>
  <div class="license-content">
    <strong>Strong Copyleft (Yield)</strong><br>
    "Viral effect." Infects the entire project on contact.<br>
    <em>GPL v2/v3, AGPL</em>
  </div>
</div>

<!-- RED: PROPRIETARY -->
<div class="license-box l-red">
  <div class="license-icon">🔴</div>
  <div class="license-content">
    <strong>Fake Open Source (Toll Booth)</strong><br>
    "Source Available." Discriminates against certain uses (Cloud/SaaS).<br>
    <em>SSPL, BSL, RSAL</em>
  </div>
</div>

---
## Why should you care?

*"I'm not a cloud provider, so who cares?!"*

❌ Wrong.
<!-- .element: class="fragment warning-box" -->

<ol>
  <li class="fragment" style="margin-bottom: 20px;">
    <strong>Vendor Lock-in:</strong> You're at the vendor's mercy. Price hikes? Tough luck!
  </li>
  <li class="fragment" style="margin-bottom: 20px;">
    <strong>License Compliance:</strong> Can I use this in my SaaS app? Do I need lawyers?
  </li>
  <li class="fragment">
    <strong>Death of the Community:</strong> External contributors stop. The ecosystem dies or splits.
  </li>
</ol>

<!-- New element: the red box -->
  <div class="fragment" style="
      margin-top: 30px;
      border: 3px solid #ff4444;
      background: rgba(255, 68, 68, 0.1);
      border-radius: 15px;
      padding: 20px;
      box-shadow: 0 0 20px rgba(255, 0, 0, 0.2);
  ">
    <h3 style="color: #ff4444; margin: 0 0 10px 0;">Current Example: Redis vs. Valkey</h3>
    <ul style="font-size: 0.8em; list-style-type: '⚠️  ';">
      <li><b>37.5% of contributors</b> left Redis after the license change.</li>
      <li>Valkey grew from 18 to <b>49 contributors</b> in 18 months.</li>
      <li>2025 development pace:<br>
          * Redis: ~42 PRs/month <br>
          * Valkey: <b>~80 PRs/month</b> 🚀
      </li>
    </ul>
  </div>

---
# The Reaction: Forks!
## The community won't stand for it.
<!-- .element: class="fragment" -->

- Elasticsearch ➔ License change ➔ OpenSearch (AWS/Community)
<!-- .element: class="fragment" -->
- Redis ➔ License change ➔ Valkey (Linux Foundation)
<!-- .element: class="fragment" -->
- MySQL ➔ Oracle acquisition ➔ MariaDB / Percona Server for MySQL
<!-- .element: class="fragment" -->
- MongoDB ➔ License change ➔ Percona Server for MongoDB (Enterprise features and backup tools - SSPL still active)
<!-- .element: class="fragment" -->
> Real Open Source always survives, but the name on the package changes.
<!-- .element: class="fragment warning-box" -->

---
## How do I recognize "real" Open Source?

**The Checklist:**

1. Is the license OSI-approved? (opensource.org)

2. Is there a "Commons Clause"? (🚩 Red Flag)

3. Does it say "Non-Commercial Use Only" anywhere? (🚩 Red Flag)

4. Who controls the project? A single company or a foundation (CNCF, Apache, Linux Foundation)?

Note:

* Commons Clause: The trick: The vendor takes a real open-source license (e.g., Apache 2.0) and adds a rider: "This is Apache 2.0, BUT you may not sell the code."
* Non-Commercial Use Only: Real Open Source MUST allow commercial use. Licenses like CC-BY-NC or the new CockroachDB license (free only for small companies) discriminate against certain user groups ("Field of Use Restriction"). Total legal uncertainty—what counts as commercial, where does it start, where does it end?

---
# Conclusion

--

1. **Names are just smoke and mirrors.**
   > *Elastic called it "Free and Open", while AWS called it misleading and forked OpenSearch.*

--

2. **Source Available ≠ Open Source.**
   > *The OSI officially confirmed: The SSPL (MongoDB) is NOT an Open Source license, no matter how often marketing repeats the term.*

--

3. **Avoid lock-in.**
   > *HashiCorp (Terraform) showed in 2023 how fast a license can flip. Only true standards like **OpenTofu** (or **Valkey** for Redis) give you an exit.*

--

Stay critical. Stay free.
<!-- .element: class="warning-box" -->

--
## Open Source Is Not Just Code: It's Integrity

https://www.percona.com/blog/open-source-is-not-just-code-its-integrity/

<img src="img/open-source-blog-post.png" style="background:none; border:none; box-shadow:none;">

--

## 100% Independent! 0% Bullshit!

<img src="img/logo.png" style="background:none; border:none; box-shadow:none;">

Note:

* We might not say what you want to hear, but we will say what you should hear and know.

---
# Questions?

Thank you!
