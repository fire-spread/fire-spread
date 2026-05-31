<!--
**fire-spread/fire-spread** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->


# FiRe-Spread

## Ziel des Tools

Das FiRe-Spread berechnet, wie lange ein Vermögen unter Berücksichtigung einer vorgegebenen Sparrate und geplanter Entnahmen ausreicht.

Zusätzlich können folgende Faktoren berücksichtigt werden:

* Regelmäßige und einmalige Einzahlungen
* Regelmäßige und einmalige Ausgaben
* Unterschiedliche Renditen für Depot und Festgeldkonto
* Lebensereignisse wie:

  * Auszahlung privater Lebensversicherungen
  * Beginn staatlicher Rentenzahlungen
* Simulation außergewöhnlich guter oder schlechter Renditejahre
* Näherungsweise Berechnung der Kapitalertragsteuer unter Berücksichtigung des Sparer-Pauschbetrags (ohne Günstigerprüfung)

Ein besonderer Fokus liegt auf einer **nachvollziehbaren und transparenten Berechnung**, sodass Fehler leichter erkannt, gemeldet und korrigiert werden können.

> Hinweis: Eine Safe Withdrawal Rate (SWR) wird weder berechnet noch berücksichtigt.

---

## Anforderungen

* Keine Makros erforderlich
* Unterstützte Tabellenkalkulationsprogramme:

  * PlanMaker (SoftMaker Office)
  * LibreOffice Calc
  * Voraussichtlich auch Microsoft Excel

---

## Annahmen und Rechnerverhalten

### Depotentwicklung

* Während der Entnahmephase erfolgt die Entnahme jeweils zu Jahresbeginn.
* Während der Ansparphase werden Einzahlungen und Verzinsung monatlich berücksichtigt.

### Regelmäßige und einmalige Zahlungen

Zur Vereinfachung werden sämtliche regelmäßigen und einmaligen Einnahmen bzw. Ausgaben als Buchung zum jeweiligen Jahresbeginn behandelt. Dies gilt auch für tatsächlich monatlich ausgezahlte Leistungen wie beispielsweise die gesetzliche Rente.

### Sparer-Pauschbetrag

* Der Sparer-Pauschbetrag wird zunächst vollständig auf die Erträge des Festgeldkontos angewendet.
* Sind die Festgelderträge geringer als der verfügbare Pauschbetrag, wird der verbleibende Betrag auf steuerpflichtige Depoterträge angerechnet.

### Entnahmen

* Entnahmen aus Depot und Festgeldkonto erfolgen stets proportional zum jeweiligen Vermögensanteil.

### Definition „Festgeldkonto“

Mit „Festgeldkonto“ ist allgemein ein Konto mit vergleichsweise stabiler Verzinsung gemeint, beispielsweise:

* Festgeldkonto
* Tagesgeldkonto
* Girokonto
* Geldmarkt-ETF ohne Teilfreistellung
* vergleichbare Anlagen mit weitgehend konstanten Zinserträgen

---

## Nicht berücksichtigte Aspekte

Folgende Themen werden aktuell nicht modelliert:

* Günstigerprüfung
* FIFO-Prinzip beim Verkauf von Wertpapieren
* Sequence-of-Returns-Risk (Reihenfolgerisiko)

  * Kann lediglich stark vereinfacht über „Außergewöhnliche Renditen“ simuliert werden
* Monte-Carlo-Simulationen
* Vorabpauschale

---

## Bekannte Einschränkungen

Der Rechner simuliert stets ab dem **1. Januar des gewählten Startjahres**.

Wird der aktuelle Vermögensstand beispielsweise erst im November erfasst, wird die hinterlegte Sparrate dennoch für das gesamte erste Simulationsjahr berücksichtigt.

Dadurch kann insbesondere im ersten Jahr der Ansparphase eine Überschätzung des Vermögens entstehen.

Der Effekt wird größer:

* je später im Jahr das Vermögen erfasst wird
* je höher die Sparrate ist

Ab dem zweiten Simulationsjahr tritt dieser Effekt nicht mehr auf.

---

## Verbesserungspotenzial

### Fachliche Überprüfung

* Konsistente Verwendung der Fachbegriffe prüfen:

  * Performance vs. Gewinnanteil
  * Nominal vs. Real
  * Brutto vs. Netto

### Validierung der Berechnungen

Insbesondere folgende Spalten sollten überprüft werden:

* `Depot – benötigte Entnahme inkl. Kapitalertragsteuer`
* `Depotwert nach Rendite inkl. Einzahlungen`
* `Gewinn nach Entnahme`

### Steuerliche Optimierung

* Hinweis anzeigen, wenn eine Günstigerprüfung potenziell sinnvoll sein könnte.
* Die jährliche Steuerlast aus Depot- und Festgeldentnahmen wird bereits berechnet und könnte hierfür als Grundlage dienen.

### Benutzerfreundlichkeit

* Kommentare in den Zellen überprüfen und verbessern.
* Nachvollziehbarkeit der Berechnungen weiter erhöhen.

### Gewinnermittlung

* Überprüfung, ob der Gewinnanteil unter Berücksichtigung von Einzahlungen und Entnahmen korrekt ermittelt wird.

### Startjahr der Simulation

Aktuell werden Sparrate und Rendite für das komplette erste Simulationsjahr berücksichtigt, auch wenn der eingegebene Vermögensstand erst später im Jahr erfasst wurde.

Siehe hierzu auch die Hinweise im Abschnitt **Vermögen**.
