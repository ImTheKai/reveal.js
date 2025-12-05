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

Note:

- Heute befassen wir uns mit dem Thema 'Etikettenschwindel' und der Frage: Wie Open Source ist deine Datenbank wirklich?

---

## Umfrage ✋

> Wer kennt mich?

Note:

- Fangen wir mit einer kleinen Umfrage zum Warmwerden an. Einfach mal die Hand heben: Wer weiß, wer ich bin?

--

<img src="img/who-we-are.png" style="background:none; border:none; box-shadow:none;">

--

<img src="img/number-of-database-environments.png" style="background:none; border:none; box-shadow:none;">

--

<img src="img/customer-base.png" style="background:none; border:none; box-shadow:none;">

---
## Umfrage ✋

> Wer von euch nutzt Open Source Datenbanken?

- ... MySQL? PostgreSQL? MongoDB? Redis?
<!-- .element: class="fragment" -->

Achtung: Mindestens zwei der genannten sind **nicht mehr** bzw waren **nicht immer** Open Source.
<!-- .element: class="fragment warning-box" -->

---
## Umfrage ✋

> Wer glaubt zu wissen was Open Source ist? 

---
## Was ist "Open Source"?

Wenn man 5 Leute fragt, bekommt man 6 Antworten.

1. "Kostet nichts." (Falsch aka "Jein")
<!-- .element: class="fragment" -->
2. "Ich kann den Code lesen." (Unzureichend)
<!-- .element: class="fragment" -->
3. "Ich kann es auf GitHub finden." (Gefährlich)
<!-- .element: class="fragment" -->

Achtung: Mindestens eine Plattform auf dieser Folie ist nicht Open Source!
<!-- .element: class="fragment warning-box" -->

Note:
* Wer im Raum hat schonmal versucht für "Open Source" zu bezahlen und ist dafür zu seinem Chef oder Finanz Team gegangen? Das existiert dort gar nicht. 

--

<img src="img/github-isnt-open-source.png" style="background:none; border:none; box-shadow:none;">

--
# "Kostet nichts?!"

<img src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none; width:1300px;">

Note:
* 2025 ca. 38 Milliarden
* Der Markt soll bis 2032 auf über 118 Milliarden anwachsen. 

--

## Der Siegeszug

*Laut db-engines.com hat Open Source im Jahr 2021 kommerzielle Datenbanken in der Popularität überholt.*

<img src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none; width:1300px;">

--

## Community und Freiheit

--

## Community

"Collaborating with a community is about more than developing code. Collaboration is about the freedom to ask questions and offer improvements - that’s the open source way and the power of the open organization."

https://www.redhat.com/en/topics/api

Note:
* SUSE/RedHat waren mit die Ersten, die "Open Source Software genommen haben und es auf einem Medium vertrieben haben und dazu eine Telefonnummer mit auf die Box gepackt haben für Support und Probleme.

--
## Free Speech vs. Free Beer

> "Free software is a matter of liberty, not price. To understand the concept, you should think of 'free' as in 'free speech', not as in 'free beer'."
>
> -- Richard Stallman --

In der **Open Source (OSI Definition)** geht es um **Freiheiten**, nicht um den Preis.

Note:
* Wie frei ist ein Freibier? Ziemlich eingeschränkt, nur zu dem aktuellen Zeitpunkt. Kein mitnehmen, weiterverkaufen, aufheben für später etc. 

---
## Die OSI Definition (TL;DR)

Damit ein Etikettenlabel **echt** ist, müssen (unter anderem) diese Bedingungen erfüllt sein:

> **Freie Weitergabe:** Ja, man darf es kopieren und verkaufen. Keine Einschränkung.
<!-- .element: class="fragment" -->
> **Offener Quellcode:** Keine Blackboxen. Alles muss offen liegen.
<!-- .element: class="fragment" -->
> **Forks erlaubt:** Gefällt dir die Richtung nicht? Dann darfst du es selbst besser machen.
<!-- .element: class="fragment" -->
> **Keine Diskriminierung:** Egal ob Militär, Atomkraft oder Cloud-Konkurrenz – jeder darf es nutzen.
<!-- .element: class="fragment" -->

Merkt euch den letzten Punkt ("Keine Diskriminierung"). Der wird gleich wichtig.
<!-- .element: class="fragment warning-box"-->

