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
## Wo finde ich die Präsentation?

<img src="img/qr-code-to-presentation.png" style="background:none; border:none; box-shadow:none;">

Note:

* Deutsch und Englisch je nach Browser Locale verfügbar

--

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

Achtung: Mindestens zwei der genannten sind oft **nicht mehr** bzw waren **nicht immer** Open Source.
<!-- .element: class="fragment warning-box" -->

---
## Wer glaubt zu wissen was Open Source ist? ✋

---
## Was ist "Open Source"?

Wenn man 5 Leute fragt, bekommt man 6 Antworten.

1. "Kostet nichts." (Falsch)
<!-- .element: class="fragment" -->
2. "Ich kann den Code lesen." (Unzureichend)
<!-- .element: class="fragment" -->
3. "Ich kann es auf GitHub finden." (Gefährlich)
<!-- .element: class="fragment" -->

--
## "Kostet nichts?!"

<img src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none;">

Note:
* Der Markt soll bis 2032 auf über 118 Milliarden anwachsen. 

--

## Der Siegeszug

*Laut db-engines.com hat Open Source im Jahr 2021 kommerzielle Datenbanken in der Popularität überholt.*

<img src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none;">

--

## Community und Freiheit

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

Note:
* Die Open Source Initiative (OSI) ist der TÜV für Lizenzen. Sie haben die "Open Source Definition" (OSD) geschrieben, die aus 10 Kriterien besteht.

---
## Der Lizenz-Dschungel

Wir müssen kurz technisch werden. Es gibt zwei Hauptkategorien:

* Permissive (permissiv) 
<!-- .element: class="fragment" -->
* Non-permissive (nicht permissiv)
<!-- .element: class="fragment" -->

Eigentlich gibt es drei Hauptkategorien da sich non-permissive aufteilt in: 
<!-- .element: class="fragment" -->
* Weak Copyleft
<!-- .element: class="fragment" -->
* Strong Copyleft
<!-- .element: class="fragment" -->

Note:
* permissiv aka freizügig oder erlaubend
* nicht permissiv aka restriktiv oder beschränkend

--
## Permissive (Freigiebig)

* Maximaler Freiraum: Erlaubt fast alles – Nutzung, Änderung und Verbreitung (auch in kommerzieller/geschlossener Software).
* Minimale Pflichten: Meist muss nur der Urheberrechtsvermerk (Copyright) und der Lizenztext beibehalten werden.
* Kein Copyleft: Änderungen müssen nicht wieder veröffentlicht werden.

> Beispiele: MIT, BSD, Apache 2.0

Note:

* MIT: Massachusetts Institute of Technology
* BSD: University of California, Berkeley - Berkeley Software Distribution
* Apache 2.0: Besonderheit - Patent Klausel - Schützt Nutzer vor dem verklagt werden durch den Urheber vor Patentverletzungen

    * Apache 2.0 - Die Lizenz sagt ausdrücklich:

    "Wenn ich dir diesen Code gebe, gebe ich dir automatisch auch eine Lizenz für alle meine Patente, die nötig sind, um diesen Code auszuführen."

    Damit ist die oben genannte Falle unmöglich. Wer Software unter Apache 2.0 veröffentlicht, kann die Nutzer später nicht wegen Patenten verklagen, die in dieser Software stecken.

    2. Die "Retaliation Clause" (Die Vergeltungs-Klausel / Friedenspflicht)
    Das ist der genialste Teil für Unternehmen. Die Klausel besagt:

    "Wenn du (der Nutzer) jemanden wegen Patentverletzung verklagst, der diese Software nutzt, dann erlischt deine Apache-Lizenz sofort."

    Was das bedeutet: Es ist eine "Waffe", die Patent-Trolle abschreckt. Wenn eine Firma Software unter Apache 2.0 nutzt, darf sie nicht aggressiv gegen die Community oder andere Nutzer wegen Patenten vorgehen, sonst verliert sie selbst das Recht, die Software zu nutzen.

--
## Was ist der Copyleft-Effekt?

* Grundprinzip: Verbesserungen müssen der Allgemeinheit zur Verfügung gestellt werden („Geben und Nehmen“).
* Umfang: Dies betrifft sowohl direkte Änderungen am Quellcode als auch Produkte, in die der Code integriert wurde.
* Ausnahme: Privat oder firmenintern (ohne Weitergabe) keine Pflicht zur Weitergabe.
* Variabilität: Wie streng der Effekt greift, hängt von der jeweiligen Lizenz ab (Weak vs. Strong).

--
## Weak Copyleft (Begrenzt)

