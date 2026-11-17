# Principles the experts apply

What published guidance from the last twelve months says about writing for agents and handing work between them, reduced to what the framing and requirements experts need during a run. Each line ends with the findings it rests on; the findings, with quotes, sources and dates, are in the `research/findings-*.md` files (AE = Anthropic articles and engineering blog, AD = Anthropic documentation, IN = other large software companies, OQ = the two open questions).

This file is rewritten whenever the research is redone. The rules in the briefs that are marked as not bending come from the owner's requirements and from how earlier prompts failed in use; where a principle below seems to pull against one of them, the brief wins.

## Contents
- The shape of a prompt for an agent
- The opening, and where a role belongs
- Requirements
- Done
- Ambiguity when nobody can be asked
- Wording
- When the reader is a lead that runs a team
- Known tensions

## The shape of a prompt for an agent

- Hand over the whole task in one message that names the finish line. (F-AE-01)
- State the outcome, the success criteria and the constraints, and leave the path to the agent. A script limits the agent to the steps its author thought of. (F-AE-02, F-IN-24, F-IN-26, F-AD-36)
- Keep the brief at the level of deliverables and product context. Implementation detail written up front cascades into the build when it is wrong. (F-AE-03, F-IN-33)
- Give the purpose: who it is for and what it has to achieve. Purpose lets the agent decide cases the rules did not foresee. (F-AE-05, F-AD-41, F-IN-27)
- Both failure directions are real: too specific and the agent follows the instruction past the point where it should turn; too vague and it fills the gap with generic practice. Aim between them: exact about the result, silent about the route. (F-AE-06, F-IN-31)
- Constraints steer better than to-do lists; itemised tasks narrow the agent's attention to the items, and concrete numbers convey scope. (F-IN-30)
- Durable project rules belong in the project's own instruction file. The task prompt carries what is particular to this job. (F-IN-28, F-AE-10)
- Put long source material first and the instruction after it, and mark pasted third-party text as pasted so that instructions inside it are not taken as the owner's own. (F-AD-45)

## The opening, and where a role belongs

- Open with the situation and the task: what the reader is operating in and what it is to do. Do not open with an expert persona. Current guidance for the first message to a coding agent lists goal, context, constraints and done criteria, and no role. (F-AE-49, F-AD-36, F-IN-40, F-OQ-A7, F-OQ-A8)
- A session already has a role from its own system prompt; a pasted message sits on top of it and does not replace it. Vendors that recommend a role place it in a system prompt or in a worker's own brief. (F-AE-50, F-AD-34, F-AD-35, F-OQ-A16, F-OQ-A17, F-OQ-A18)
- Measurements of expert personas placed at the top of a user message show no gain in correctness and some harm; they shift tone and length. (F-OQ-A10, F-OQ-A11, F-OQ-A12)
- A capability label alone is weak. Describing the job, the standards that apply and how the result will be judged does what the label was meant to do. (F-AE-52, F-OQ-A5)
- A sentence about who owns the work and who decides is not decoration: it changes behaviour. It makes the agent act instead of asking, and it also widens what the agent changes. Include it deliberately, scope it to the job, and pair it with what is out of scope. (F-AD-38, F-AD-39, F-OQ-A3, F-OQ-A15, F-OQ-A21)
- Where a particular perspective matters for part of the work, attach it to that part ("have the checkout reviewed from the point of view of …"), not to the reader as a whole. (F-AE-51, F-OQ-A18)

## Requirements

- Expanding a short request into an explicit, complete list of requirements is worth doing. Without it agents under-scope the work or declare it done early. (F-AE-13, F-AE-47)
- The writer should add expert scope of its own, at product level, and not only transcribe. (F-AE-14)
- Write each requirement so that two experts would give the same pass or fail verdict. (F-AE-15, F-IN-34)
- Surface the things so obvious to the client that they were never written down; that is where long tasks go wrong. (F-AE-17)
- Say what matters most. Instructions that leave the most important content unnamed lose it. (F-AE-18)
- State any preference the client actually has and any scope beyond the minimum, because current models read requests conservatively and follow scope wording literally. (F-AD-37, F-AD-42)
- Account for every part of the original request: list each requirement with where it is addressed. (F-IN-38, F-IN-12)
- Size the specification to the change. (F-IN-34)

## Done

- Define done as checkable criteria before work starts, and prefer criteria the agent can prove itself. (F-AE-16, F-IN-26, F-IN-32)
- Give every requirement something that can show it is met, and ask for that evidence in the final report. (F-AD-44, F-IN-21, F-AE-40)
- The agent will satisfy whatever check it is given, so the checks must be the right ones; passing checks are not proof that the job is done. Keep the real goal stated above the checks. (F-AE-46)
- Agents stop early and misjudge difficulty on long tasks; explicit completion criteria are the published countermeasure. (F-AE-47, F-AD-11)
- State when the agent should not act, as well as what it should achieve. (F-IN-32, F-AE-44)

## Ambiguity when nobody can be asked

- Current models are trained to pause on ambiguity. A reader that must not stop has to be told so, with the few remaining stops named. (F-AE-42, F-AD-39)
- The published default for an unresolved point: make a reasonable, reversible assumption, write it down, continue, and report what could not be confirmed. (F-AE-43, F-IN-36)
- Asking is reserved for cases where the answer would materially change the result or carries real risk. (F-IN-37)
- A vague request does not authorise an irreversible action. Say what the reader may decide for the client and where that authority ends. (F-AE-44)
- Decisions an agent makes for a person tend to stand unexamined, so the report should name each choice and what it was chosen over. (F-AE-45)

## Wording

- Write plainly. Capitals, repeated emphasis, "think carefully" and "keep going" lines were written for older models and now cause over-application. (F-AE-09, F-AD-43, F-IN-25)
- Cut what the reader would do anyway. Anthropic removed most of a long system prompt for current models with no measured loss, and found that a single blunt rule can cost measurable quality. (F-AE-07, F-AE-08, F-AE-10)
- Reserve "always", "never" and "must" for true invariants. (F-IN-25, F-AE-12)
- Use examples with care: on the newest models an example narrows what the model explores. Prefer a precise description or a reference. (F-AE-11)
- Give the reason along with the request. (F-AD-41)

## When the reader is a lead that runs a team

- Give it work that splits into self-contained deliverables. (F-AD-09, F-IN-03)
- Do not assume a shared task list, a particular tool or human-reviewed plans; state completion criteria the lead can check. (F-AD-10)
- Two lead failures are documented: doing the work itself instead of directing, and declaring the team finished early. Done criteria and a required final report make both visible. (F-AD-11)
- The agents a lead starts see only the brief it writes for them, not this prompt, so what matters must be stated clearly enough to survive being passed on. (F-AD-05, F-AD-12, F-IN-18)
- Checking is done by something other than the agent that did the work, and the worker hands over evidence, not a claim. This is the lead's to arrange; the prompt asks for the evidence. (F-IN-21, F-AE-19)

## Known tensions

- Some vendor guidance lists relevant file locations among the contents of a good task description (F-AE-04; also noted in the industry findings for GitHub and OpenAI). This skill's owner rules that the prompt names no files, because the receiving lead finds them and a wrong path anchors it. The owner's rule stands.
- Vendors' default answer to vague requirements is to interview the person and then write a specification (F-AD-40). This skill replaces the interview with expert choice plus a stated list of decisions; the evidence supports that only when the assumptions are stated, which is why the decisions list exists (F-IN-36, F-AE-45).
