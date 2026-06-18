# Jailbreak – Claude Fable 5 / Mythos 5 (12. Juni 2026)

## Was ist ein Jailbreak?

Im KI-Kontext: das gezielte Umgehen oder Brechen der Safety-Guardrails eines Modells durch spezifische Prompts, sodass es Inhalte ausgibt, die es eigentlich verweigern würde (z. B. Anleitungen zu Waffenbau, Exploits, schädlichem Code). Klassische Techniken sind Rollenspiel-Prompts („DAN"), Token-Smuggling, verschachtelte Übersetzungen oder Codierung. Auslöser ist meist ein konstruiertes Prompt, das das Modell dazu bringt, seine eigenen Richtlinien zu ignorieren. Wichtig: „perfekte" Jailbreak-Resistenz ist laut Anthropic für **kein** Modell möglich — Guardrails sind probabilistisch.

## Fable 5 vs. Mythos 5 — wichtig vorab

Zwei verschiedene Modelle, oft verwechselt:

- **Claude Fable 5** — öffentliches Modell (seit 9. Juni 2026), mit stärkeren Guardrails. Bei Cybersecurity-Anfragen fällt es auf Claude Opus 4.8 zurück.
- **Claude Mythos 5** — dasselbe Basismodell, aber mit **gelockerten** Guardrails in Cybersecurity-Bereichen. Nur für geprüfte Partner via **Project Glasswing** (Cyberverteidiger, kritische Infrastruktur). Laut Anthropic kann Mythos neu veröffentlichte Schwachstellen (N-days) in *Stunden statt Wochen* zu funktionierenden Exploits machen — „a lone operator can now turn a month's worth of patches into working exploits in a single afternoon."

## Der Vorfall — zwei konkurrierende Lesarten

Am **12. Juni 2026, 17:21 ET**, erhielt Anthropic eine Exportkontroll-Direktive des US Commerce Department (Secretary Howard Lutnick). Sie verlangte, den Zugriff von **ausländischen Staatsbürgern** — auch außerhalb der USA, inklusive ausländischer Anthropic-Mitarbeiter — auf beide Modelle zu suspendieren. Da Anthropic die Nationalität von API-Nutzern nicht zuverlässig bestimmen kann, schaltete es die Modelle **global für alle** Kunden ab. Erstmals nutzte die US-Regierung Export-Control-Authority für einen Recall kommerzieller KI.

### Lesart A — Anthropic: „defensive Code-Wartung, kein Jailbreak"

Anthropic selbst nennt die Aktion ein „Missverständnis". Die Regierung habe nur „verbal evidence of a potential narrow, non-universal jailbreak" geteilt, das im Kern daraus bestehe, das Modell zu bitten, „a specific codebase to read and fix any software flaws". Das sei eine alltägliche defensive Cybersecurity-Aufgabe, die auch OpenAIs GPT-5.5 erfüllt und die Verteidiger täglich nutzen. Die gefundenen Schwachstellen seien „a small number of previously known, minor vulnerabilities". Würde man diesen Standard auf die Branche anwenden, „would essentially halt all new model deployments for all frontier model providers."

### Lesart B — Regierung/Amazon: gezielter Jailbreak-Versuch

Berichte von WSJ, Reuters und The Information (Update vom 13. Juni) zeichnen ein anderes Bild:

- **Amazon-CEO Andy Jassy** meldete Bedenken ans Weiße Haus. Laut WSJ hatte Amazon „*a series of prompts*" verwendet, um **Fable 5** dazu zu bringen, Informationen preiszugeben, „*that could be used to aid cyberattacks and was supposed to be off-limits*" — also gezielte Guardrail-Umgehung, nicht alltägliche Code-Wartung.
- **David Sacks** (Co-Chair, President's Council of Advisors on Science and Technology) schrieb auf X: Anthropic habe *geweigert*, einen Jailbreak zu fixen, den „a highly credible trusted partner of both Anthropic and the USG" gemeldet habe, und das Consumer-Modell über Sicherheit gestellt.
- **Semafor** (14. Juni): Die Entscheidung sei auch durch Befürchtung motiviert, Mythos 5 sei durch eine **china-nahe Gruppe** genutzt worden. Wer, wie und über welchen Zugang — unklar.

Sicherheitsforscherin **Katie Moussouris**, die den Regierungsbericht einsehen konnte, widerspricht der Schwere-Einstufung: kein Hack, sondern legitimer Defensive-Use-Case.

## War es nun ein Jailbreak oder nicht?

Ehrliche Antwort: das hängt davon ab, welcher Quelle man folgt. Die Diskrepanz liegt vermutlich in der Prompt- Konstruktion begründet — ein einfaches `fix this code` ist defensiver Standard, eine *Reihe* konstruierter Prompts, die gezielt off-limits-Informationen ziehen, ist ein Jailbreak-Versuch. Anthropic und Moussouris erzählen Lesart A, Regierung und WSJ erzählen Lesart B. Dass Anthropic die Regierungsauffassung öffentlich „Missverständnis" nennt, während Sacks Anthropic öffentlich vorwirft, Sicherheit zu ignorieren, zeigt: hier geht es auch um Politik, nicht nur um Technik.

## Gefahren sehr mächtiger Modelle

- **Offensive Cybersecurity-Fähigkeiten**: Mythos kann N-days in Stunden zu Exploits machen — Demokratisierung von Angriffen bei sinkendem Skill-Level.
- **Dual-Use**: Dieselbe Fähigkeit (Schwachstellen finden) ist defensiv wertvoll und offensiv missbrauchbar — Trennung oft nicht sauber möglich.
- **Nicht determinierbar**: Guardrails sind probabilistisch; **alle** Modelle lassen sich mit genug Aufwand jailbreaken. „Perfect jailbreak resistance is not possible".
- **Exportkontroll-Präzedenz**: Erstmalige Nutzung von Export-Control-Authority gegen kommerzielle KI. Vergleichbar mit den „Crypto Wars" der 1990er (starke Verschlüsselung als Munition eingestuft) — damals schwächte die US-Politik die eigene Industrie und trieb Technologie ins Ausland.
- **Kill-Switch-Risiko**: Vendor muss Zugang in Echtzeit entziehen können, wenn eine Regierung es verlangt — bereits getroffene Vorkehrungen wie 30-Tage-Datenretention bei Fable zeigen die Richtung.
- **Kollateralschaden**: Globale Abschaltung trifft unbeteiligte Nutzer und gesamte Kundenbasis.
- **Geopolitik**: Wenn die USA ihre stärksten Modelle zurückhalten, dürften China und andere eigene Modelle ebenfalls nicht open-source veröffentlichen — starke LLMs könnten langfristig nicht mehr für allgemeine Nutzung verfügbar sein (Top-HN-Kommentar libraryofbabel).
- **Selektivität**: Die Direktive traf nur Anthropic, nicht OpenAI, Google, Mistral — obwohl deren Modelle ähnliche Fähigkeiten haben.

## Kontext: Anthropic vs. US-Regierung

Das Verhältnis ist seit frühen 2025 angespannt: Das DoD stufte Anthropic als „supply chain risk" ein, zwei Klagen laufen. Gleichzeitig nutzt die NSA laut Berichten weiter Mythos-Klasse-Modelle für offensive Cyberoperationen. Die Administration spricht öffentlich darüber, eine Beteiligung an OpenAI (Anthropics Konkurrent) zu übernehmen. Dieser Vorfall ist also auch ein Kapitel in einem größeren politischen Konflikt, nicht nur ein isolierter Sicherheitszwischenfall.

## Quellen

- [Anthropic-Statement, 12. Juni 2026](https://www.anthropic.com/news/fable-mythos-access) — Primärquelle
- [The Hacker News, 13. Juni 2026](https://thehackernews.com/2026/06/us-orders-anthropic-to-suspend-fable-5.html) — inkl. WSJ/Reuters/The-Information-Update zu Amazon/Jassy, Sacks-Statement, Semafor-China-Bericht
- [State of Surveillance, 12. Juni 2026](https://stateofsurveillance.org/news/anthropic-fable-5-mythos-5-suspended-us-export-control-2026/) — politische Einordnung, Crypto-Wars-Vergleich, Hacker-News-Thread
- [Nerova.ai, 12. Juni 2026](https://nerova.ai/news/anthropic-disables-claude-fable-5-mythos-5-export-control-june-12-2026) — Enterprise/Agent-Abhängigkeitsrisiko, Project Glasswing
