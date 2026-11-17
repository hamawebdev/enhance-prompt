# Redoing the research

Follow this when the owner asks to redo, refresh or update the research behind this skill. It replaces the stored research with a current one and carries the consequences into the few places that depend on it. It does not rebuild the skill: the run procedure and the briefs stay as they are unless a finding forces a specific change.

Unlike a normal run, a refresh needs web access. Ask the owner nothing; decide, and report at the end.

## What depends on the research

Only these may change in a refresh:

- `research/sources.md`: every source, its date, the day it was read.
- `research/findings-*.md`: the findings, each with verbatim quotes and source IDs.
- `research/decisions.md`: the two settled questions, the other choices, and the tensions.
- `references/principles.md`: what the experts apply during a run, each line citing findings.
- The block headed "Settings from research" in `SKILL.md`.

The sections of the briefs that state the owner's fixed rules, and the "Lessons from use" section of `decisions.md`, do not come from published research and are not touched.

If a refreshed finding cannot be honoured without a change outside that list (for example the answer on teammates and subagents reverses, which would change how the run starts its experts), make the smallest edit that applies it and name that edit in your report.

## Steps

1. **Keep the old research recoverable.** The skill folder is a git repository. Make sure the working tree is clean, so the current research is in history, before changing anything.

2. **Set the window.** The twelve months ending today. Record both dates.

3. **Run the research as a team of four in parallel**, one per slice, plus the open-questions pass. Use an agent team if the session has that feature enabled, otherwise subagents; if neither is available, do the slices one after another yourself. Give each researcher the common brief below and its slice.

4. **Check what comes back.** Every cited page was actually fetched, every quote is verbatim, every source has a date or says plainly that it has none. Reject findings that rest on memory.

5. **Replace the stored research.** Overwrite the four findings files and rebuild `sources.md` from their source tables, with the new window and retrieval date at the top.

6. **Re-decide.** Go through `decisions.md` section by section against the new findings. For each of the two questions and each other choice, either confirm it with current evidence or change it, and update the confidence, the evidence and the "what would change this" lists. Keep the section on where the research does not support the design honest: add new tensions, remove ones that no longer hold.

7. **Carry it into the run.** Rewrite `references/principles.md` from the new findings in the same form (short lines, each citing finding IDs, a contents list at the top). Update the "Settings from research" block in `SKILL.md` if either answer changed.

8. **Check for private material.** Nothing from the owner's sessions, projects or clients goes into this repository: no names, phone numbers, messages or project details. Search what you wrote before committing.

9. **Commit, and do not push.** One commit that says the research was refreshed, with the window.

10. **Report** to the owner in a short list: the new window, how many sources and how many are new, which decisions changed and why, which stayed, and any edit made outside the list above.

## Common brief for every researcher

```
You are one of several researchers refreshing the evidence base of a Claude Code skill.

What the skill does: it turns an owner's rough paste of requirements (often a client's message) into a
finished prompt for the agent that will do the work, by default a Claude Code lead session that owns the
project, decides for the client and runs its own agents. Inside one run a framing expert settles goal,
audience, the role the work calls for and what is out of scope; a requirements expert writes well-defined
requirements with expert additions and corrections; an independent checker that has not seen their
reasoning compares the result with the original paste and sends it back until nothing is missing. Nobody
asks the owner anything. The final prompt says what is wanted and what done looks like, never files or an
implementation approach.

Topics: multi-agent orchestration and when it helps or hurts; briefing and delegating to another agent;
handing work between agents without loss; independent verification and maker-checker loops; writing
prompts and specifications for agents and for current models (outcome versus steps, over-prompting,
emphasis, examples, role or persona lines); handling ambiguity without asking the person; done criteria
and traceability to the original request; Claude Code agent teams, subagents and skills.

Two questions every researcher collects evidence on:
A. Should a prompt handed to a Claude Code lead open with an expert role ("You are a senior X")?
B. For a short sequential pipeline inside one run (framer, requirements writer, blind checker with a
   send-back loop), should the experts be agent-team teammates or subagents?

Source rules:
- Window: published or substantively updated in the twelve months ending <today>. Older landmark pieces
  go in a separate section labelled as background.
- Fetch and read every page you cite. Never cite from memory. Quotes are verbatim and short. Record the
  date shown on the page; if there is none, say so and give any bound you can establish.
- Pages you could not read are listed under "Could not verify" and are not evidence.
- Search queries are generic. Never put a person, client, project or anything from this machine into a
  query or a URL.

Deliverable: one markdown file with a sources table (ID, title, publisher, URL, published, retrieved,
in window), numbered findings (each: a one-sentence actionable claim, the verbatim evidence with source
IDs, which part of the skill it bears on, and its strength: direct recommendation, measured result,
described practice or opinion), what your slice says on questions A and B with finding IDs, background
outside the window, and what could not be verified. Say plainly where the evidence is thin.
```

## The slices

| File | Source ID prefix | Slice |
|---|---|---|
| `findings-anthropic-engineering.md` | AE | Anthropic's own articles: the engineering blog, research and news pages, and its product blogs. Start by listing what was published in the window, then read the relevant posts in full. |
| `findings-anthropic-docs.md` | AD | Anthropic's documentation: Claude Code (agent teams, subagents, skills, best practices, common workflows, headless use), the developer platform's prompting guides for current models, the Agent SDK, and the Agent Skills specification. Quote exactly; these features change. Include a comparison table of teammates and subagents built only from quoted documentation, and the packaging facts a skill author needs. |
| `findings-industry.md` | IN | Engineering blogs and official guides of large software companies other than Anthropic: model vendors, developer-tool companies and large engineering organisations. First-party posts only, from at least six companies. Include where they disagree with each other. |
| `findings-open-questions.md` | OQ | Questions A and B only, argued adversarially: the strongest evidence on each side, including empirical studies of persona prompting (papers outside the window are admissible as labelled background when they are the best measurements available), then a verdict with a confidence, the specific rule the skill should follow, and what would change the verdict. |
