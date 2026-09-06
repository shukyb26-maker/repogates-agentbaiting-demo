# agentbaiting-demo

A deliberately harmless repository that exists to demonstrate one check in
[RepoGates](https://repogates.com): **C22, AI-agent provenance**.

There is nothing to install here. Do not install it.

## What it demonstrates

RepoGates scores a GitHub repository before a browser download and holds the
download if it fails policy. One of its checks can only run in the browser:
whether an AI assistant led you to the repository. That technique — seeding
repositories so that assistants find and recommend them — is called
[AgentBaiting](https://repogates.com/intel/agentbaiting.html).

This repository carries a `.devcontainer/devcontainer.json` whose only
command is `echo`. On its own that is a **warning** (check C10: a
devcontainer's `initializeCommand` runs on the host). Reach this repository
from an AI surface — claude.ai, chatgpt.com, gemini.google.com, an MCP
directory — and press *Download ZIP*, and RepoGates escalates the warning to
a **block**, with a note saying which surface led you here.

That is the whole demonstration. Reach the same repository by typing its
address, and it stays a warning.

## What is actually in the devcontainer

```json
{ "initializeCommand": "echo 'RepoGates demo: this command runs on the host when a folder opens'" }
```

It prints a sentence. The point is that RepoGates cannot know that from the
file list, which is why a devcontainer warns rather than blocks — and why an
AI recommendation on top of a warning is treated as the thing that tips it.

## Scope, stated

RepoGates gates browser-initiated downloads. It does not see `git clone`,
package managers, `curl`, or an AI agent that fetches on its own.

Maintained by the RepoGates project purely as a demonstration fixture.