Note:
* Die Open Source Initiative (OSI) ist der TÜV für Lizenzen. Sie haben die "Open Source Definition" (OSD) geschrieben, die aus 10 Kriterien besteht.

--
## Umfrage ✋

> Wie viele OSI anerkannte Open Source Lizenzen gibt es? 

- ... weniger als 10?
<!-- .element: class="fragment" -->
- ... zwischen 10 und 50?
<!-- .element: class="fragment" -->
- ... zwischen 50 und 86?
<!-- .element: class="fragment" -->
- ... über 122?
<!-- .element: class="fragment" -->

Es sind 123 Lizenzen!
<!-- .element: class="fragment warning-box"-->

Note:
Es sind 123 anerkannte Lizenzen, stand 27.11.2025

---
## Der Lizenz-Dschungel

Wir müssen kurz technisch werden. Es gibt zwei Hauptkategorien:

* Permissive (erlaubend) 
<!-- .element: class="fragment" -->
* Non-permissive (beschränkend)
<!-- .element: class="fragment" -->

Note:
* permissiv aka freizügig oder erlaubend
* nicht permissiv aka restriktiv oder beschränkend

--
## Permissive (Erlaubend)

* Maximaler Freiraum: Erlaubt fast alles – Nutzung, Änderung und Verbreitung (auch in kommerzieller/geschlossener Software).
* Minimale Pflichten: Meist muss nur der Urheberrechtsvermerk (Copyright) und der Lizenztext beibehalten werden.
* Kein Copyleft: Änderungen müssen nicht wieder veröffentlicht werden.

> Beispiele: MIT, BSD, Apache 2.0

Note:

* "Stell dir vor, ich schenke dir eine riesige Kiste voller Legosteine. Ich sage dazu: 'Mach damit, was du willst.'
    - Du baust ein Auto daraus? Super.
    - Du verkaufst das Auto? Viel Erfolg.
    - Der Clou: Du darfst die Steine mit Superkleber zusammenkleben (Closed Source), sodass niemand mehr sieht, wie du es gebaut hast. Du musst mir nichts zurückgeben, außer einem kleinen Zettel im Handschuhfach, aufdem steht: 'Steine waren ursprünglich von Kai'."

* MIT: Massachusetts Institute of Technology
* BSD: University of California, Berkeley - Berkeley Software Distribution
* Apache 2.0: Besonderheit - Patent Klausel - Schützt Nutzer vor dem verklagt werden durch den Urheber vor Patentverletzungen

### Die Analogie: "Die Kiste mit dem Schutzschild"
(Unterschied zu MIT: Rechtssicherheit)

"Stellt euch vor, ich schenke euch wieder die Kiste Lego (wie bei MIT). Aber bei der MIT gibt es ein Restrisiko: Vielleicht habe ich auf die **Form** der Noppen ein Patent. Du baust dein Auto, wirst reich, und dann komme ich und verklage dich wegen Patentverletzung.

**Bei der Apache-Kiste liegt deshalb ein Vertrag bei:**
1.  **Der Schutzbrief (Patent Grant):** 'Ich verspreche, dich nie wegen Patenten an diesen Steinen zu verklagen.' (Du bist sicher).
2.  **Der Selbstzerstörungsknopf (Retaliation Clause):** 'Wenn DU aber jemanden wegen Patenten an diesen Steinen verklagst, verlierst du sofort das Recht, meine Steine zu nutzen.'

Das ist der **Waffenstillstand**, den Großkonzerne brauchen, um sicher zusammenzuarbeiten."

--

## Der Lizenz-Dschungel

Wir müssen kurz technisch werden. Es gibt zwei Hauptkategorien:

* Permissive (erlaubend) 
* Non-permissive (beschränkend)

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
## Was ist der Copyleft-Effekt?

* Grundprinzip: Verbesserungen müssen der Allgemeinheit zur Verfügung gestellt werden („Geben und Nehmen“).
* Umfang: Dies betrifft sowohl direkte Änderungen am Quellcode als auch Produkte, in die der Code integriert wurde.
* Ausnahme: Privat oder firmenintern (ohne Weitergabe) keine Pflicht zur Weitergabe.
* Variabilität: Wie streng der Effekt greift, hängt von der jeweiligen Lizenz ab (Weak vs. Strong).

--
## Weak Copyleft (Leicht Begrenzt)

