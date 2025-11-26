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

## Etikettenschwindel
### Wie "Open Source" ist Deine Datenbank wirklich?

Eine Reise durch Lizenzen, Marketing-Fallen und echte Freiheit.

<p>Kai Wagner | <a href="mailto:kai.wagner@percona.com">kai.wagner@percona.com</a></p>

---

<img src="img/who-we-are.png" style="background:none; border:none; box-shadow:none;">

--

<img src="img/number-of-database-environments.png" style="background:none; border:none; box-shadow:none;">

--

<img src="img/customer-base.png" style="background:none; border:none; box-shadow:none;">

---
## Kurze Umfrage ✋

Wer von euch nutzt Open Source Datenbanken in Produktion?

- ... MySQL? PostgreSQL? MongoDB? Redis?
<!-- .element: class="fragment" -->

Achtung: Mindestens zwei der genannten sind oft **nicht mehr** Open Source.
<!-- .element: class="fragment warning-box" -->

---
## Wer glaubt zu wissen was Open Source ist? ✋

---
## Was ist "Open Source"?

Wenn man 5 Leute fragt, bekommt man 6 Antworten.

1. "Es kostet nichts." (Falsch)
<!-- .element: class="fragment" -->
2. "Ich kann den Code lesen." (Unzureichend)
<!-- .element: class="fragment" -->
3. "Ich kann es auf GitHub finden." (Gefährlich)
<!-- .element: class="fragment" -->

--
## "Kostet nichts?!"

<img src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none;">

Note:
Der Markt soll bis 2032 auf über 118 Milliarden anwachsen. 

--
"Collaborating with a community is about more than developing code. Collaboration is about the freedom to ask questions and offer improvements - that’s the open source way and the power of the open organization."

https://www.redhat.com/en/topics/api

--
## Free Speech vs. Free Beer

> "Free software is a matter of liberty, not price. To understand the concept, you should think of 'free' as in 'free speech', not as in 'free beer'."
>
> -- Richard Stallman --

In der **Open Source (OSI Definition)** geht es um **Freiheiten**, nicht um den Preis.

---
## Die OSI Definition (TL;DR)

Damit ein Etikettenlabel **echt** ist, müssen (unter anderem) diese Bedingungen erfüllt sein:

- Free Redistribution: Du darfst es weitergeben/verkaufen.
<!-- .element: class="fragment" -->
- Source Code: Muss enthalten sein.
<!-- .element: class="fragment" -->
- Derived Works: Du darfst es verändern (Forks).
<!-- .element: class="fragment" -->
- No Discrimination: Gegen Personen, Gruppen oder Einsatzzwecke (Field of Use).
<!-- .element: class="fragment" -->

Merkt euch den letzten Punkt ("Einsatzzwecke"). Der wird gleich wichtig.
<!-- .element: class="fragment" -->

---
## Der Lizenz-Dschungel

Wir müssen kurz technisch werden. Es gibt zwei Hauptkategorien:

* Permissive 
<!-- .element: class="fragment" -->
* Non-permissive
<!-- .element: class="fragment" -->

Eigentlich gibt es drei Hauptkategorien da sich non-permissive aufteilt in: 
<!-- .element: class="fragment" -->
* Weak Copyleft
<!-- .element: class="fragment" -->
* Strong Copyleft
<!-- .element: class="fragment" -->

--
## Was ist der Copyleft-Effekt?

* Grundprinzip: Verbesserungen müssen der Allgemeinheit zur Verfügung gestellt werden („Geben und Nehmen“).
* Viraler Effekt: Abgeleitete Werke erben zwingend dieselbe Lizenz.
* Auslöser: Die Pflicht greift erst bei Weitergabe (Distribution) der Software.
* Interne Nutzung: Privat oder firmenintern (ohne Weitergabe) keine Pflicht zur Weitergabe.

--
## Permissive (Freigiebig)

* Maximaler Freiraum: Erlaubt fast alles – Nutzung, Änderung und Verbreitung (auch in kommerzieller/geschlossener Software).
* Minimale Pflichten: Meist muss nur der Urheberrechtsvermerk (Copyright) und der Lizenztext beibehalten werden.
* Kein Copyleft: Änderungen müssen nicht wieder veröffentlicht werden.

