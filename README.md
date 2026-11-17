# enhance-prompt

A Claude Code skill that turns a rough paste of requirements into a finished prompt for the agent that will do the work.

It is built for one way of working: you relay what a client wants in a few quick lines, and you hand the result to a Claude Code lead session that owns the project, decides on the client's behalf and directs its own agents. You are not asked anything along the way.

## What a run does

1. **A framing expert** reads your message and the project and settles what has to be settled first: the goal, who it is for, the role the work calls for, the size, the authority of the receiving agent, and what is out of scope.
2. **A requirements expert** takes that framing and writes the requirements as a senior specialist in that field would: every task well defined, with their own additions and corrections where your message is weak, incomplete or wrong.
3. **A checker that has seen none of their reasoning** compares the result with your original message, item by item, and sends it back until nothing you wrote is missing.

Then it prints two things and stops:

- the final prompt, in one block, ready to paste;
- a short list of what the experts decided, added or changed, with the reason for each.

It never runs the prompt.

A diagram of the run is in [docs/how-it-works.excalidraw](docs/how-it-works.excalidraw); open it at excalidraw.com or with an Excalidraw editor extension.

## What it guarantees

- **No questions.** Where your message is ambiguous the experts choose as an expert would and tell you what they chose.
- **Nothing lost.** Every requirement in your message can be pointed to in the prompt. It may be reorganised, sharpened, or openly changed with a reason; it is never silently dropped.
- **What, not how.** The prompt says what is wanted and what done looks like. It names no files and picks no approach; the lead that receives it finds the best one. Tools and ways of working that you asked for yourself are kept as requirements.

## Use

In any Claude Code session:

```
use enhance prompt skill to enhance this prompt:
<your rough requirements or the client's message>
```

or `/enhance-prompt <text>`. "Using enhance prompt skill, write a prompt to …" works as well when you have no draft at all.

Reply to the result with a correction and you get a whole new prompt, not a patch.

A run starts the three experts one after another, plus a second pass when the checker finds gaps. Expect about seven to eleven minutes and several times the usage of a single-pass rewrite. It needs no web access.

## Install

```
git clone https://github.com/hamawebdev/enhance-prompt ~/.claude/skills/enhance-prompt
```

The folder name must be `enhance-prompt`. Requires a Claude Code version that can start subagents; without them the skill does the same steps in one context and says that the check was not independent.

## What it is built on

The skill's design rests on research stored in the repository, so a run looks nothing up:

- [research/sources.md](research/sources.md): every source with its publication date and the day it was read. Anthropic's articles, engineering blog and documentation, and the engineering blogs of other large software companies, from the twelve months before the research date.
- `research/findings-*.md`: the findings, each with verbatim quotes.
- [research/decisions.md](research/decisions.md): what the research settled, including two questions the design had left open (the final prompt does not open with an expert role; the experts are subagents, not agent-team teammates), where the research does not support the design, and what would change each answer.
- [references/principles.md](references/principles.md): what the experts apply from it during a run.

To redo the research later, say "redo the research for enhance prompt". The skill follows [research/refresh.md](research/refresh.md), replaces the stored research, and updates only what depends on it.

## Layout

```
SKILL.md                    the run: what the coordinating session does
briefs/framing.md           instructions for the framing expert
briefs/requirements.md      instructions for the requirements expert
briefs/checker.md           instructions for the checker
references/principles.md    research-derived principles the experts apply
research/                   sources, findings, decisions, and how to refresh them
```

## Earlier version

The tag `v1` is the previous skill: a single pass that returned a rewritten prompt, a list of open questions and a note on what was cut. `git checkout v1` restores it.