* Der Kompromiss: Brücke zwischen strengem Copyleft und permissiven Lizenzen.
* Dateibezogen: Änderungen an dieser spezifischen Komponente/Bibliothek müssen offengelegt werden.
* Verlinkung erlaubt: Darf oft zusammen mit proprietärer Software genutzt werden (z. B. als dynamische Bibliothek), ohne das Hauptprogramm zu "infizieren".

> Beispiele: LGPL, Mozilla Public License (MPL).

Note:
* Generell zu Weak Copyleft aber speziell MPL: Das "Lego-Prinzip"
    * Stell dir vor, du baust ein Raumschiff aus Lego.
    * Dein Raumschiff ist deine proprietäre Software (geheim).
    * Der Standard-Motor, den du einbaust, ist eine Weak Copyleft Bibliothek (z. B. MPL).
    * Das Prinzip: Solange du den Motor nur benutzt (einbaust), darf dein Raumschiff geheim bleiben. Der Motor bleibt ein eigenständiges Bauteil.
    * Die Pflicht (Der Copyleft-Teil): Wenn du den Motor aufschraubst und verbesserst (z. B. schneller machst), musst du den Bauplan für den verbesserten Motor veröffentlichen. Aber der Bauplan für den Rest des Raumschiffs bleibt dein Geheimnis.
* Fun Fact zu LGPL: Ursprünglich stand die Abkürzung für "Library General Public License".
    * Die Free Software Foundation (FSF) hat sie jedoch ganz bewusst umbenannt, um eine politische Botschaft zu senden:
    * Library (Alt): Der Name klang zu "empfehlend" – als wäre dies die Standard-Lizenz für alle Bibliotheken.
    * Lesser (Neu): Das Wort "Lesser" (Geringer) soll ausdrücken, dass diese Lizenz die Freiheit der Nutzer weniger schützt als die volle GPL.
* Bei LGPL (Lesser GPL) alles nochmal spezieller: Dynamic linking erlaubt, Static linking schon schwieriger, da du die Objektdateien mitliefern müsstest, damit der Nutzer die Bibliothek neu linken kann. Bei LGPL muss gewährleistet sein, dass der Nutzer, die LGPL Datei problemlos austauschen kannst. z.B. eine .dll oder .so. Sobald das nicht mehr geht in einer .EXE oder Binary, hast du schon ein Problem, weil der Code "verschmolzen" wurde. Dadurch müsste ich dem Nutzer meine kompilierten Objekt-Dateien (.o/.obj) bereitstellen, was Reverse Engineering extrem vereinfacht und somit keine Firma möchte mit proprietärem Code. 

--
## Strong Copyleft (Streng)

* Viraler Effekt: Wenn diese Software genutzt oder integriert wird, muss das gesamte entstehende Werk unter derselben Lizenz stehen.
* Keine Mischung: Eine Kombination mit proprietärem (geschlossenem) Code ist in der Regel nicht möglich, ohne diesen ebenfalls offenzulegen.
* Fokus: Schützt die Freiheit der Software am aggressivsten.

> Beispiele: GPL v2/v3, AGPL.

Note:
* GPL: Auslöser der "alles muss offengelegt werden", erst bei Distribution, also der Weitergabe als EXE, ISO, Docker-Image etc., somit ein SaaS-Loophole, da keine Weitergabe
* AGPL: Schließt das SaaS-Loophole, da die Pflicht greift bei "Interaktion über ein Netzwerk" -> Nach dem Zugriff, muss der Cloud-Provider den Source Code offenlegen.

--
## Lizenz-Dschungel Übersicht

<div class="table">

| Permissive | Weak Copyleft | Strong Copyleft |
| --- | --- | --- |
| Mach was du willst.<br><br>MIT<br>Apache 2.0<br>BSD | Änderungen müssen zurückgegeben werden.<br><br>MPL<br>LGPL | Alles muss offengelegt werden.<br><br>GPL v2/v3<br>AGPL |

</div>

Note:
Permissive: Business-freundlich. Copyleft: User-Freedom-freundlich (viral). AGPL: Schließt das Cloud-Loophole.

--
## Wie viele OSI anerkannte Open Source Lizenzen gibt es? ✋

- ... weniger als 10?
<!-- .element: class="fragment" -->
- ... zwischen 10 und 50?
<!-- .element: class="fragment" -->
- ... zwischen 50 und 86?
<!-- .element: class="fragment" -->
- ... über 122?
<!-- .element: class="fragment" -->

Note:
Es sind 123 anerkannte Lizenzen, stand 27.11.2025

---
## Ihr erinnert euch noch an den Open Source Markt?

