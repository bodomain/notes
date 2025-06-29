[article](https://github.blog/developer-skills/github/less-todo-more-done-the-difference-between-coding-agent-and-agent-mode-in-github-copilot/#h-take-this-with-you)

- **Agent mode = synchronous:** Works inside VSCode as an autonomous collaborator that iterates on code, runs tests, and fixes its own mistakes in real time
- **Coding agent = asynchronous:** Runs inside GitHub Actions (in public prewiew), picks up issues you assign ( ```assignee: Copilot```), explores the repo, writes code,  passes tests, and opens a pull request for your review.
>[!note] Think of agent mode as the senior dev pair programming with you, and coding agent as the diligent teammate grinding through well-scoped tickets>.

>[!note]  Tips for using agent mode
> - **Scope the outcome:** Be as clear as possible about what you want; Vagueness breeds hallucination.
> - **Seed with context:** Point it at the spec file or paste the schema so it doesn't reinvent shapes.
> - **Iterate interactively:** Let it run, but nudge when it veers-like pair programming with a skiled teammate who's fast but needs occasional direction.
> - **Extend with MCP servers:** If you need custom tools (database migrations, cloud deploys, etc.).

>[!note] Coding agent (asynchronous teammate)
> Agent mode lives in the IDE, coding agent lives in the repos. It spins up a secoure cloud workspace (via GitHub Actions), figures out a plan, edites code on its own branch, runs  tests/linters, and opens a pull request tagging you for review.