* Der Kompromiss: Brücke zwischen strengem Copyleft und permissiven Lizenzen.
* Dateibezogen: Änderungen an dieser spezifischen Komponente/Bibliothek müssen offengelegt werden.
* Verlinkung erlaubt: Darf oft zusammen mit proprietärer Software genutzt werden (z. B. als dynamische Bibliothek), ohne das Hauptprogramm zu "infizieren".

> Beispiele: LGPL, Mozilla Public License (MPL).

Note:
### 1. MPL (Das Lego-Prinzip / Datei-Level)
* Generell zu Weak Copyleft aber speziell MPL: Das "Lego-Prinzip"
    * Stell dir vor, du baust ein Raumschiff aus Lego.
    * Dein Raumschiff ist deine proprietäre Software (geheim).
    * Der Standard-Motor, den du einbaust, ist eine Weak Copyleft Bibliothek (z. B. MPL).
    * Das Prinzip: Solange du den Motor nur benutzt (einbaust), darf dein Raumschiff geheim bleiben. Der Motor bleibt ein eigenständiges Bauteil.
    * Die Pflicht (Der Copyleft-Teil): Wenn du den Motor aufschraubst und verbesserst (z. B. schneller machst), musst du den Bauplan für den verbesserten Motor veröffentlichen. Aber der Bauplan für den Rest des Raumschiffs bleibt dein Geheimnis.

### 2. LGPL (Der Austausch-Zwang / Library-Level)
Hier wird es komplizierter. Die LGPL will nicht nur den Code, sie will die **Freiheit des Nutzers, den Motor auszutauschen**.

* **Szenario A (Erlaubt - Dynamisch):** Du baust den Motor so ein, dass man ihn einfach herausklicken und durch einen neueren (z.B. schnelleren) Motor ersetzen kann. (In der IT: Dynamic Linking / .dll / .so). -> Alles super.
* **Szenario B (Problematisch - Statisch):** Du verklebst den Motor fest mit dem Rumpf (Static Linking), sodass man ihn nicht mehr tauschen kann, ohne das Schiff zu zerstören.
    * **Die Folge:** Das ist unter LGPL verboten, *außer* du lieferst dem Nutzer ein "Lösungsmittel" und die Einzelteile (Objekt-Dateien), damit er das Schiff selbst neu zusammenkleben kann.
    * **Fazit:** LGPL ist in modernen Sprachen (Go, Rust), die gerne "alles verkleben", extrem nervig. MPL ist da entspannter.

--
## Strong Copyleft (Streng Begrenzt)

* Viraler Effekt: Wenn diese Software genutzt oder integriert wird, muss das gesamte entstehende Werk unter derselben Lizenz stehen.
* Keine Mischung: Eine Kombination mit proprietärem (geschlossenem) Code ist in der Regel nicht möglich, ohne diesen ebenfalls offenzulegen.
* Fokus: Schützt die Freiheit der Software am aggressivsten.

> Beispiele: GPL v2/v3, AGPL.

Note:

**1. GPL (Der virale Reaktor)**
Stell dir vor, du verbaust einen **GPL-Reaktor** in dein Raumschiff.
Dieser Reaktor ist extrem mächtig, hat aber eine spezielle physikalische Eigenschaft:
* Er strahlt eine Energie aus, die **jedes Material, das ihn berührt, transparent macht**.
* **Die Konsequenz:** Sobald du diesen Reaktor fest mit deinem Rumpf verbindest (Linking), wird dein **gesamtes Raumschiff aus Glas**.
* Du kannst keine Geheimwaffen oder versteckte Cockpits mehr haben. Wer den Reaktor nutzt, muss der Welt den Bauplan für das **komplette Schiff** zeigen. Es gilt: Ganz oder gar nicht.

**2. AGPL (Das Schließen des 'Fernrohr-Schlupflochs')**
Hier haben die Cloud-Provider (wie AWS) einen Trick gefunden:
* **GPL-Regel:** 'Du musst den Bauplan nur zeigen, wenn du das Schiff an jemanden verkaufst oder verleihst (Distribution).'
* **Der Cloud-Trick:** AWS behält das Schiff einfach bei sich im Hangar. Sie lassen dich nur durch ein **Fernrohr** (Internet/API) zuschauen, wie es fliegt. Da das Schiff den Hangar nie verlässt, mussten sie den Bauplan nicht zeigen.
* **Die AGPL-Regel:** Sie sagt: 'Nein! Sobald du jemanden auch nur durchs Fernrohr (Netzwerk) mit dem Schiff interagieren lässt, musst du den Bauplan offenlegen.' Das zwingt AWS dazu, die Karten auf den Tisch zu legen."

