# What the research settled

Research carried out on 2026-11-17 over sources published or updated between 2025-11-17 and 2026-11-17: Anthropic's articles, engineering blog and documentation, and the engineering blogs and official guides of other large software companies. Four researchers worked in parallel, one per slice, and a fifth pass argued both sides of the two open questions. Sources and dates are in [sources.md](sources.md); findings with verbatim quotes are in the `findings-*.md` files. Finding IDs below point into those files.

## Contents
- Question A: should the final prompt open with an expert role?
- Question B: should the experts in a run be teammates or subagents?
- Other choices the research settled
- Where the research does not support the design
- What the research could not tell us
- Lessons from use

## Question A: should the final prompt open with an expert role?

**No.** Confidence: medium to high (three researchers independently put it at 70 to 75 percent).

The rule the skill follows:

1. The final prompt never starts with "You are a/an [expert] …" and carries no expertise persona anywhere. It opens with the goal and who it is for.
2. The role the framing expert identifies is used inside the run only, as the specialisation of the requirements expert.
3. In the final prompt that role is turned into things the reader can act on: the domain context such an expert would assume, the standards they would apply (written as requirements), the audience, what is out of scope, and done criteria with a way to check them.
4. Standing and authority are a different matter and are stated: that the reader owns the job and decides for the client. This is included on purpose, scoped to the job.
5. Where a particular perspective matters for part of the work, it is attached to that part, not to the reader.

Evidence for "no":

- Vendor guidance for the first message to a coding agent lists what to include, and a role is not on any list. Claude Code's best-practices page: "A specific prompt helps for the same reason, because it gives Claude information it doesn't already have." (undated documentation, read 2026-11-17; F-OQ-A7, F-AD-36). OpenAI's guidance for its coding agent has the same four-part shape of goal, context, constraints and "done when", with no role (undated documentation; F-OQ-A8, F-IN-26).
- Every current vendor statement that recommends a role places it in the system prompt of a deployed agent or in a worker's own brief, not in a task message (F-AD-34, F-AD-35, F-OQ-A16, F-OQ-A17, F-OQ-A18).
- The best-controlled study tested this exact placement, persona text at the top of the user prompt under an unchanged system prompt, and found no reliable gain: "When persona prompts do matter, they are more likely to reduce accuracy than to increase it" (arXiv 2512.05858, 2025-12-05; F-OQ-A10). It included no Claude models and no agentic tasks.
- A pre-registered 2026 study on frontier models writing code, including Claude Opus, found that engineer personas changed output length, not correctness (arXiv 2607.17420, 2026-07-19, abstract only; F-OQ-A12). A 2026 mechanism study found expert personas harmed knowledge-dependent work, longer personas more so (F-OQ-A11).
- In-window Anthropic writing frames the opening of a prompt as situation and task, and uses personas only for narrow subagents that need a stance different from the main agent, such as a skeptic (F-AE-49, F-AE-51).

Evidence on the other side:

- Google's current guide for its newest models allows a role definition at the start of the user prompt (F-OQ-A1), and GitHub's survey of agent definition files favours a specific persona, though for standing definition files and not task messages (F-IN-39).
- An identity sentence is not inert on the newest Claude model. A sentence about the model's standing toward the work changes behaviour considerably (F-OQ-A3), and it has a cost: more output and unrequested changes (F-OQ-A15, F-AD-38). This is why the rule keeps the statement of authority and drops the claim of expertise.
- Roles reliably shift tone, emphasis and style (F-OQ-A5, F-OQ-A14, F-OQ-A20).

What would change this answer:

- A direct comparison on this skill's own outputs: the same briefs with and without an opening expert line, run in fresh lead sessions and graded blind. Nobody has published that test.
- The receiving session running with a replaced system prompt, so that it has no default role.
- A reader built on a model whose vendor recommends the role at the start of the user prompt.
- A deliverable judged mainly on voice or register, where personas do help.

## Question B: should the experts in a run be teammates or subagents?

**Subagents.** Confidence: high (about 90 percent, the same from all four researchers).

The rule the skill follows:

1. Each expert is a plain subagent with a fresh context, of the general-purpose kind, started by the session that runs the skill. Never a fork of the conversation, never an agent-team teammate, and never named, because where agent teams are enabled a named helper may be launched as a teammate.
2. The owner's message is saved word for word in a file before anything else, and every stage reads that file. Briefs point at files and do not paraphrase them.
3. The checker receives the owner's message, the candidate prompt and its criteria, and nothing else.
4. Gaps go back to the requirements expert, a new checker checks again, and the loop stops after three checks with the remaining gaps closed by the coordinator.
5. If subagents cannot be started, the same steps are done in one context with the check as a separate pass, and the result says the check was not independent.

Evidence for subagents:

- The agent-teams documentation itself: "For sequential tasks, same-file edits, or work with many dependencies, a single session or subagents are more effective." Teams are "experimental and disabled by default", are not started in non-interactive runs, and use "approximately 7x more tokens than standard sessions when teammates run in plan mode" (undated documentation, read 2026-11-17; F-AD-01, F-AD-02, F-AD-04, F-AD-07, F-OQ-B1).
- A chain of subagents routed by the caller, and a skill that starts subagents, are both documented patterns (F-AD-15, F-AD-29, F-OQ-B2, F-OQ-B3).
- A fresh-context subagent is Anthropic's stated tool for an unbiased review: "a fresh subagent that never saw your conversation. It isn't swayed by the reasoning that produced the code" (F-OQ-B4, F-AE-37). Running the grader in its own context window improved task success by up to 10 points in Anthropic's report (F-AE-20).
- Subagents cannot ask the user anything, which suits a run that must never ask; teammates are built to be talked to and can message each other, which is a side channel a blind checker should not have (F-AD-17, F-AD-06, F-OQ-B8, F-OQ-B13).
- Other vendors arrive at the same shape. Cursor's equal-status agents coordinating through shared state failed, and its working design has isolated workers that return one handoff to the requester (2026-01-14; F-IN-01, F-IN-02). Cognition now endorses a manager with isolated children (F-IN-04). Google Research measured every multi-agent variant losing 39 to 70 percent on strictly sequential tasks, with a central orchestrator containing errors far better than independent agents (2026-01-28; F-IN-09), and Google ships an orchestrated pipeline over isolated contexts for its solve-and-verify loop (F-IN-11).

Evidence for teammates:

- Teammates keep their context across rounds, which a send-back loop can use (F-OQ-B9), and peers that message each other skip a relay through the coordinator (F-OQ-B10). Both are answered by handing over files word for word and by continuing a subagent where the session allows it (F-OQ-B16, F-AD-18).
- The documentation names review and mutual challenge as a team strength (F-OQ-B11), and one large vendor's architecture guide describes the maker and checker loop as a shared conversation (F-OQ-B12, F-IN-16).

What would change this answer:

- Agent teams leaving experimental status with documentation that recommends them for sequential pipelines, or that offers a way to stop teammates messaging each other.
- A measurement on this skill's own runs showing that requirements are lost in the coordinator's relay even with file handoffs.
- Runs growing from minutes to hours.

## Other choices the research settled

| Choice | What the skill does | Findings |
|---|---|---|
| How work passes between stages | Word for word, in files. In a measured test summarising kept 41 of 57 facts and quoting kept all 57. | F-AE-30, F-AE-31, F-AE-32, F-IN-12, F-IN-17, F-OQ-B16 |
| What the checker sees | The original request and the output, without the authors' explanations. Judging got worse when the author's prose was included, and worse again when the user's words were removed. | F-AE-21, F-IN-07, F-IN-10, F-IN-13, F-AD-21 |
| What the checker is told | Explicit criteria, a full pass and not a sample, and not to wave findings through; also what not to flag, because a reviewer told only to find problems always finds some. | F-AE-22, F-AE-23, F-AE-24, F-AD-22, F-IN-20 |
| Where the checker's findings go | Back to an agent that holds the full instructions, which decides how to act on them. | F-IN-08 |
| How long the loop runs | A cap of three checks and a fallback when the cap is reached. | F-AE-25, F-IN-16, F-OQ-B17 |
| A new checker each round, or the same one | A new one, to keep it blind, told what the previous check reported so that rounds build on each other. | F-AD-18, F-AE-26, F-OQ-B17 |
| Asking the owner | Never. The run decides, states what it decided, and continues. | F-AE-42, F-AE-43, F-IN-36, F-IN-37, F-AD-39 |
| Reporting decisions | A list of each choice made for the owner, because such decisions otherwise stand unexamined. | F-AE-45, F-IN-36 |
| Shape of the final prompt | Outcome, purpose, constraints and done criteria; no steps; plain wording. | F-AE-01, F-AE-02, F-AE-05, F-AD-36, F-AD-43, F-IN-24, F-IN-30 |
| Keeping additions apart | The specialist's additions sit in one short list of recommendations, separate from the owner's requirements, so the reader can tell which is which. | F-AE-14, F-IN-38 |
| Size of the prompt | Proportionate to the request, with additions cut first when it runs long: over-specified prompts now hurt, and each line has to earn its place. | F-AE-06, F-AE-07, F-AE-08, F-IN-25, F-IN-34 |
| Packaging | A plain folder under the personal skills directory; the main file short, with briefs and evidence in files it links to directly. | F-AD-24, F-AD-31 |
| Stopping questions at the tool level | The skill removes the question tool while it is active. | F-AD-26 |