> Beispiele: MIT, Apache 2.0, BSD.

--
## Weak Copyleft (Begrenzt)

* Der Kompromiss: Brücke zwischen strengem Copyleft und permissiven Lizenzen.
* Dateibezogen: Änderungen an dieser spezifischen Komponente/Bibliothek müssen offengelegt werden.
* Verlinkung erlaubt: Darf oft zusammen mit proprietärer Software genutzt werden (z. B. als dynamische Bibliothek), ohne das Hauptprogramm zu "infizieren".

> Beispiele: LGPL, Mozilla Public License (MPL).

--
## Strong Copyleft (Streng)

* Viraler Effekt: Wenn diese Software genutzt oder integriert wird, muss das gesamte entstehende Werk unter derselben Lizenz stehen.
* Keine Mischung: Eine Kombination mit proprietärem (geschlossenem) Code ist in der Regel nicht möglich, ohne diesen ebenfalls offenzulegen.
* Fokus: Schützt die Freiheit der Software am aggressivsten.

> Beispiele: GPL v2/v3, AGPL.

--
## Lizenz-Dschungel Übersicht

<div class="table">

| Permissive | Weak Copyleft | Strong Copyleft |
| --- | --- | --- |
| Mach was du willst.<br><br>MIT<br>Apache 2.0<br>BSD | Änderungen müssen zurückgegeben werden.<br><br>MPL<br>LGPL | Alles was das berührt, muss auch offen sein.<br><br>GPL v2/v3<br>AGPL |

</div>

Note:
Permissive: Business-freundlich. Copyleft: User-Freedom-freundlich (viral). AGPL: Schließt das Cloud-Loophole.

---
## Der Siegeszug

*Laut db-engines.com hat Open Source im Jahr 2021 kommerzielle Datenbanken in der Popularität überholt.*

<img src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none;">

--
## Aber dieser absehbare Erfolg weckte Begehrlichkeiten.

---
## Das Lockvogelangebot
### (Der Köder-Trick)

Wie fängt man Entwickler?

1. Baut eine coole Datenbank.
<!-- .element: class="fragment" -->
2. Lizenziert sie unter Apache 2.0 (maximale Adoption).
<!-- .element: class="fragment" -->
3. Wartet, bis AWS/Google/Azure sie als Service anbieten.
<!-- .element: class="fragment" -->
4. PANIK! "Die Cloud Provider stehlen unseren Umsatz!"
<!-- .element: class="fragment" -->

---
## Die Timeline des "Verrats"
### Beispiele von Datenbanken, die ihre Lizenz änderten:

<div class="table">

| Jahr | Datenbank | Von | Zu |
|---|---|---|---|
| 2018 | **MongoDB** | AGPL | SSPL (Nicht Open Source) |
| 2019 | **CockroachDB** | Apache | BSL (Business Source) |
| 2021 | **Elastic** | Apache | SSPL / Elastic License |
| 2024 | **Redis** | BSD | RSALv2 / SSPL |

</div>

*Hinweis: Elastic, CockroachDB und Redis ruderten teilweise zurück*

Note:

Wieso AGPL? -> Grund: Um den Begriff "Open Source" wieder offiziell nutzen zu dürfen und Vertrauen zurückzugewinnen.

CockroachDB:
* 2015 - Juni 2019 Apache 2.0
* Juni 2019 - BSL 1.1 (Business Source License) - Schutz vor Cloud - "Anti-AWS-Paragraph". Darf genutzt werden, außer kommerzielle SaaS Dienste aka AWS
--> Besonderheit - Nach 3 Jahren, fällt jede Version automatisch zur offenen Apache 2.0 zurück.
--> Zusätzlich Aufteilung in kostenlose Version und Enterprise Version mit weiteren Features
* 18. November 2024 - Keine freie Version mehr, nur noch CockroachDB Software License (proprietär), kein Open Source mehr - Kostenlos nutzbar für Einzelentwickler und Firmen unter 10 Mio. USD Jahresumsatz.
Redis 
* 20.März 2024 wechsel von BSD zu SSPL und RSALv2 (Redis Source Available License).
* Shitstorm, aus Distributionen geworfen worden, Rückkehr mit AGPLv3 am 1.Mai 2025 - Jetzt 3 Lizenzen
* AGPL ist OSI anerkannt, aber Strong Copyleft. Jede Änderung am Code muss offengelegt werden. Somit Hosting wieder möglich.