--
## Lizenz-Dschungel Übersicht

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

<!-- GRÜN: PERMISSIVE -->
<div class="license-box l-green fragment fade-up">
  <div class="license-icon">🟢</div>
  <div class="license-content">
    <strong>Permissive (Freie Fahrt)</strong><br>
    "Mach was du willst." Keine Einschränkung für Proprietäres.<br>
    <em>MIT, BSD, Apache 2.0</em>
  </div>
</div>

<!-- GELB: WEAK COPYLEFT -->
<div class="license-box l-yellow fragment fade-up">
  <div class="license-icon">🟡</div>
  <div class="license-content">
    <strong>Weak Copyleft (Schulterblick)</strong><br>
    "Dateien getrennt halten." Änderungen an Libs zurückgeben.<br>
    <em>MPL, LGPL</em>
  </div>
</div>

<!-- ORANGE: STRONG COPYLEFT -->
<div class="license-box l-orange fragment fade-up">
  <div class="license-icon">🟠</div>
  <div class="license-content">
    <strong>Strong Copyleft (Vorfahrt beachten)</strong><br>
    "Viraler Effekt." Infiziert das gesamte Projekt bei Kontakt.<br>
    <em>GPL v2/v3, AGPL</em>
  </div>
</div>

Nochmal schnell weg bevor die Ampel auf **rot** wechselt!
<!-- .element: class="fragment warning-box"-->

---
## Ihr erinnert euch noch an den Open Source Markt?

<div style="display:flex; gap:30px; align-items:center; justify-content:space-between;">
  <img width="50%" height="100%" src="img/db-engine-db-trend-numbers.png" style="background:none; border:none; box-shadow:none;">
  <img width="50%" height="100%" src="img/open-source-services-market-size-by-service-2024-2032.png" style="background:none; border:none; box-shadow:none;">
</div>

--
## Aber dieser absehbare Erfolg weckte Begehrlichkeiten.

---
## Das Lockvogelangebot

<!-- Flex-Container für 2 Spalten -->
<div style="display: flex; align-items: center; justify-content: space-between; gap: 40px; margin-top: 50px;">

  <div style="width: 55%; text-align: left;">
    <p>Wie fängt man Entwickler?</p>
    <ol>
      <li class="fragment" style="margin-bottom: 15px;">
        Baut eine coole Datenbank.
      </li>
      <li class="fragment" style="margin-bottom: 15px;">
        Lizenziert sie unter <b>Apache 2.0</b> (maximale Adoption).
      </li>
      <li class="fragment" style="margin-bottom: 15px;">
        <b>Die Falle:</b> Verlangt ein CLA (Copyright Transfer).<br>
        <small><i>"Nur für die Rechtssicherheit, versprochen!" 😉</i></small>
      </li>
      <li class="fragment" style="margin-bottom: 15px;">
         Wartet, bis AWS/Google/Azure sie als Service anbieten.
      </li>
      <li class="fragment" style="color: #ff4444; font-weight: bold; margin-top: 25px;">
        PANIK! "Die Cloud Provider stehlen unseren Umsatz!" <br>
        <small>(Gut, dass wir dank CLA alle Rechte haben, um die Lizenz zu ändern!)</small>
      </li>
    </ol>
  </div>

  <!-- Rechte Spalte: Bild (40% Breite) -->
  <div style="width: 40%;">
    <img src="img/aws-surfing.webp" 
         class="fragment" 
         style="width: 70%; border-radius: 15px; box-shadow: 0 10px 30px rgba(0,0,0,0.5); transform: rotate(2deg);">
  </div>

</div>

Note:

* Wenn die Community Rechte am Code behält, müsste der Hersteller jeden einzelnen Contributor fragen, ob er der Lizenzänderung zustimmt. Hat er aber dank CLA alle Rechte eingesammelt, kann er alleine entscheiden.

---
## Die Timeline des "Verrats"
### Beispiele von Datenbanken, die ihre Lizenz änderten:

<div class="table">