## Where the research does not support the design

- **Splitting framing and requirements into two agents.** The evidence supports isolating the checker. It does not clearly support separating the framing expert from the requirements expert: Anthropic lists consecutive phases of the same work as a poor place to split, and one researcher put it at about 60 percent that a single author for both would do at least as well (F-AE-33, F-AE-38, F-OQ-B14). The two experts are kept because the skill's owner specified them, and the loss this finding warns about is countered by the file handoff: the requirements expert reads the owner's message itself, not only the framing. A comparison of the two arrangements on the same inputs would settle it.
- **Naming no files.** Some vendor guidance lists relevant file locations among the contents of a good task description (F-AE-04). The owner's rule that the prompt names no files stands; the receiving lead finds them.
- **Never asking.** Vendors' own default for vague requirements is to interview the person first (F-AD-40). The evidence supports proceeding without questions only together with stated assumptions, which is the purpose of the decisions list.
- **A checker on every run.** On easy inputs a separate checker is overhead (F-AE-29, F-OQ-B15). It is kept on every run because the owner's requirement that nothing be lost is absolute.

## What the research could not tell us

- No source studied a pipeline that writes requirements; the measurements come from coding, planning and research tasks.
- No source measured a role line at the top of a task message to a Claude Code session.
- Documentation pages are undated; their dates in the sources file are bounds inferred from version numbers and model names.
- Several vendor pages that bear most directly on both questions are undated documentation and were counted separately from the dated sources.
- Pages that could not be read are listed at the end of each findings file and were not used as evidence.

## Lessons from use

The sections called "Rules that do not bend" and "How to read the owner" in the briefs do not come from published research. They come from a review of real uses of the previous version of this skill and of what happened in the sessions that received its prompts. That review is private and is not stored here. The patterns it found, stated generally:

- Questions placed after the prompt were mostly never read, and each unanswered question left the prompt without a decision, which resurfaced later as a stalled agent.
- Things the owner had stated outright were turned into questions or overruled.
- Sentences giving the receiving agent ownership were cut as role preamble, and the agent then stopped to ask.
- Approval steps, "stop and ask" conditions and bans on pushing or releasing were written in though the owner had not asked for them, and the owner had to come back to lift them.
- "Done" stopped short of the client being able to use the result, or needed something the agent did not have.
- A short hint about process was inflated into heavy mandatory process, and deadlines did not shape the prompt.
- The writer's own inferences entered the prompt as the owner's rules or as facts, and misfired.
- A thin request was built far larger than the client wanted.
- Requirements were narrowed, reversed or dropped, sometimes because the session reworded the owner's message before the skill saw it.
- Text meant to appear in the product was "corrected" under an instruction to copy it exactly.
- Replies after the first were sometimes patches or continuations that a fresh session could not use.

What the previous version did well is kept: acceptance written as a walk through the product in the user's words, behaviour stated as outcomes, facts found in the project that the owner did not type, fallbacks instead of stops, a record of decisions made for the client, and a final report that says what is done, what is not, and what is left for the owner.
