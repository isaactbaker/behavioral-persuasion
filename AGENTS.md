---
description: "Project instructions for behavioral-persuasion. Extends the global contract at ~/.dsh/AGENTS.md."
kind: "agent-contract"
---

# AGENTS.md - behavioral-persuasion

**Read `~/.dsh/AGENTS.md` first.** It loads before this file and carries the
contract that applies to every project: how to work, task sizing and the triage
block, the two machine spaces, verification, the fan-out and harsh critic loop,
one writer per tree, completion status, self-rating, the confusion protocol and
the safety rules. None of it is repeated here.

This file adds only what is specific to this repository.

## Stack

- Static HTML pages with inline CSS and JavaScript. No build step, no package
  manager, no server.
- Each page is self-contained: `index.html` plus one file per tool
  (`negotiation-prep-agent.html`, `skills-development-agent.html`,
  `executive-communication-coach.html`).

## Commands - the gates for this repo

Use the narrowest row that covers your diff. These are the real commands; do not
invent a different runner.

| Surface | Gate |
|---|---|
| Any change | open the page in a browser and exercise the flow end to end |
| Contract or copy change | verify the copy renders as intended at desktop and mobile widths |

**There is no automated gate here at all**: no build, no tests, no lint. Say so
plainly in your report rather than implying a gate ran. Manual verification of
the actual page is the only evidence available, and it is required, not optional.

## Scope of the contract here

Because nothing is automated, correctness depends on reading the whole page you
touched. A change to shared inline script or styles can break a sibling page:
grep for the function or class name across all `*.html` files before you change
it.

Keep each page self-contained and dependency-free. A CDN import is the only
external dependency this project accepts, and adding one needs a reason.