| Jahr | Datenbank | Von | Zu |
|---|---|---|---|
| 2018 | **MongoDB** | AGPLv3 | SSPL (Nicht Open Source) |
| 2019 | **CockroachDB** | Apache | BSL (Business Source) |
| 2021 | **Elasticsearch** | Apache | SSPL / Elastic License |
| 2024 | **Redis** | BSD | RSALv2 / SSPL |

</div>

*Hinweis: Elastic und Redis ruderten teilweise zurück*

Note:

Mongo:
* 2009 bis 15. Oktober 2018 AGPLv3
* 16 Oktober 2018 SSPL

CockroachDB:
* 2015 - Juni 2019 Apache 2.0
* Juni 2019 - BSL 1.1 (Business Source License) ist nicht Open Source nach OSI definition - Schutz vor Cloud - "Anti-AWS-Paragraph". Darf genutzt werden, außer kommerzielle SaaS Dienste aka AWS
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
* Die SSPL wurde in 2018 von MongoDB selbst erstellt und eingeführt.

* GPL / AGPL: "Zeig mir den Code der Anwendung." (AWS: "Kein Problem, hier ist die unveränderte DB.")
* SSPL: "Zeig mir den Code deiner gesamten Cloud-Infrastruktur." (AWS: "Niemals!")

* SSPL: Der "Giftköder" SSPL: Wer die Software als Service anbietet (SaaS), muss nicht nur den Code der Software selbst offenlegen, sondern auch den Code für das gesamte Management-System drumherum (Backups, Monitoring, User-Verwaltung, Hosting-Infrastruktur).
* BSL: Die neueste, geilste Version gehört uns (proprietär). Die alte Version schenken wir der Community (Open Source). "Change Date" entscheidend. Klassiker: Du darfst die Software nutzen, aber du darfst sie nicht als Managed Service (SaaS) anbieten, der mit uns konkurriert.
* EDas Museumsstück (Nur gucken, nicht anfassen) aka GPL/AGPL vs sind nicht deine Steine. Du hast sie nur geliehen bekommen – mit strengen Auflagen, wem du sie zeigen darfst.

--

## Der Lizenz-Dschungel (inklusive Rotphase)
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

<!-- GRÜN: PERMISSIVE -->
<div class="license-box l-green">
  <div class="license-icon">🟢</div>
  <div class="license-content">
    <strong>Permissive (Freie Fahrt)</strong><br>
    "Mach was du willst." Keine Einschränkung für Proprietäres.<br>
    <em>MIT, BSD, Apache 2.0</em>
  </div>
</div>

<!-- GELB: WEAK COPYLEFT -->
<div class="license-box l-yellow">
  <div class="license-icon">🟡</div>
  <div class="license-content">
    <strong>Weak Copyleft (Schulterblick)</strong><br>
    "Dateien getrennt halten." Änderungen an Libs zurückgeben.<br>
    <em>MPL, LGPL</em>
  </div>
</div>

<!-- ORANGE: STRONG COPYLEFT -->
<div class="license-box l-orange">
  <div class="license-icon">🟠</div>
  <div class="license-content">
    <strong>Strong Copyleft (Vorfahrt beachten)</strong><br>
    "Viraler Effekt." Infiziert das gesamte Projekt bei Kontakt.<br>
    <em>GPL v2/v3, AGPL</em>
  </div>
</div>

<!-- ROT: PROPRIETÄR -->
<div class="license-box l-red">
  <div class="license-icon">🔴</div>
  <div class="license-content">
    <strong>Fake Open Source (Mautstelle)</strong><br>
    "Source Available." Diskriminiert Nutzung (Cloud/SaaS).<br>
    <em>SSPL, BSL, RSAL</em>
  </div>
</div>

---
## Warum sollte mich das interessieren?

*"Ich bin ja kein Cloud Provider, mir doch egal?!"*

❌ Falsch.
<!-- .element: class="fragment warning-box" -->

<ol>
  <li class="fragment" style="margin-bottom: 20px;">
    <strong>Vendor Lock-in:</strong> Du bist dem Hersteller ausgeliefert. Preiserhöhungen? Pech gehabt!
  </li>
  <li class="fragment" style="margin-bottom: 20px;">
    <strong>Lizenz-Compliance:</strong> Darf ich das in meiner SaaS-App nutzen? Brauche ich Anwälte?
  </li>
  <li class="fragment">
    <strong>Tod der Community:</strong> Externe Contributor hören auf. Das Ökosystem stirbt oder spaltet sich.
  </li>