--
## Was ist SSPL / BSL?
### Sie klingen wie Open Source, sind es aber **nicht**.

- **SSPL (Server Side Public License):** Diskriminiert gegen Cloud-Provider. (Verletzt OSI Punkt 6 & 9).
- **BSL (Business Source License):** "Source Available". Du darfst gucken, aber nicht in Produktion nutzen (unter gewissen Umständen), bis X Jahre vergangen sind.

> Das ist kein "Open Source". Das ist **Proprietäre Software**, bei der man den Code lesen darf.

Note:
Der "Giftköder" SSPL: Wer die Software als Service anbietet (SaaS), muss nicht nur den Code der Software selbst offenlegen, sondern auch den Code für das gesamte Management-System drumherum (Backups, Monitoring, User-Verwaltung, Hosting-Infrastruktur).

---
## Warum sollte dich das interessieren?

*"Ich bin ja kein Cloud Provider, mir doch egal?"*

❌ Falsch.
<!-- .element: class="fragment fade-up" -->

1. Vendor Lock-in: Du bist dem Hersteller ausgeliefert. Preiserhöhungen? Pech gehabt.
<!-- .element: class="fragment" -->
2. Lizenz-Compliance: Darf ich das in meiner SaaS-App nutzen? Brauche ich Anwälte?
<!-- .element: class="fragment" -->
3. Tod der Community: Externe Contributor hören auf. Das Ökosystem stirbt oder spaltet sich.
<!-- .element: class="fragment" -->
> Redis verlor seine Core-Entwickler an Valkey – die Entwicklung brach massiv ein.
>  * 37.5% of contributors (9 of 24) stopped contributing to Redis after the fork
>  * Valkey grew from 18 to 49 contributors in 18 months
>  * Valkey averages 80 PRs/month in 2025 vs Redis's 42
<!-- .element: class="fragment" -->


---
# Die Reaktion: Forks!
## Die Community lässt sich das nicht gefallen.

- **Elasticsearch** ➔ Lizenzänderung ➔ **OpenSearch** (AWS/Community)
- **Redis** ➔ Lizenzänderung ➔ **Valkey** (Linux Foundation)
- **MySQL** ➔ Oracle Kauf ➔ **MariaDB / Percona Server for MySQL**
- **MongoDB** ➔ Lizenzänderung ➔ **Percona Server for MongoDB** (Enterprise Features und Backup Tools - SSPL weiterhin aktiv)

> Echte Open Source überlebt immer, aber der Name auf der Packung ändert sich.
<!-- .element: class="fragment warning-box" -->

---
## Wie erkenne ich "echtes" Open Source?

**Die Checkliste:**

1. Ist die Lizenz OSI-approved? (opensource.org)
2. Gibt es eine "Commons Clause"? (🚩 Red Flag)
3. Steht irgendwo "Non-Commercial Use Only"? (🚩 Red Flag)
4. Wer kontrolliert das Projekt? Eine einzelne Firma oder eine Foundation (CNCF, Apache, Linux Foundation)?

---
## Fazit

1. **Namen sind Schall und Rauch.** Nur die Lizenz zählt.
2. **Source Available ≠ Open Source.**
3. **Vermeidet Lock-in.** Setzt auf echte Community-Standards (Postgres, Valkey, Percona Server for MySQL/MariaDB).

Bleibt kritisch. Bleibt frei.
<!-- .element: class="fragment warning-box" -->

--
## Open Source Is Not Just Code: It's Integrity

https://www.percona.com/blog/open-source-is-not-just-code-its-integrity/

---
# Fragen?

Vielen Dank!

