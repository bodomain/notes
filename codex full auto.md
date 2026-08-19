Use the dangerous bypass mode:

```bash
codex --dangerously-bypass-approvals-and-sandbox
# alias:
codex --yolo
```

For safer “mostly auto”:

```bash
codex --sandbox workspace-write --ask-for-approval on-request
```

That lets Codex edit/run inside the repo, but it will still ask for network or outside-workspace changes. Enable network with:

```bash
codex --sandbox workspace-write --ask-for-approval on-request \
  -c 'sandbox_workspace_write.network_access=true'
```

Why `/goal` still asks: Goals continue work, but they do **not** remove security boundaries. Codex still stops when approval policy/sandbox requires it. Official docs list full bypass as `--dangerously-bypass-approvals-and-sandbox` / `--yolo`, and describe normal Auto as workspace-write plus on-request approvals. ([OpenAI Developers][1])

Also update first:

```bash
npm install -g @openai/codex@latest
codex --version
```

Goals require Codex `0.128.0+`. ([OpenAI Developers][2])

[1]: https://developers.openai.com/codex/agent-approvals-security "Agent approvals & security – Codex | OpenAI Developers"
[2]: https://developers.openai.com/cookbook/examples/codex/using_goals_in_codex "Using Goals in Codex"
