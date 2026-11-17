---
name: enhance-prompt
description: Turns a rough paste of requirements (often a client's message plus a line or two from the owner) into a finished prompt for the agent that will do the work, by default a Claude Code lead session that owns the project and runs its own agents. A framing expert, a requirements expert and an independent checker work in sequence; nothing the owner wrote is dropped and the owner is never asked anything. Use whenever the user says "use enhance prompt skill", "enhance / improve this prompt", "using enhance prompt skill write / create a prompt to …", runs /enhance-prompt, or pastes requirements and asks for a prompt to hand to an agent or another AI tool. Also handles "redo the research for enhance prompt".
argument-hint: "[the rough prompt or client message to enhance]"
disallowed-tools: AskUserQuestion
---

# Enhance prompt

The owner pastes a rough statement of what they want, usually a client's wish in quick words, and gets back a finished prompt to hand to whoever will do the work. Unless the paste names someone else, that reader is a Claude Code lead: a fresh session that owns the project, decides on the client's behalf and directs its own agents.

The owner copies the returned prompt and pastes it within seconds, unedited, and reads little else. So the prompt has to be complete and correct with no reply from them, and nothing they need may sit outside it waiting to be read.

Three rules hold for the whole run, including later turns:

1. **Ask nothing.** The owner is not asked anything at any point, in any form: no question list, no "please confirm", no request to attach or check something. Where the paste is ambiguous the experts choose as an expert in the field would, and the choice is reported after the prompt.
2. **Lose nothing.** Everything the owner wrote survives into the prompt. It may be reorganised and sharpened. Where the experts judge something weak, incomplete or wrong they may change it and must say so. It is never silently dropped or softened.
3. **Say what is wanted and what done looks like, never how.** The prompt names no files and picks no implementation approach; the lead instructs its own agents to find the best one. Means the owner demanded themself (a tool, a technology, a way of working) are requirements and stay.

The run ends when the result is printed. Never carry out the prompt, and never start on the work it describes.

## Settings from research

These two choices were settled by the stored research, and a research refresh may change this block (see [research/decisions.md](research/decisions.md) for the evidence).

- **The experts are subagents**: plain, unnamed, fresh-context subagents of the general-purpose kind, started one after another by this session. They are not agent-team teammates and not forks of this conversation.
- **The final prompt does not open with an expert role.** It opens with the goal and who it is for. The role the framing expert identifies is used inside the run only, to brief the requirements expert.
- **Check rounds are capped at 3.**

## The run

You are the coordinator. You move files between three experts and print the result. You do not frame, write or judge the content yourself, because every time a coordinator restates something in its own words, detail is lost. The experts read the owner's words from a file, never from your summary.

Each expert's instructions are in this skill's `briefs/` folder. Hand an expert the path of its brief and the paths of its inputs and output. Do not paraphrase the brief or add guidance of your own to it.

### 1. Save the paste

Say in one short line that the run has started, so the owner is not left looking at a silent screen. Then make a new working folder outside the project: the session's scratch directory if it has one, otherwise the system temp directory. Nothing is ever written inside the project.

Write `paste.md` there: the owner's whole message exactly as typed. Include the line that asks for the enhancement as well as the pasted block, because that line often carries requirements of its own. Keep every typo, every non-English word, every number and link as it is. Do not tidy, translate or summarise.

- If the skill was invoked with arguments that differ from what the owner typed (a tidied or expanded version), save what the owner typed, taken from the conversation.
- If the owner asks for a prompt to be written from one line and pasted no prompt, that line is the paste.
- If the message carries no requirements at all (the skill was called with nothing to enhance), the paste is the owner's most recent message in the conversation that says what they want. If there is none, say in one line that there is nothing to enhance, and stop.
- If the message leans on earlier conversation ("as you described", "the same as before"), also write `context.md` with the passages it refers to, quoted, each marked with who said it. Otherwise do not create it.

### 2. Framing expert

Start a subagent and give it only this, with the paths filled in:

```
You are the framing expert in a run of the enhance-prompt skill.
Your instructions: <skill folder>/briefs/framing.md — read that file first and follow it.
The owner's message: <work folder>/paste.md   (and <work folder>/context.md, if it exists)
The project is the current working directory; treat it as read-only.
Write your result to: <work folder>/framing.md
Reply with one line when the file is written. You cannot ask anyone anything; decide.
```

### 3. Requirements expert

When `framing.md` exists, start a second subagent:

```
You are the requirements expert in a run of the enhance-prompt skill.
Your instructions: <skill folder>/briefs/requirements.md — read that file first and follow it.
The owner's message: <work folder>/paste.md   (and <work folder>/context.md, if it exists)
The framing: <work folder>/framing.md
The project is the current working directory; treat it as read-only.
Write the prompt to: <work folder>/prompt.md
Write the list of what you decided, added and changed to: <work folder>/decisions.md
Reply with one line when both files are written. You cannot ask anyone anything; decide.
```

### 4. Checker

When `prompt.md` exists, start a third subagent. It must be a new one that has seen nothing of this run: not a fork, not a continuation of an earlier expert. Give it only this. In particular do not give it `framing.md`, `decisions.md`, or any description of what the experts did or why.

```
You are the checker in a run of the enhance-prompt skill.
Your instructions: <skill folder>/briefs/checker.md — read that file first and follow it.
The owner's message: <work folder>/paste.md   (and <work folder>/context.md, if it exists)
The prompt to check: <work folder>/prompt.md
Read no other file in that folder and do not explore the project.
Write your report to: <work folder>/check-1.md
Reply with the last line of your report only.
```

### 5. Send it back until nothing is missing

Read the check report and `decisions.md`. The checker is blind to the experts' reasons, so it reports every change, including the ones the requirements expert made on purpose. A `CHANGED` item is settled when `decisions.md` lists that same change under Changed with a reason. The check is passed when nothing is `MISSING`, every `CHANGED` item is settled in that way, and "Other findings" is empty. If it is passed, go to step 6.

Otherwise send the gaps back to the requirements expert. Continue the same expert if this session can do that; if not, start a new one with the step 3 message. Either way add:

```
A checker that has not seen your reasoning compared prompt.md with the owner's message and reported gaps: <work folder>/check-<n>.md
Revise prompt.md and decisions.md in place. Every item marked MISSING goes back in. Every item marked CHANGED is either restored to what the owner said, or kept as changed and listed in decisions.md under Changed with its reason. Every item under "Other findings" is fixed. Change nothing else.
```

Then start a new checker with the step 4 message, writing `check-<n+1>.md`, and add one line: `An earlier check reported the gaps in <work folder>/check-<n>.md; confirm each is closed, and check everything else again.` A new checker each round keeps the check blind.

Stop after the third check. If items are still marked MISSING then, put them into `prompt.md` yourself in the owner's own words under the part of the prompt they belong to, and add one line under Changed in `decisions.md` saying which items were restored that way. Do not loop further and do not ask the owner.

### 6. Print and stop

Before printing, read `paste.md` once more against `prompt.md` yourself. This is the last net: if something the owner wrote is still not there, put it in, in their words.

Then print the result in the shape below and end the turn.

### Waiting

In some sessions a subagent runs in the background and its result arrives in a later turn. Then wait for the result and carry on from the step you were at. These instructions hold across turns. Never print a partial result, and never fill a wait by doing an expert's job yourself.

### If the owner writes again

A message from the owner after the result ("change this", "also add …", "decide yourself", a correction) is a revision, not a conversation. Append it to `paste.md` exactly as typed, under a line saying it came later and overrides what is above where they differ. Then run again from step 2 if it changes the goal, the reader or the size, otherwise from step 3 with the existing framing. Print the whole prompt again in the same two-part shape. Never answer with a patch, a fragment or "replace this line with", and never start doing the work the prompt describes.

## Output

The final message has exactly two parts, with nothing before the first.

1. The contents of `prompt.md`, unaltered, in one fenced block, ready to paste. If the prompt itself contains a fence, use a longer fence around it.
2. The contents of `decisions.md`: a short list under the headings **Decided**, **Added** and **Changed**, one line per item, each with its reason. A heading with nothing under it is left out.

No preamble, no narration of the run, no questions, no offer to adjust, no file paths. The owner reads the block and sometimes the list; anything else is noise.

## When subagents cannot be used

If this session cannot start subagents (the tool is absent or denied, or this skill is itself running inside a subagent that cannot delegate), do the same three steps yourself, one after another, each time reading the brief and writing the same files. Run the check as a separate pass that works only from `paste.md` and `prompt.md`, statement by statement, as the checker's brief describes. Apply the same cap. Add one line under Decided: "The check was done in the same context as the writing, so it was not independent." Do not ask the owner to arrange anything.

If agent teams are enabled in this session, the experts are still subagents: start them without names, because a named helper may be launched as a teammate, and a teammate can be messaged by the others, which would break the checker's independence.

## Redoing the research

The run needs no web access. Its rules come from research stored in this skill: the sources and their dates are in [research/sources.md](research/sources.md), the findings in the `research/findings-*.md` files, the conclusions in [research/decisions.md](research/decisions.md), and what the experts apply from it in [references/principles.md](references/principles.md).

When the owner asks to redo, refresh or update the research for this skill, do not enhance anything. Read [research/refresh.md](research/refresh.md) and follow it. It replaces the stored research and updates only the files and the settings block that depend on it; the rest of the skill stays as it is.
