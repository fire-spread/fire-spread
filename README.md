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


# 🔥 FiRe-Spread

Ein Excel-Tool zur langfristigen Vermögensplanung im Kontext von **Financial Independence / Retire Early (FIRE)**. Das Tool berechnet, wie lange Depot und Festgeldkonto eine geplante jährliche Entnahme tragen — unter Berücksichtigung von Steuern, Inflation, Sonderereignissen und individuellen Rendite-Szenarien.

Keine Makros. Läuft in LibreOffice Calc, PlanMaker (SoftMaker) und voraussichtlich auch in Microsoft Excel.

---

## Funktionen

- Depot und Festgeldkonto werden **getrennt** geführt, jeweils mit eigener Rendite
- Entnahmen werden immer **proportional** zum aktuellen Stand beider Töpfe aufgeteilt
- Automatische Berechnung der **Kapitalertragssteuer** (inkl. Soli, 30 % Teilfreistellung, konfigurierbarer Sparer-Pauschbetrag)
- Der Sparer-Pauschbetrag wird zuerst gegen Festgeldzinsen verrechnet, der Rest gegen Depot-Gewinne
- Die Sparrate kann **jährlich dynamisch wachsen** (konfigurierbarer Prozentsatz)
- Die Entnahme wächst jährlich automatisch mit der **Inflationsrate** (Kaufkraft bleibt konstant)
- **Einmalige Ereignisse** (z. B. Lebensversicherungsauszahlung, Autokauf) und **regelmäßige Sonderpositionen** (z. B. Rente, Kosten für Krankenversicherung) werden berücksichtigt
- Für einzelne Zeiträume lässt sich eine **abweichende Rendite** hinterlegen, um gute oder schlechte Börsenphasen zu simulieren
- Ergebnis wird sowohl **nominal als auch real** (inflationsbereinigt) ausgegeben

---

## Schnellstart

1. Datei in LibreOffice Calc, PlanMaker oder Excel öffnen
2. Im Tabellenblatt **Parameter** die individuellen Parameter eintragen:
   - Startjahr und Monat der Vermögenserfassung
   - Depotwert, davon Gewinnanteil (Kursgewinne)
   - Festgeldstand
   - Monatliche Sparrate (Depot + Festgeld)
   - FIRE-Startjahr und geplante Jahresentnahme
3. Ergebnis direkt oben rechts im Parameter-Sheet ablesen

Das Tabellenblatt **FIRE** enthält die vollständige Jahresrechnung und kann zur Nachvollziehbarkeit eingesehen werden.

---

## Was zu beachten ist

- Die **Entnahme** wird als heutiger Kaufkraftwert (real) eingegeben — das Tool rechnet die jährlich steigende Nominalentnahme automatisch aus
- Renditen, Sparrate und Inflationsrate sind **nominal** anzugeben
- Entnahmen und Sonderpositionen gelten vereinfacht immer als **Jahresbeginn-Buchung**
- Den **Gewinnanteil des Depots** (Kursgewinne vs. eingezahltes Kapital) beim Start korrekt eintragen — er ist Grundlage der Steuerberechnung
- Einmalige Sonderpositionen (z. B. Auszahlungen, Einmalkäufe) fließen immer ins **Festgeldkonto**, nicht ins Depot
- Wird der Vermögensstand **nicht zum Jahresbeginn** erfasst, den aktuellen Monat im Parameter-Sheet angeben — sonst werden Sparrate und Verzinsung fälschlicherweise für das gesamte Startjahr hochgerechnet
- Der eingegebene Depotwert muss immer dem **tatsächlichen Stand des angegebenen Monats** entsprechen — also inklusive aller Kursgewinne und geleisteten Sparraten seit Januar. Wer im Oktober erfasst und trotzdem den Januar-Stand einträgt, unterschätzt sein Vermögen um 9 Monate Rendite und Sparrate, was das Ergebnis um mehrere Jahre verfälschen kann

---

## Was das Tool nicht macht

| Feature | Status |
|---|---|
| Safe Withdrawal Rate (SWR) | ❌ nicht enthalten |
| Günstigerprüfung (Einkommensteuer) | ❌ nicht enthalten |
| FiFo-Prinzip beim Wertpapierverkauf | ❌ nicht enthalten |
| Renditereihenfolgerisiko (Sequence of Returns Risk) | ⚠️ nur **sehr grob** über Rendite-Szenarien simulierbar |
| Monte-Carlo-Simulation | ❌ nicht enthalten |
| Vorabpauschale auf Fonds/ETFs | ❌ nicht enthalten |

---

## Annahmen & Rechnerverhalten

- Die Entnahme erfolgt jeweils zum **Jahresbeginn**
- Sonstige Ein- und Auszahlungen (Rente, Einmalbeträge etc.) gelten vereinfacht ebenfalls als Jahresbeginn-Buchung
- Die Steuerberechnung ist eine **Annäherung**: Kapitalertragssteuer auf Entnahmen unter Berücksichtigung des Sparer-Pauschbetrags, ohne Günstigerprüfung
- Mit „Festgeldkonto" ist ein beliebiges liquides Konto gemeint (Giro, Tagesgeld, Festgeld — auch ein zweites Depot mit anderer Rendite ist möglich)

---

## Tabellenblätter

| Blatt | Beschreibung |
|---|---|
| **Parameter** | Alle Eingaben und das Ergebnis auf einen Blick |
| **FIRE** | Vollständige Jahresrechnung (Spalte für Spalte nachvollziehbar) |
| **Historie** | Changelog |

---

## Fehler melden / Verbesserungen vorschlagen

Berechnungsfehler, Formel-Bugs oder Verbesserungsideen bitte als [Issue](../../issues) melden — idealerweise mit dem betroffenen Jahr, den verwendeten Parametern und dem erwarteten vs. tatsächlichen Ergebnis. Da alle Berechnungen im Tabellenblatt FIRE transparent und zeilenweise nachvollziehbar sind, lassen sich Fehler gezielt eingrenzen.

---

## Lizenz

Dieses Tool steht unter der Lizenz **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

Das bedeutet:
- ✅ Weitergabe und Weiterverbreitung erlaubt
- ✅ Bearbeitung und Anpassung erlaubt
- ✅ Nutzung für private und kommerzielle Zwecke erlaubt
- ⚠️ **Der Urheber muss genannt werden** — bei Weitergabe oder Veröffentlichung sind anzugeben: Name/Pseudonym des Urhebers, Quelle (Link zum Original-Repository), Link zur Lizenz sowie ein Hinweis auf vorgenommene Änderungen

Vollständiger Lizenztext: [creativecommons.org/licenses/by/4.0](https://creativecommons.org/licenses/by/4.0/deed.de)

---

## Haftungsausschluss

Dieses Tool wird **ohne jegliche Gewährleistung** bereitgestellt — weder ausdrücklich noch stillschweigend. Die Berechnungen basieren auf vereinfachten Annahmen und dienen ausschließlich der persönlichen Orientierung.

Der Urheber übernimmt u.a. **keine Haftung** für:
- Fehler oder Ungenauigkeiten in den Berechnungen
- Finanzielle Entscheidungen, die auf Basis dieses Tools getroffen werden
- Direkte oder indirekte Schäden, die aus der Nutzung entstehen — einschließlich entgangener Gewinne oder Vermögensverluste

Das Tool ersetzt **keine individuelle Steuer- oder Finanzberatung**. Für verbindliche Aussagen zur persönlichen Finanzplanung wende dich an einen zugelassenen Steuerberater oder Finanzberater.

Die Nutzung erfolgt **ausschließlich auf eigenes Risiko**.



