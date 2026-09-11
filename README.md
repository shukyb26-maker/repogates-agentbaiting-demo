# agentbaiting-demo

A deliberately harmless repository that exists to demonstrate one check in
[RepoGates](https://repogates.com): **C22, AI-agent provenance**.

There is nothing to install here. Do not install it.

## What it demonstrates

RepoGates scores a GitHub repository before a browser download and holds the
download if it fails policy. One of its checks can only run in the browser:
whether an AI assistant led you to the repository. The technique of seeding
repositories so that assistants find and recommend them is called
[AgentBaiting](https://repogates.com/intel/agentbaiting.html).

This repository has the shape the FakeGit campaign used: a **young
maintainer account** and a **brand-new repository**. On its own that is a
**REVIEW** — the download is held and the two findings are shown, and you can
proceed. Reach the same repository from an AI surface — claude.ai,
chatgpt.com, gemini.google.com, an MCP directory — and press *Download ZIP*,
and RepoGates escalates the review to a **BLOCK**, with a note naming the
surface that led you here.

That is the whole demonstration. Reach it by typing the address, and it stays
a review.

## Why those two findings

- [C1 — owner account age](https://repogates.com/checks/c01-owner-account-age.html):
  the account that owns this repository is under a year old.
- [C2 — repository age](https://repogates.com/checks/c02-repository-age.html):
  the repository was created recently. This finding expires after thirty
  days; the account-age one persists for the account's first year.

Neither is evidence of anything by itself — which is exactly why an AI
recommendation on top of them is the thing that tips the verdict.

## Scope, stated

RepoGates gates browser-initiated downloads. It does not see `git clone`,
package managers or `curl` — outside Claude Code with the RepoGates
plugin, whose hook refuses a clone or install that names a blocked
repository on the command line, before it runs. An AI agent that fetches
on its own is not seen either, unless it asks through the RepoGates MCP
tools.

Maintained by the RepoGates project purely as a demonstration fixture.
