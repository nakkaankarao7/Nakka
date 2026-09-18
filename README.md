# Nakka

**An AI coding agent in your VS Code sidebar — and you decide how much it may do on its own.**

[Install from the VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=Nakka.nakka)

---

## This repository

This is where Nakka's **issues, questions and documentation** live. It is not
where the source is — the source is private.

- **Found a bug?** [Open an issue](https://github.com/nakkaankarao7/Nakka/issues/new/choose)
- **Want something?** Same place, as a feature request
- **Security problem?** Please do not open an issue — see [SECURITY.md](SECURITY.md)

---

## You choose how much rope it gets

Switch with `Shift+Tab`, or from the mode chip in the input bar.

| | |
|---|---|
| **Manual** | Stops for your approval before it changes anything. |
| **Plan** | Reads and searches only. Writes a plan, and waits for you to approve it before touching a file. |
| **Auto** | Runs what the safety check clears, and stops for the rest. |

**Auto does not mean "anything".** Every command is classified before it runs:

- `npm test`, `pytest`, `git status`, `npm install` — runs
- `rm -rf`, `kill -9`, `git push --force` — stops and asks, in every mode
- Anything catastrophic — refused outright, in every mode, including Auto

**Plan mode is enforced, not advisory.** While a plan is being written, edits
are refused by the permission layer, and only the plan file may be written.

---

## What it can do

- **Read and search** — open files, grep across the tree, glob for paths
- **Edit** — exact-match edits, shown as a diff you accept or reject
- **Run commands** — output streamed back; a long-running command is moved to
  the background rather than killed
- **Ask you** — when a choice is genuinely yours, it asks in the transcript
- **Track its own work** — a task list you can watch it move through

## Bring your own model

| Provider | Notes |
|---|---|
| **Anthropic** | Over the Messages API |
| **OpenAI** | And any endpoint that speaks the OpenAI Chat Completions API |
| **Ollama** | Models on your own machine — no key, no network |

There is no account and no proxy. Requests go from your editor to the provider
you configured, with the key you supplied.

### Configuration

`~/.nakka/config.yaml`:

```yaml
models:
  - name: Sonnet
    provider: anthropic
    model: claude-sonnet-4-6
    apiKey: sk-ant-...
    roles: [chat, edit, apply]

  - name: Local
    provider: ollama
    model: qwen2.5-coder:7b
    roles: [chat, edit, apply, autocomplete]
```

**Project rules.** Nakka reads `AGENTS.md`, `AGENT.md` or `CLAUDE.md` from your
repository root, and any `.md` file under `.nakka/rules/`, as standing
instructions for that project.

---

## Privacy

No telemetry. Nakka collects nothing and sends nothing anywhere except the
model provider you configured. Your code goes to that provider and nowhere
else.

---

## Licence

Apache-2.0 — see [LICENSE](LICENSE) and [NOTICE](NOTICE).

Nakka is a fork of [Continue](https://github.com/continuedev/continue), also
Apache-2.0. The files have been changed substantially; NOTICE sets out what was
changed. Continue Dev, Inc. does not endorse this extension and is not
connected to it.
