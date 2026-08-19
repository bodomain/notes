Codex is quietly killing your SSD.

It writes diagnostic logs to disk non-stop, even when you're not
doing anything. Your SSD has a write limit. Codex is burning through it in the background.

One command fixes it 👇

I checked my machine today. 628 MB of useless logs. 78,000+ TRACE
entries, internal garbage I'll never read. Built up over a few days
of light use.

The file looks small but SQLite keeps flushing writes to disk
underneath. The drive wears out while the file size barely moves.
Mehr anzeigen


I quit Codex, ran one command, and verified:

  sqlite3 ~/.codex/logs_2.sqlite "CREATE TRIGGER IF NOT EXISTS
  block_log_inserts BEFORE INSERT ON logs BEGIN SELECT RAISE(IGNORE);
  END;"

This adds a rule that silently drops all new log entries. Your
conversations are in a different file, completely safe.

Tested it, output 0. Nothing gets written anymore. Codex works fine.
 
 sqlite3 ~/.codex/logs_2.sqlite "CREATE TRIGGER IF NOT EXISTS
  block_log_inserts BEFORE INSERT ON logs BEGIN SELECT RAISE(IGNORE);
  END;"