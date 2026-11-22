# Start
export OPENCODE_GO_MODEL="qwen3.7-plus"
# Welches Model benuzte ich?
Ja, das geht – aber nicht direkt über das, was Claude Code selbst anzeigt. Die CLI kennt nämlich nur den Alias, mit dem sie gestartet wurde (sonnet); das echte Modell kennt nur der Proxy.
Warum /status „Sonnet“ zeigt
Claude Code ist nur das Harness. Es schickt model: sonnet an 127.0.0.1:4141, und erst der Proxy ersetzt das durch qwen3.7-plus. Deshalb zeigt /status „Sonnet 5.5“ – das ist kein Fehler.
Zuverlässig prüfen (empfohlen)
In einem zweiten Terminal, während die Session läuft:
curl -s http://127.0.0.1:4141/health
Ausgabe:
{"ok":true,"model":"qwen3.7-plus"}
Das ist die tatsächliche Wahrheit. Alternativ im Proxy-Log, das beim Start im Terminal erscheint:
OpenCode Go Claude proxy listening on http://127.0.0.1:4141/v1 -> qwen3.7-plus
POST /messages -> 200 as qwen3.7-plus
Innerhalb der laufenden CLI
- /status zeigt Modell und API-Base-URL. Wenn dort http://127.0.0.1:4141 steht, läuft es über den Proxy – aber als Modell steht der Alias Sonnet 5.5.
- /model öffnet die Modellauswahl. Dort gibt es eine zusätzliche Zeile „OpenCode Go qwen3.7-plus“, weil der Launcher ANTHROPIC_CUSTOM_MODEL_OPTION setzt. Das ist das echte Backend-Modell.
- Wenn du diese Zeile auswählst – oder direkt /model qwen3.7-plus eingibst –, zeigt /status danach qwen3.7-plus. Der Proxy schickt trotzdem dasselbe Modell upstream, es ändert sich also nur die Anzeige. Getestet:
Set model to `qwen3.7-plus` for this session only
- Alternativ von Anfang an mit dem echten Namen als Harness-Modell starten:
CLAUDE_CODE_MODEL_ALIAS=qwen3.7-plus claude-o-go
Dann meldet /model: Current model: qwen3.7-plus.
Einschränkung: Bei einem unbekannten Modell warnt Claude Code einmalig, dass es 1 Mio. Kontextfenster annimmt. Wenn das nicht stimmt, kannst du es korrigieren:
CLAUDE_CODE_MAX_CONTEXT_TOKENS=256000 CLAUDE_CODE_MODEL_ALIAS=qwen3.7-plus claude-o-go
Was nicht funktioniert
- Das Modell selbst fragen („Welches Modell bist du?“) – unzuverlässig, weil der System-Prompt es als Claude anspricht.
- echo "$OPENCODE_GO_MODEL" – zeigt nur die Konfiguration, nicht was eine laufende Session wirklich sendet.
Ich habe das jetzt auch als Abschnitt „Checking the actual model“ in der README.md dokumentiert. Wenn du möchtest, kann ich zusätzlich eine Statuszeile einrichten, die dir das echte Modell dauerhaft unten in der Claude-Code-TUI anzeigt – das wäre die komfortabelste Variante.