</ol>

<!-- DAS NEUE ELEMENT: Die rote Box -->
  <div class="fragment" style="
      margin-top: 30px;
      border: 3px solid #ff4444;
      background: rgba(255, 68, 68, 0.1);
      border-radius: 15px;
      padding: 20px;
      box-shadow: 0 0 20px rgba(255, 0, 0, 0.2);
  ">
    <h3 style="color: #ff4444; margin: 0 0 10px 0;">Aktuelles Beispiel: Redis vs. Valkey</h3>
    <ul style="font-size: 0.8em; list-style-type: '⚠️  ';">
      <li><b>37.5% der Contributor</b> verließen Redis nach dem Lizenzwechsel.</li>
      <li>Valkey wuchs in 18 Monaten von 18 auf <b>49 Contributor</b>.</li>
      <li>Entwicklungstempo 2025:<br>
          * Redis: ~42 PRs/Monat <br>
          * Valkey: <b>~80 PRs/Monat</b> 🚀
      </li>
    </ul>
  </div>
</section>

Note:

* Valkey numbers are for the core server part, not the whole project, as there we have above 150+ contributors. 

---
## Die Reaktion: Forks!
> Die Community lässt sich das nicht gefallen.
<!-- .element: class="fragment" -->

- Elasticsearch ➔ Lizenzänderung ➔ OpenSearch (AWS/Community)
<!-- .element: class="fragment" -->
- Redis ➔ Lizenzänderung ➔ Valkey (Linux Foundation)
<!-- .element: class="fragment" -->
- MySQL ➔ Oracle Kauf ➔ MariaDB / Percona Server for MySQL
<!-- .element: class="fragment" -->
- MongoDB ➔ Lizenzänderung ➔ Percona Server for MongoDB (Enterprise Features und Backup Tools - SSPL weiterhin aktiv)
<!-- .element: class="fragment" -->
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

--

### Geheimtipp Nr. 5 -  Der ultimative Datenbank-Check
howfuckedismydatabase.com
<!-- .element: class="warning-box" -->

<img src="img/howfuckedismydatabase.png" style="background:none; border:none; box-shadow:none;">
 
--
<img src="img/mysql_clicked.png" style="background:none; border:none; box-shadow:none;">
--
<img src="img/mysql-clicked2.png" style="background:none; border:none; box-shadow:none;">
--
<img src="img/excel_clicked.png" style="background:none; border:none; box-shadow:none;">
--
<img src="img/excel-clicked2.png" style="background:none; border:none; box-shadow:none;">
--
<img src="img/msaccess_clicked.png" style="background:none; border:none; box-shadow:none;">
--
<img src="img/msaccess-clicked2.png" style="background:none; border:none; box-shadow:none;">
 
---
# Fazit

--

1. **Namen sind Schall und Rauch.**
   > Nur weil Open Source drauf steht, muss das noch lange nicht stimmen.

2. **Source Available ≠ Open Source.**
   > *Die OSI hat offiziell bestätigt: Die SSPL (MongoDB) ist KEINE Open Source Lizenz, egal wie oft der Begriff im Marketing fällt.*

3. **Vermeidet Lock-in.**
   > *HashiCorp (Terraform) zeigte 2023, wie schnell eine Lizenz kippen kann. Überlegt vorher, welche Software ihr einsetzt.*

Bleibt kritisch. Bleibt frei.
<!-- .element: class="fragment warning-box"-->

Note:

* Akt 1: Der Standard (Bis August 2023)
    - Terraform war der absolute Industriestandard für "Infrastructure as Code" (IaC).
    - Riesiges Ökosystem
    - Lizenz: MPL 2.0 (Weak Copyleft / Open Source) zu BSL gewechselt (Keine Produkte mehr, die mit Terraformi/Hashicorp konkurieren"
    - Definition von Konkurenz ist schwammig. 
    - Der Vertrauensbruch: HashiCorp hatte jahrelang versichert, Terraform bleibe Open Source.

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

#### Wo finde ich die Präsentation?

<img src="img/qr-code-to-presentation.png" style="background:none; border:none; box-shadow:none;">

# Vielen Dank!

Note:

* Deutsch und Englisch je nach Browser Locale verfügbar
