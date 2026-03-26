
# Run It
## Terminal 1 — Start the proxy server:

uv run uvicorn server:app --host 0.0.0.0 --port 8082


## Terminal 2 — Run Claude Code:

ANTHROPIC_AUTH_TOKEN=freecc ANTHROPIC_BASE_URL=http://localhost:8082 claude


# [*] Just use that:
https://github.com/bodomain/claude_w_openrouter