<section>
<img width="50%" height="100%" src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none;"><img width="50%" height="100%" src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none;">
</section>

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
| 2018 | **MongoDB** | GPLv3 | SSPL (Nicht Open Source) |
| 2019 | **CockroachDB** | Apache | BSL (Business Source) |
| 2021 | **Elastic** | Apache | SSPL / Elastic License |
| 2024 | **Redis** | BSD | RSALv2 / SSPL |

</div>

*Hinweis: Elastic, CockroachDB und Redis ruderten teilweise zurück*

Note:

Wieso AGPL? -> Grund: Um den Begriff "Open Source" wieder offiziell nutzen zu dürfen und Vertrauen zurückzugewinnen.

Mongo:
* 2009 bis 15. Oktober 2018 GPLv3
* 16. Oktober 2018 SSPL

CockroachDB:
* 2015 - Juni 2019 Apache 2.0
* Juni 2019 - BSL 1.1 (Business Source License) - Schutz vor Cloud - "Anti-AWS-Paragraph". Darf genutzt werden, außer kommerzielle SaaS Dienste aka AWS
    * Besonderheit - Nach 3 Jahren, fällt jede Version automatisch zur offenen Apache 2.0 zurück.
    * Zusätzlich Aufteilung in kostenlose Version und Enterprise Version mit weiteren Features
* 18 November 2024 - Keine freie Version mehr, nur noch CockroachDB Software License (proprietär), kein Open Source mehr - Kostenlos nutzbar für Einzelentwickler und Firmen unter 10 Mio. USD Jahresumsatz.

Elastic:
* 2010 - 14. Januar 2021 -> Apache 2.0
* 14 Januar 2021 -> Dual License SSPL + Elastic License (Kein Open Source mehr
* 29 AUgust 2024 -> Dritte Lizenz mit AGPL

Redis: 
* 20.März 2024 wechsel von BSD zu SSPL und RSALv2 (Redis Source Available License).
* Shitstorm, aus Distributionen geworfen worden, Rückkehr mit AGPLv3 am 1.Mai 2025 - Jetzt 3 Lizenzen
* AGPL ist OSI anerkannt, aber Strong Copyleft. Jede Änderung am Code muss offengelegt werden. Somit Hosting wieder möglich.

--

<img src="img/aws-instance-running.png" style="background:none; border:none; box-shadow:none;">

--
## Was ist SSPL / BSL?
### Sie klingen wie Open Source, sind es aber **nicht**.

- **SSPL (Server Side Public License):** Diskriminiert gegen Cloud-Provider. (Verletzt OSI Punkt 6 & 9).
- **BSL (Business Source License):** Proprietär auf Zeit. Heute stark eingeschränkt (Source Available), erst in Zukunft echtes Open Source.

> Das ist kein "Open Source". Das ist **Proprietäre Software**, bei der man den Code lesen darf.

Note:
* SSPL: Der "Giftköder" SSPL: Wer die Software als Service anbietet (SaaS), muss nicht nur den Code der Software selbst offenlegen, sondern auch den Code für das gesamte Management-System drumherum (Backups, Monitoring, User-Verwaltung, Hosting-Infrastruktur).
* BSL: Die neueste, geilste Version gehört uns (proprietär). Die alte Version schenken wir der Community (Open Source). "Change Date" entscheidend. Klassiker: Du darfst die Software nutzen, aber du darfst sie nicht als Managed Service (SaaS) anbieten, der mit uns konkurriert.


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

Note:

* Commons Clause: Der Trick: Der Hersteller nimmt eine echte Open-Source-Lizenz (z.B. Apache 2.0) und klebt am Ende einen Zusatztext dran: "Das hier ist Apache 2.0, ABER du darfst den Code nicht verkaufen."
* Non-Commercial Use Only: Echtes Open Source MUSS kommerzielle Nutzung erlauben. Lizenzen wie die CC-BY-NC (Creative Commons Non-Commercial) oder die neue Lizenz von CockroachDB (kostenlos nur für kleine Firmen) diskriminieren bestimmte Nutzergruppen ("Field of Use Restriction"). Komplette Rechtsunsicherheit - was ist kommerziell, wo fängt es an, wo hört es auf?

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

<img src="img/open-source-blog-post.png" style="background:none; border:none; box-shadow:none;">

--

## 100% Unabhängig! 0% Bullshit!

<img src="img/logo.png" style="background:none; border:none; box-shadow:none;">

Note:

* Vielleicht sagen wir nicht das was ihr hören wollt, aber das was ihr hören und wissen solltet!

---
# Fragen?

Vielen Dank!

