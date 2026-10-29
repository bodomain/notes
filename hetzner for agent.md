Fixkosten für den VPS, bestehende Modell-Abonnements nutzen und Limits einfach akzeptieren.

Ich würde sogar bewusst klein anfangen:

- Hetzner: 2 vCPU, 4 GB RAM
- OS: Debian 13
- Agent: Hermes
- LLM: ChatGPT/Codex oder OpenCode Go
- Betrieb: `systemd` für dauerhafte Verfügbarkeit
- Zugriff: zunächst SSH, später eventuell Telegram
- Sicherheit: eigener Linux-User, keine Root-Rechte für den Agenten

Das Interessante an dem Experiment ist weniger der Chatbot selbst, sondern ein persistenter Agent mit eigenem Arbeitsverzeichnis, Gedächtnis und der Möglichkeit, Aufgaben über längere Zeit selbstständig zu verfolgen.

Und wenn das Ganze nichts taugt, löschst du den VPS wieder. Keine große Investition, keine langfristige Verpflichtung.