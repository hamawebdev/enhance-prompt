# Anthropic's own articles and engineering blog — evidence for the prompt-building skill

Slice: anthropic.com (engineering, research, news) and Anthropic's two product blogs (claude.com/resources/articles, claude.dev/blog).
Window: 2025-11-17 to 2026-11-17. Retrieved: 2026-11-17 for every source.

Method. Each page was downloaded directly and converted to text; every quote below was checked by script as a verbatim substring of the downloaded page (curly and straight quotes treated as equal, whitespace collapsed). Dates are the "Published" date printed on the page and in its metadata.

Notes on the sites.
- anthropic.com/engineering now serves its posts at `/research/<slug>` (the `/engineering/<slug>` address redirects there). The engineering index lists 29 posts; 16 fall in the window and all 16 were downloaded.
- `claude.com/blog/<slug>` redirects to `claude.dev/blog/<slug>`. claude.dev is treated as an Anthropic site because claude.com links to it as its own blog and its bylines read "member of technical staff, Anthropic".
- Some claude.com pages show their example prompts and code as images or embeds that are not in the page text. Those examples could not be quoted (see "Could not verify").

# Sources

| ID | Title | Publisher | URL | Published | Retrieved | In window? |
|---|---|---|---|---|---|---|
| AE-01 | Harness design for long-running application development | Anthropic, Engineering | https://www.anthropic.com/research/harness-design-long-running-apps | 2026-03-24 | 2026-11-17 | Yes |
| AE-02 | Effective harnesses for long-running agents | Anthropic, Engineering | https://www.anthropic.com/research/effective-harnesses-for-long-running-agents | 2025-11-26 | 2026-11-17 | Yes |
| AE-03 | Building a C compiler with a team of parallel Claudes | Anthropic, Engineering | https://www.anthropic.com/research/building-c-compiler | 2026-02-05 | 2026-11-17 | Yes |
| AE-04 | Scaling Managed Agents: Decoupling the brain from the hands | Anthropic, Engineering | https://www.anthropic.com/research/managed-agents | 2026-04-08 | 2026-11-17 | Yes |
| AE-05 | The components of agent memory | Anthropic, Engineering | https://www.anthropic.com/research/components-of-agent-memory | 2026-11-06 | 2026-11-17 | Yes |
| AE-06 | How we built Claude Code auto mode: a safer way to skip permissions | Anthropic, Engineering | https://www.anthropic.com/research/claude-code-auto-mode | 2026-03-25 | 2026-11-17 | Yes |
| AE-07 | Demystifying evals for AI agents | Anthropic, Engineering | https://www.anthropic.com/research/demystifying-evals-for-ai-agents | 2026-01-09 | 2026-11-17 | Yes |
| AE-08 | An update on recent Claude Code quality reports | Anthropic, Engineering | https://www.anthropic.com/research/april-23-postmortem | 2026-04-23 | 2026-11-17 | Yes |
| AE-09 | Building multi-agent systems: when and how to use them (page heading "When to use multi-agent systems (and when not to)") | Anthropic, claude.com blog | https://claude.com/resources/articles/building-multi-agent-systems-when-and-how-to-use-them | 2026-01-23 (edited since: it links to an October 2026 post) | 2026-11-17 | Yes |
| AE-10 | Multi-agent coordination patterns: Five approaches and when to use them | Anthropic, claude.com blog | https://claude.com/resources/articles/multi-agent-coordination-patterns | 2026-04-10 | 2026-11-17 | Yes |
| AE-11 | Building agents: When to fold subagents into your main agent loop | Anthropic, claude.com blog | https://claude.com/resources/articles/building-agents-when-to-fold-subagents-into-your-main-agent-loop | 2026-10-22 | 2026-11-17 | Yes |
| AE-12 | How and when to use subagents in Claude Code | Anthropic, claude.com blog | https://claude.com/resources/articles/subagents-in-claude-code | 2026-04-07 | 2026-11-17 | Yes |
| AE-13 | Steering Claude Code: when to use CLAUDE.md, skills, hooks, and subagents | Anthropic, claude.com blog | https://claude.com/resources/articles/steering-claude-code-skills-hooks-rules-subagents-and-more | 2026-06-18 | 2026-11-17 | Yes |
| AE-14 | A field guide to Claude Fable 5: Finding your unknowns | Anthropic, claude.com blog | https://claude.com/resources/articles/a-field-guide-to-claude-fable-finding-your-unknowns | 2026-07-06 | 2026-11-17 | Yes |
| AE-15 | The new rules of context engineering for Claude 5 generation models | Anthropic, claude.dev blog | https://claude.dev/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models/ | 2026-07-24 | 2026-11-17 | Yes |
| AE-16 | Getting the most out of Opus 5.5 in Claude and Claude Code | Anthropic, claude.dev blog | https://claude.dev/blog/getting-the-most-out-of-opus-5-5/ | 2026-09-22 | 2026-11-17 | Yes |
| AE-17 | How the Claude Code team thinks about verification | Anthropic, claude.dev blog | https://claude.dev/blog/how-the-claude-code-team-thinks-about-verification/ | 2026-11-16 | 2026-11-17 | Yes |
| AE-18 | A harness for every task: dynamic workflows in Claude Code | Anthropic, claude.dev blog | https://claude.dev/blog/a-harness-for-every-task-dynamic-workflows-in-claude-code/ | 2026-06-02 | 2026-11-17 | Yes |
| AE-19 | Best practices for using Claude Opus 4.7 with Claude Code | Anthropic, claude.com blog | https://claude.com/resources/articles/best-practices-for-using-claude-opus-4-7-with-claude-code | 2026-04-16 | 2026-11-17 | Yes |
| AE-20 | Working with Claude Fable 5 in Claude Cowork | Anthropic, claude.com blog | https://claude.com/resources/articles/working-with-claude-fable-5-in-claude-cowork | 2026-07-16 | 2026-11-17 | Yes |
| AE-21 | Agent harness design: 3 patterns for harnessing Claude's intelligence | Anthropic, claude.com blog | https://claude.com/resources/articles/harnessing-claudes-intelligence | 2026-04-02 | 2026-11-17 | Yes |
| AE-22 | How the Claude Code team does code review | Anthropic, claude.dev blog | https://claude.dev/blog/solving-code-review-at-anthropic/ | 2026-10-15 | 2026-11-17 | Yes |
| AE-23 | Safely scaling multi-agent teams with Claude Fable 5.2 | Anthropic, claude.dev blog | https://claude.dev/blog/safely-scaling-multi-agent-teams-with-fable-5-2/ | 2026-11-09 | 2026-11-17 | Yes |
| AE-24 | Patterns and problems in multiagent systems | Anthropic, Research | https://www.anthropic.com/research/multiagent-systems | 2026-08-13 | 2026-11-17 | Yes |
| AE-25 | Long-running Claude for scientific computing | Anthropic, Research | https://www.anthropic.com/research/long-running-claude | 2026-03-23 | 2026-11-17 | Yes |
| AE-26 | New in Claude Managed Agents: dreaming, outcomes, and multiagent orchestration | Anthropic, claude.com blog | https://claude.com/resources/articles/new-in-claude-managed-agents | 2026-05-19 | 2026-11-17 | Yes |
| AE-27 | Common workflow patterns for AI agents | Anthropic, claude.com blog | https://claude.com/resources/articles/common-workflow-patterns-for-ai-agents-and-when-to-use-them | 2026-03-05 | 2026-11-17 | Yes |
| AE-28 | What a task costs on Opus 5.5 | Anthropic, claude.dev blog | https://claude.dev/blog/what-a-task-costs-on-opus-5-5/ | 2026-09-25 | 2026-11-17 | Yes |
| AE-29 | Which Claude model should you build with? Fable, Opus, Sonnet, or Haiku | Anthropic, claude.dev blog | https://claude.dev/blog/which-claude-model-should-you-build-with/ | 2026-11-09 | 2026-11-17 | Yes |
| AE-30 | Lessons from building Claude Code: How we use skills | Anthropic, claude.dev blog | https://claude.dev/blog/lessons-from-building-claude-code-how-we-use-skills/ | 2026-06-03 | 2026-11-17 | Yes |
| AE-31 | Using Claude Code: session management and 1M context | Anthropic, claude.com blog | https://claude.com/resources/articles/using-claude-code-session-management-and-1m-context | 2026-04-15 | 2026-11-17 | Yes |
| AE-32 | Claude Opus 4.6 (launch announcement) | Anthropic, News | https://www.anthropic.com/news/claude-opus-4-6 | 2026-02-05 | 2026-11-17 | Yes |
| AE-33 | Trustworthy agents in practice | Anthropic, Research | https://www.anthropic.com/research/trustworthy-agents | 2026-04-09 | 2026-11-17 | Yes |
| AE-34 | Measuring AI agent autonomy in practice | Anthropic, Research | https://www.anthropic.com/research/measuring-agent-autonomy | 2026-02-18 | 2026-11-17 | Yes |
| AE-35 | Automating eval design and hillclimbing with Claude | Anthropic, claude.dev blog | https://claude.dev/blog/automating-eval-design-and-hillclimbing/ | 2026-09-28 | 2026-11-17 | Yes |
| AE-36 | Improving skill-creator: Test, measure, and refine Agent Skills | Anthropic, claude.com blog | https://claude.com/resources/articles/improving-skill-creator-test-measure-and-refine-agent-skills | 2026-03-03 | 2026-11-17 | Yes |
| AE-37 | Using Claude Code: Spending your effort | Anthropic, claude.dev blog | https://claude.dev/blog/spending-your-effort/ | 2026-09-25 | 2026-11-17 | Yes |
| AE-38 | Claude Code in the cloud: a field guide to cloud sessions | Anthropic, claude.dev blog | https://claude.dev/blog/claude-code-in-the-cloud/ | 2026-10-06 | 2026-11-17 | Yes |
| AE-39 | Loop engineering: Getting started with loops | Anthropic, claude.com blog | https://claude.com/resources/articles/getting-started-with-loops | 2026-06-30 | 2026-11-17 | Yes |
| AE-40 | Maximizing the value of your Claude Code sessions | Anthropic, claude.com blog | https://claude.com/resources/articles/maximizing-the-value-of-your-claude-code-sessions | 2026-08-14 | 2026-11-17 | Yes |
| AE-41 | Which Claude model is best to use for knowledge work (URL slug: using-claude-opus-5-5-as-your-daily-driver-for-knowledge-work) | Anthropic, claude.com blog | https://claude.com/resources/articles/using-claude-opus-5-5-as-your-daily-driver-for-knowledge-work | 2026-11-12 | 2026-11-17 | Yes |
| AE-42 | Introducing dynamic workflows | Anthropic, claude.com blog | https://claude.com/resources/articles/introducing-dynamic-workflows-in-claude-code | 2026-05-28 | 2026-11-17 | Yes |
| AE-43 | How AI agents shape experts' judgment calls | Anthropic, Research | https://www.anthropic.com/research/agents-judgment-calls | 2026-10-27 | 2026-11-17 | Yes |
| BG-01 | Building effective agents | Anthropic, Engineering | https://www.anthropic.com/research/building-effective-agents | 2024-12-19 | 2026-11-17 | No |
| BG-02 | How we built our multi-agent research system | Anthropic, Engineering | https://www.anthropic.com/research/multi-agent-research-system | 2025-06-13 | 2026-11-17 | No |
| BG-03 | Effective context engineering for AI agents | Anthropic, Engineering | https://www.anthropic.com/research/effective-context-engineering-for-ai-agents | 2025-09-29 | 2026-11-17 | No |
| BG-04 | Best practices for prompt engineering | Anthropic, claude.com blog | https://claude.com/resources/articles/best-practices-for-prompt-engineering | 2025-11-10 (seven days before the window opens) | 2026-11-17 | No |

In-window sources: 43 (AE-01 to AE-43). Background sources: 4 (BG-01 to BG-04).

# Findings

## A. Shape of the final prompt

## F-AE-01 — Hand over the whole task in one message that names the finish line and says when to stop and ask.
- Evidence: "Give the whole task in one message. Name the finish line, like “the tests pass” or “every endpoint is migrated.”" — AE-16
- Evidence: "describe your goal, the finished output, and when you want it to stop and ask" — AE-41
- Evidence: "Ambiguous prompts conveyed progressively across many turns tend to reduce both token efficiency and, sometimes, overall quality." — AE-19
- Bears on: final-prompt shape
- Strength: direct recommendation

## F-AE-02 — State the outcome and how it will be judged; do not script the steps, because a script limits the agent to the steps the author thought of.
- Evidence: "A step-by-step prompt can also limit it to the steps you thought of; a goal gives it room to find a better path." — AE-20
- Evidence: "Pick an outcome you're responsible for and say how you'd judge it, then let Claude propose the steps to get there." — AE-20
- Evidence: "State the goal and the constraints, not every step." — AE-30
- Evidence: "It states the goal and what the final output looks like, and leaves the approach to Claude." — AE-41
- Bears on: final-prompt shape | requirements
- Strength: direct recommendation

## F-AE-03 — Keep the spec at the level of deliverables and product context; implementation detail written up front cascades into the build when it is wrong.
- Evidence: "if the planner tried to specify granular technical details upfront and got something wrong, the errors in the spec would cascade into the downstream implementation" — AE-01
- Evidence: "It seemed smarter to constrain the agents on the deliverables to be produced and let them figure out the path as they worked." — AE-01
- Bears on: requirements | final-prompt shape
- Strength: described practice (the author's stated reason for his harness design)

## F-AE-04 — Tension to settle: Anthropic's Opus 4.7 guidance lists file locations among the things a good task description contains, while the skill forbids naming files.
- Evidence: "Well-specified task descriptions that incorporate intent, constraints, acceptance criteria, and relevant file locations give Opus 4.7 the context it needs to deliver stronger outputs." — AE-19
- Note: the other three items (intent, constraints, acceptance criteria) match the skill's shape. The later Opus 5.5 and Fable 5 posts (AE-16, AE-20, AE-41) describe the same shape without mentioning file locations.
- Bears on: final-prompt shape
- Strength: direct recommendation

## F-AE-05 — Give the purpose (who it is for, what it has to accomplish) rather than a list of rules; purpose lets the agent decide cases the rules did not foresee.
- Evidence: "You wouldn't hand them a list of rules, but chances are you'd tell them who it's for, when it's needed, and what it has to accomplish, and trust them to make good decisions from there." — AE-20
- Evidence: "But a constraint only tells Claude what not to do. Context tells it what the work is for, so it can make the right call in situations your constraints didn't anticipate." — AE-20
- Bears on: framing | final-prompt shape
- Strength: direct recommendation

## F-AE-06 — Both failure directions are real: too specific and the agent follows the instruction past the point where it should pivot; too vague and it fills the gap with generic best practice.
- Evidence: "If you are too specific, Claude will follow your instructions even when a pivot may be more appropriate." — AE-14
- Evidence: "If you are too vague, Claude will often make choices and assumptions based on industry best practices that may not be a fit for your task." — AE-14
- Bears on: requirements | final-prompt shape
- Strength: opinion (a named Anthropic engineer's working practice)

## F-AE-07 — Cut the prompt hard: Anthropic removed over 80% of Claude Code's system prompt for current models with no measured loss, and found conflicting instructions cost the model effort.
- Evidence: "We removed over 80% of Claude Code’s system prompt for models like Claude Opus 5 and Claude Fable 5 with no measurable loss on our coding evaluations." — AE-15
- Evidence: "Overall, we found that we were overconstraining Claude Code, both through our system prompt and in our CLAUDE.md files and skills." — AE-15
- Evidence: "Claude must think more carefully about these overlapping and conflicting messages before deciding what to do" — AE-15
- Bears on: final-prompt shape | requirements
- Strength: measured result

## F-AE-08 — A single blunt rule can cost measurable quality, so each line of a standing prompt should earn its place.
- Evidence: "one addition to the system prompt caused an outsized effect on intelligence in Claude Code" — AE-08
- Evidence: "One of these evaluations showed a 3% drop for both Opus 4.6 and 4.7." — AE-08
- Note: the line was a word limit on replies ("keep text between tool calls to ≤25 words…"). Anthropic's stated response was to run ablations line by line on every system-prompt change.
- Bears on: final-prompt shape
- Strength: measured result

## F-AE-09 — Drop "think carefully" lines, repeated instructions and emphasis written for older models.
- Evidence: "Remove “think carefully,” “think step by step,” and similar lines from your prompts and your saved instructions." — AE-16
- Evidence: "We found we could delete these repeat examples and put instructions on how to use tools in the tool descriptions rather than the system prompt." — AE-15
- Evidence: "newer models have better judgement and can handle these decisions well without explicit rules" — AE-15
- Bears on: final-prompt shape
- Strength: direct recommendation

## F-AE-10 — Do not restate what the model would do anyway; spend the words on what is particular to this client and project.
- Evidence: "A skill that restates what Claude would do by default adds context without adding value." — AE-30
- Evidence: "Avoid stating ‘the obvious’ things Claude should know by looking at your file system or your repo." — AE-15
- Evidence: "every token added depletes Claude’s attention budget and it is wasteful to pre-load context with rarely used instructions" — AE-21
- Bears on: requirements | final-prompt shape
- Strength: direct recommendation

## F-AE-11 — Use examples with care: on the newest models an example narrows what the model explores, so prefer a precise description, a reference, or a named list of what to avoid.
- Evidence: "With our newest models, we’ve found that giving examples actually constrains them to a certain exploration space." — AE-15
- Evidence: "A general instruction like “avoid a generic look” mostly swaps one default for another. A list of specific patterns works much better." — AE-16
- Evidence: "We find that positive examples of the voice you want work better than negative “Don’t do this” instructions." — AE-19
- Note: AE-19 (April 2026, Opus 4.7) and AE-15 (July 2026, Claude 5 models) point different ways; AE-15 is about tool-use examples and is the later statement. Treat examples as a deliberate choice, not a default.
- Bears on: final-prompt shape
- Strength: direct recommendation (with a conflict between posts)

## F-AE-12 — Where a hard prohibition must hold, a prompt line is the wrong tool; say so in the prompt only as context and rely on the project's enforcement.
- Evidence: "When there's something that absolutely must not happen, an instruction is the wrong tool." — AE-13
- Bears on: final-prompt shape | framing (out-of-scope items)
- Strength: direct recommendation

## B. Requirements

## F-AE-13 — Expanding a short request into an explicit, complete requirement list is worth doing: without it agents under-scope or declare the job done early.
- Evidence: "we prompted the initializer agent to write a comprehensive file of feature requirements expanding on the user’s initial prompt" — AE-02
- Evidence: "a later agent instance would look around, see that progress had been made, and declare the job done" — AE-02
- Evidence: "Without the planner, the generator under-scoped: given the raw prompt, it would start building without first speccing its work" — AE-01
- Bears on: requirements
- Strength: described practice (observed across two harness experiments)

## F-AE-14 — The requirements writer should add its own expert scope, not only transcribe; Anthropic's planner was told to be ambitious and stay at product level.
- Evidence: "I prompted it to be ambitious about scope and to stay focused on product context and high level technical design rather than detailed technical implementation." — AE-01
- Bears on: requirements
- Strength: described practice

## F-AE-15 — Write each requirement so that two experts would give the same pass or fail verdict, and state everything the checker will check.
- Evidence: "A good task is one where two domain experts would independently reach the same pass/fail verdict." — AE-07
- Evidence: "Everything the grader checks should be clear from the task description; agents shouldn’t fail due to ambiguous specs." — AE-07
- Evidence: "Two engineers reading the same initial spec could come away with different interpretations on how the AI should handle edge cases." — AE-07
- Bears on: requirements | checker
- Strength: direct recommendation

## F-AE-16 — Define "done" as checkable criteria before work starts, and prefer criteria an agent can prove.
- Evidence: "agreeing on what "done" looked like for that chunk of work before any code was written" — AE-01
- Evidence: "Write each task as a self-contained ticket that states what's wrong, what done looks like, and how to prove it." — AE-38
- Evidence: "When you define the success criteria, Claude doesn’t have to make a determination on what is “good enough” and end the loop early." — AE-39
- Bears on: requirements | final-prompt shape
- Strength: direct recommendation

## F-AE-17 — Surface the "unknown knowns": things so obvious to the client they were never written down are where a long task goes wrong.
- Evidence: "Unknown Knowns: What's so obvious I’d never write it down, but would recognize it if I saw it?" — AE-14
- Evidence: "Claude Fable is the first model where I find the quality of the work is bottlenecked by my ability to clarify its unknowns." — AE-14
- Note: the post's own remedy is to have Claude interview the user, which this skill rules out; the usable part is the checklist of unknowns for the framing and requirements experts to resolve by choice.
- Bears on: framing | requirements
- Strength: opinion (a named Anthropic engineer's working practice)

## F-AE-18 — Say what matters most; instructions that left the most important content unnamed lost 28% of the facts in a measured test.
- Evidence: "The contract terms were the most important part of the wiki, but the instructions didn’t say that." — AE-05
- Evidence: "When we graded the brief generated from this improved wiki, 100% of the criteria could be met, up from 72%." — AE-05
- Bears on: requirements | final-prompt shape
- Strength: measured result

## C. The independent checker

## F-AE-19 — The author should not grade its own work: agents praise what they produced, and a separate skeptical evaluator is easier to tune than a self-critical author.
- Evidence: "When asked to evaluate work they've produced, agents tend to respond by confidently praising the work—even when, to a human observer, the quality is obviously mediocre." — AE-01
- Evidence: "tuning a standalone evaluator to be skeptical turns out to be far more tractable than making a generator critical of its own work" — AE-01
- Evidence: "Self-preferential bias refers to Claude’s tendency to prefer its own results or findings, especially when asked to verify or judge them against a rubric." — AE-18
- Bears on: checker | question B
- Strength: described practice (consistent across three posts)

## F-AE-20 — Run the checker in its own context window so the author's reasoning cannot influence it; Anthropic reports up to 10 points better task success from this design.
- Evidence: "A separate grader evaluates the output against your criteria in its own context window, so it isn't influenced by the agent's reasoning." — AE-26
- Evidence: "In testing, outcomes improved task success by up to 10 points over a standard prompting loop, with the largest gains on the hardest problems." — AE-26
- Evidence: "having a separate grader check Claude’s work against a rubric improved task success by up to 10 points over a standard prompting loop" — AE-17
- Bears on: checker | question B
- Strength: measured result

## F-AE-21 — Give the checker the original request and the output, and withhold the author's explanations: Anthropic measured worse judging when the author's prose was included, and worse again when the user's words were removed.
- Evidence: "We strip assistant text so the agent can't talk the classifier into making a bad call." — AE-06
- Evidence: "Including assistant messages and tool results caused a drop in performance on our overeagerness testset." — AE-06
- Evidence: "A tool-calls-only variant had the lowest false-negative rate still but lost the user-intent anchor, blocking actions the user had plainly asked for." — AE-06
- Note: this is a safety classifier, not a requirements checker, but it is the closest measured test in the slice of "blind to reasoning, anchored on the user's own words".
- Bears on: checker | handoff
- Strength: measured result

## F-AE-22 — A checker with no stated criteria approves everything; give it explicit criteria and require a full pass, not a sample.
- Evidence: "A verifier told only to check whether output is good, with no further criteria, will rubber-stamp the generator's output." — AE-10
- Evidence: "The verifier runs one or two tests, observes them pass, and declares success." — AE-09
- Evidence: "The verifier does not need to understand why the artifact was built as it was. It only needs to determine whether the artifact meets the specified criteria." — AE-09
- Bears on: checker
- Strength: direct recommendation

## F-AE-23 — Expect the checker to talk itself out of real findings; its instructions must stop it waving issues through.
- Evidence: "I watched it identify legitimate issues, then talk itself into deciding they weren't a big deal and approve the work anyway." — AE-01
- Evidence: "I calibrated the evaluator using few-shot examples with detailed score breakdowns." — AE-01
- Bears on: checker
- Strength: described practice

## F-AE-24 — Write the checker's rubric as checkable claims, judge each dimension separately, let it answer "unknown", and judge the product rather than the path.
- Evidence: "a rubric written as checkable claims (not a 1-to-5 scale)" — AE-35
- Evidence: "grade each dimension with an isolated LLM-as-judge rather than using one to grade all dimensions" — AE-07
- Evidence: "To avoid hallucinations, give the LLM a way out, like providing an instruction to return “Unknown” when it doesn’t have enough information." — AE-07
- Evidence: "it’s often better to grade what the agent produced, not the path it took" — AE-07
- Bears on: checker
- Strength: direct recommendation

## F-AE-25 — The send-back loop needs a round cap and a fallback, or author and checker keep each other busy without converging.
- Evidence: "Review has to converge. An agent author and an agent reviewer can keep each other busy indefinitely." — AE-22
- Evidence: "A round cap. After three rounds, the reviewer asks the author to step back and reconsider the approach." — AE-22
- Evidence: "A maximum iteration limit with a fallback strategy (escalate to a human, return the best attempt with caveats) prevents this from becoming an infinite loop." — AE-10
- Evidence: "Set clear stopping criteria before you start iterating." — AE-27
- Note: for a skill that never asks the user, the fitting fallback from AE-10 is "return the best attempt with caveats". Three rounds is the cap Anthropic's own team uses in two posts (AE-22, AE-17).
- Bears on: checker | run mechanics
- Strength: direct recommendation

## F-AE-26 — After the first pass, re-check only what changed, do not repeat findings, and report a class of gap once so every instance is fixed.
- Evidence: "Flag the class of bug, so the author fixes every instance, not one line." — AE-22
- Evidence: "No repeats of findings already posted." — AE-22
- Evidence: "We point each pass at context from earlier rounds and past failures rather than re-checking everything from scratch." — AE-17
- Evidence: "Noise costs more when the author is an agent." — AE-22
- Note: this bears on what "blind" should mean across rounds. The checker stays blind to the authors' reasoning, but Anthropic's practice is that later rounds do see the earlier findings.
- Bears on: checker | run mechanics
- Strength: described practice

## F-AE-27 — Tune one checker rather than stacking a second one on top, and keep the checker's criteria out of the author's reach.
- Evidence: "Adding a second, more expensive, reviewer on top of the primary one is often a worse approach than tuning the primary." — AE-17
- Evidence: "If a change can modify the check that judges it, the check is broken." — AE-17
- Bears on: checker | run mechanics
- Strength: described practice

## F-AE-28 — Agents built on the same model with similar context make the same mistakes, so the checker's value comes from its different context (and, in evals, a different judge model).
- Evidence: "when one agent makes a bad decision, it is likely that many agents will make that same bad decision" — AE-24
- Evidence: "All that differentiates one agent from another is its context, its scaffolding, and the model that underlies it." — AE-24
- Evidence: "You pick the judge model, and it should not be the model you are testing." — AE-35
- Evidence: "They judge outputs without knowing which is which, so you can tell whether a change actually helped." — AE-36
- Bears on: checker | question B
- Strength: described practice (AE-24 is observation across experiments; AE-35 is advice for eval judges, applied here by analogy)

## F-AE-29 — A checker is a cost that pays off on hard work and is overhead on easy work; the skill can scale it to the task.
- Evidence: "It is worth the cost when the task sits beyond what the current model does reliably solo." — AE-01
- Evidence: "more capable orchestrator models (like Claude Opus 4.5) are increasingly able to evaluate subagent work directly without a separate verification step" — AE-09
- Evidence: "add evaluator-optimizer loops only when you can measure the quality improvement" — AE-27
- Evidence: "When the cost of a wrong answer is high, a workflow gives Claude independent attempts at the problem and adversarial agents working to break the result before you see it." — AE-42
- Bears on: checker | run mechanics
- Strength: described practice

## D. Handoff between stages

## F-AE-30 — Pass source text word for word, not as a summary: in a measured test, summarising into a shared table kept 41 of 57 facts and quoting verbatim kept all 57.
- Evidence: "Each contract got its own page in the wiki, written by a single agent, which quoted the terms word for word rather than summarizing them into a shared table." — AE-05
- Evidence: "When we graded the brief generated from this improved wiki, 100% of the criteria could be met, up from 72%." — AE-05
- Bears on: handoff | checker
- Strength: measured result

## F-AE-31 — Each summarising step drops constraints, especially edge cases and prohibitions, so every stage should receive the original paste itself.
- Evidence: "Each summarization step is lossy, and details like edge-case requirements or "don't do X" constraints can get lost." — AE-18
- Evidence: "After several such handoffs, critical details are often lost or summarized away." — AE-10
- Evidence: "irreversible decisions to selectively retain or discard context can lead to failures" — AE-04
- Bears on: handoff
- Strength: described practice

## F-AE-32 — Hand work between agents as files or artifacts, because a subagent's reply contains only what it chose to report.
- Evidence: "Communication was handled via files: one agent would write a file, another agent would read it and respond either within that file or with a new file that the previous agent would read in turn." — AE-01
- Evidence: "Just keep in mind that the main session only gets back what the subagent chose to report." — AE-40
- Evidence: "Each call still hands back a lossy summary" — AE-11
- Evidence: "I make a new session and pass any artifacts to the prompt. This gives Claude a fresh context window but with all of the information it compiled from your planning." — AE-14
- Bears on: handoff | run mechanics
- Strength: described practice

## F-AE-33 — Split work between agents by what context each needs, not by job title; role-by-role pipelines play a telephone game, while black-box verification is a clean split.
- Evidence: "When agents are split by problem type, they engage in a "telephone game," passing information back and forth with each handoff degrading fidelity." — AE-09
- Evidence: "Sequential phases of the same work. Planning, implementation, and testing of the same feature share too much context." — AE-09
- Evidence: "Blackbox verification. A verifier that only needs to run tests and report results does not require implementation context." — AE-09
- Evidence: "An agent that has seen the result of each earlier step can connect them, which leads to richer outputs and better insights than a set of summaries handed back by subagents." — AE-11
- Note: applied to the skill, the framer and the requirements writer share almost all their context (a "problematic" boundary in AE-09's terms), while the blind checker is the kind of boundary both posts endorse.
- Bears on: handoff | run mechanics | question B
- Strength: direct recommendation

## E. Run mechanics: subagents, agent teams, cost

## F-AE-34 — Multi-agent designs cost several times more tokens; add agents only for context protection, parallel work, or specialisation.
- Evidence: "In our testing, multi-agent implementations typically use 3-10x more tokens than single-agent approaches for equivalent tasks." — AE-09
- Evidence: "we’ve seen teams invest months building elaborate multi-agent architectures only to discover that improved prompting on a single agent achieved equivalent results" — AE-09
- Evidence: "parallelism and specialization have to earn their coordination cost" — AE-18
- Evidence: "The harness was over 20x more expensive, but the difference in output quality was immediately apparent." — AE-01
- Bears on: run mechanics | question B
- Strength: measured result

## F-AE-35 — Agent teams are the heavier option: each teammate is a separate session that keeps spending until it exits, about seven times a standard session.
- Evidence: "Our costs docs put a team at about seven times the tokens of a standard session when teammates run in plan mode." — AE-28
- Evidence: "Each teammate is a separate Claude Code instance with its own context window, and it keeps using tokens until it exits." — AE-28
- Evidence: "With agent teams, subagents coordinate across separate sessions rather than within one, which makes them heavier and more expensive." — AE-12
- Bears on: question B | run mechanics
- Strength: measured result (figure attributed by the post to Anthropic's cost documentation)

## F-AE-36 — Anthropic's selection rule: subagents for short, bounded subtasks with a clear output; agent teams for long-running, independent, parallel work or when workers must talk to each other.
- Evidence: "Choose orchestrator-subagent when subtasks are short, focused, and produce clear outputs." — AE-10
- Evidence: "Choose agent teams when subtasks benefit from sustained, multi-step work." — AE-10
- Evidence: "For most use cases, we recommend starting with orchestrator-subagent. It handles the widest range of problems with the least coordination overhead." — AE-10
- Evidence: "Subagents report back to the main conversation but can't talk to one another. For tasks where subagents need to communicate, use agent teams." — AE-12
- Evidence: "best for tasks that split into independent, read-heavy work like codebase reviews" — AE-32
- Bears on: question B
- Strength: direct recommendation

## F-AE-37 — A fresh-context subagent is Anthropic's stated tool for an unbiased review, and its own team uses one before every pull request.
- Evidence: "a subagent provides a clean slate because it doesn't inherit the assumptions, context, or blind spots from the primary conversation" — AE-12
- Evidence: ""Use a subagent that does not see our previous discussion" ensures clean evaluation" — AE-12
- Evidence: "Then a subagent reviews the diff with fresh context." — AE-22
- Evidence: "They are effective at verification, parallel work, and modular permissioning." — AE-11
- Evidence: "“Spin up a subagent to verify the result of this work based on the following spec file”" — AE-31
- Bears on: question B | checker
- Strength: direct recommendation

## F-AE-38 — For one chain of dependent steps, a single session is usually cleaner than a relay, and orchestration costs more than it saves.
- Evidence: "When step two needs the full output of step one, and step three needs both, a single session handling the chain is usually cleaner than a relay of subagents passing state through files." — AE-12
- Evidence: "Skip it for one chain of dependent steps or for work that fits in one context window. There, the planning and merging cost more than they save." — AE-29
- Evidence: "a single agent with skills frequently outperformed both the one-prompt-for-everything design and the subagent design on quality, and often at a lower cost and latency per task" — AE-11
- Note: the same post (AE-12) also lists pipelines as a fit for subagents ("The design subagent isn't distracted by implementation concerns, the implementation subagent works from a clean spec, and the testing subagent evaluates the result independently."). The posts agree on the checker and differ on whether the upstream stages deserve separate contexts.
- Bears on: question B | run mechanics
- Strength: direct recommendation

## F-AE-39 — Current agents cooperate well when one treats another as a call with defined input and output, and poorly as long-lived peers; prescribing roles or a hierarchy to a peer swarm made little difference.
- Evidence: "insofar as they are able to treat other agents as tool invocations—that is, with well-defined inputs (prompts) and outputs (responses and artifacts)—they can work together efficiently" — AE-24
- Evidence: "Where agents currently stumble, however, is in treating each other as more like distinct, long-lived peers" — AE-24
- Evidence: "But these prompts did not make much difference." — AE-24
- Bears on: question B | question A
- Strength: measured result (experiments across five models; the roles comparison is reported without figures)

## F-AE-40 — When delegating to a subagent, state the scope and the output wanted, and have the lead check the evidence that comes back.
- Evidence: "Being explicit matters. Specify the scope, request parallel execution when tasks are independent, and describe the desired output." — AE-12
- Evidence: "When a subagent reports back, check its evidence before you accept it." — AE-16
- Evidence: "it spawns a verification subagent with the artifact to verify, clear success criteria, and tools to perform verification" — AE-09
- Bears on: run mechanics | final-prompt shape (what the lead is told about delegating)
- Strength: direct recommendation

## F-AE-41 — Every stage in a pipeline encodes a guess about what the model cannot do alone; test stages by removing one at a time and drop those that no longer change the result.
- Evidence: "every component in a harness encodes an assumption about what the model can't do on its own, and those assumptions are worth stress testing" — AE-01
- Evidence: "harnesses encode assumptions about what Claude can’t do on its own" — AE-04
- Bears on: run mechanics
- Strength: described practice

## F. Autonomy without asking

## F-AE-42 — Claude is trained to pause on ambiguity, so a run that must not ask has to say so and name the few stops that remain.
- Evidence: "we construct training scenarios that place Claude in ambiguous situations, and then reinforce Claude’s choice to pause, rather than to assume" — AE-33
- Evidence: "On the most complex tasks, Claude Code stops to ask for clarification more than twice as often as humans interrupt it." — AE-34
- Evidence: "Stop and ask only when you can't continue without me, or before anything destructive: deleting data, force-pushing, or changing anything outside this repository." — AE-16
- Evidence: "It follows instructions that name these stops. Name the stops you want, too." — AE-16
- Bears on: final-prompt shape | run mechanics
- Strength: direct recommendation

## F-AE-43 — The published default for unresolved ambiguity is: take the conservative option, write the decision down, keep going, and report what could not be confirmed.
- Evidence: "If you hit an edge case that forces you to deviate from the plan, pick the conservative option, log it under 'Deviations', and keep going." — AE-14
- Evidence: "Add “Mark anything you couldn’t confirm, and say where you looked” to the request." — AE-16
- Evidence: "End every run with three headings: Blocked on me, Changed, Found." — AE-16
- Evidence: "higher effort levels will get more work done but Claude will also make more assumptions on my behalf" — AE-37
- Note: the AE-37 line is a reminder that an agent told to work hard and not ask will make more choices silently, which is why the log of decisions matters.
- Bears on: final-prompt shape | run mechanics
- Strength: direct recommendation (AE-14 is one engineer's example prompt)

## F-AE-44 — A vague request does not authorise an irreversible action; the prompt should state what the lead may decide for the client and where that authority ends.
- Evidence: "The prompt establishes what is authorized; everything the agent chooses on its own is unauthorized until the user says otherwise." — AE-06
- Evidence: "Inside the subagent, the orchestrator's instruction is the user message, so tasks look fully authorized." — AE-06
- Note: the second quote matters for a lead that runs a team: whatever the lead writes reads as the client's own instruction to its workers, so mistaken scope in the final prompt is passed down as if authorised.
- Bears on: framing | final-prompt shape
- Strength: described practice (design rationale for a shipped feature)

## F-AE-45 — Decisions an agent makes for a person tend to stand unexamined, so the after-report should name each choice and the alternative it rejected.
- Evidence: "Across all four combined, the result was 86%." — AE-43
- Evidence: "But they rarely made a strong case for why an expert might prefer the other option, which might have helped analysts make a better-informed choice." — AE-43
- Note: 86% is the share of analytical decisions on which 50 professional analysts ended up matching the option their agent had been set to favour.
- Bears on: run mechanics (the report of resolved ambiguities) | framing
- Strength: measured result

## G. Long-running work

## F-AE-46 — For unattended work the checks must be right, because the agent will satisfy whatever check it is given, and passing checks are not proof the job is done.
- Evidence: "it’s important that the task verifier is nearly perfect, otherwise Claude will solve the wrong problem" — AE-03
- Evidence: "For autonomous systems, it is easy to see tests pass and assume the job is done, when this is rarely the case." — AE-03
- Evidence: "your job shifts from reading every diff to defining what “done” looks like and reviewing the evidence" — AE-17
- Bears on: requirements | final-prompt shape
- Strength: described practice

## F-AE-47 — Agents stop early and misjudge difficulty on long tasks; explicit completion criteria are the published countermeasure.
- Evidence: "Agents tend to give up on hard problems and misjudge their difficulty." — AE-23
- Evidence: "Agentic laziness refers to when Claude stops before finishing a particularly complex, multi-part task and declares the job done after partial progress" — AE-18
- Evidence: "These features were all initially marked as “failing” so that later coding agents would have a clear outline of what full functionality looked like." — AE-02
- Bears on: requirements | final-prompt shape
- Strength: described practice

## F-AE-48 — Autonomous work suits tasks that are well scoped with clear success criteria, and the human's time is best spent on the instructions that state deliverables and context.
- Evidence: "These are tasks where the work is well-scoped, the success criteria are clear, and human oversight can be occasional rather than continuous." — AE-25
- Evidence: "you should spend most of your time (in consultation with Claude), crafting a set of instructions that clearly articulates the project’s deliverables and relevant context" — AE-25
- Bears on: framing | final-prompt shape
- Strength: direct recommendation

## H. Role and persona

## F-AE-49 — In-window Anthropic guidance frames the opening of a prompt as situation and task, not persona: tell Claude what it is operating in and what it is doing, and treat it as a capable engineer being delegated to.
- Evidence: "A system prompt is heavily tied to the product context. It tells Claude what product it’s operating in and what it’s doing." — AE-15
- Evidence: "treat Claude more like a capable engineer you’re delegating to than a pair programmer you’re guiding line by line" — AE-19
- Note: none of the 43 in-window sources recommends opening a prompt with "You are a senior X". The example task prompts that could be read (in AE-14, AE-16, AE-18, AE-25) do not open with a role; the only ones that do are the specialised-subagent system prompts in AE-09 (see F-AE-51). This is absence of a recommendation, not a tested result.
- Bears on: question A | framing
- Strength: described practice

## F-AE-50 — A Claude Code session already has a role from its own system prompt; added instructions sit on top of it rather than replacing it.
- Evidence: "It doesn’t modify Claude’s role; it just adds instructions to its default role." — AE-13
- Note: the sentence describes the append-system-prompt flag. The same post reserves output styles for "Significant role changes (code assistant to general assistant)".
- Bears on: question A
- Strength: described practice

## F-AE-51 — Where Anthropic does use personas in this period, it is for narrow subagents that need a stance different from the main agent, such as a skeptic or a critic.
- Evidence: "Different tasks sometimes require different personas, constraints, or instructions that conflict when combined." — AE-09
- Evidence: "Creating a skeptic persona subagent to review the rules to make sure they are in line will help avoid too many false positives." — AE-18
- Evidence: "You are a CRM specialist." — AE-09
- Note: the last quote is the first line of an example system prompt for a specialised subagent in AE-09 (January 2026, written against Sonnet 4.5).
- Bears on: question A | checker
- Strength: described practice

## F-AE-52 — A capability label alone is weak; describing the job and when it applies works better than naming an expert.
- Evidence: "Be specific about the trigger conditions, not just the capability." — AE-12
- Note: the post's example is that "Reviews code for security issues before commits" routes better than "security expert". This is about a subagent's description field, applied here by analogy.
- Bears on: question A
- Strength: direct recommendation (for a neighbouring case)

# Question A — what this slice's evidence says

Should the prompt handed to a Claude Code lead open with an expert role ("You are a senior X")?

This slice says no, with medium confidence, and says what to open with instead.

- Nothing in the 43 in-window sources recommends a persona opener for a capable agent, and the readable example task prompts do not use one; the exception is a set of specialised-subagent system prompts from January 2026 (F-AE-49, F-AE-51). The opening Anthropic describes is the situation and the task: what the agent is operating in, what it is doing, who the work is for and what it must accomplish (F-AE-05, F-AE-49).
- A Claude Code session already carries a role from its system prompt, and what the user adds sits on top of that role (F-AE-50). A "You are a senior X" line therefore competes with, or merely repeats, a role the lead already has.
- The direction of travel in this period is to remove standing instructions that restate what the model already does (F-AE-07, F-AE-09, F-AE-10). A generic expert label is the clearest case of such a line.
- The one direct statement on role prompting is seven days outside the window (BG-04, 2025-11-10): heavy role prompting is often unnecessary on modern models, and stating the perspective wanted is often more effective. It still allows a role where a specific persona, a consistent tone, or domain framing is needed.
- Personas do appear in-window, but for narrow subagents that need a different stance from the main agent: a skeptic, a critic, a specialist with its own tools (F-AE-51). That supports giving the skill's checker a skeptical stance. It does not support a persona opener for the lead.
- Prescribing roles to a group of peer agents made little difference in Anthropic's swarm experiments (F-AE-39), and a capability label routes worse than a description of the job (F-AE-52).

What the evidence supports for the skill's "role" field: write it as the lead's position and authority (whose project this is, that it decides on the client's behalf, where that authority stops; F-AE-44), not as an expertise claim.

Limits. No in-window source tests a role opener against no opener, so this rests on what Anthropic describes and omits, plus one near-window statement. The teammate covering Anthropic's documentation should check whether the current prompting guide still advises giving Claude a role; if it does, that is a direct recommendation that would outrank the inference here.

# Question B — what this slice's evidence says

Inside one run (framer → requirements writer → blind checker, with a send-back loop), should the experts be agent-team teammates or subagents?

This slice says subagents, with high confidence for the checker and medium-high for the pipeline as a whole. It also raises a third option for the first two stages.

- The pipeline matches Anthropic's stated case for subagents and not its case for agent teams. Subagents are for short, bounded subtasks with a clear output; agent teams are for sustained, independent, parallel work or for workers that must talk to each other (F-AE-36). The skill's stages are short and sequential, each returns one artifact, and the send-back loop can pass through the main session, so no stage needs to message another directly.
- Agent teams cost more for this shape with nothing gained: about seven times a standard session, each teammate spending until it exits (F-AE-35). Anthropic's default advice is to start with orchestrator-subagent (F-AE-36).
- A fresh-context subagent is the mechanism Anthropic names for an unbiased review, and the one its own team uses (F-AE-37). The measured gain from a separate grader comes from its separate context window (F-AE-20). A subagent starts without the conversation, which is what "has not seen their reasoning" requires; a teammate that persists across the run accumulates context, which works against blindness on later rounds.
- Agents currently cooperate well as calls with defined input and output, and poorly as long-lived peers (F-AE-39). The pipeline is the first kind.
- Third option, for the framer and requirements writer only: several posts say a chain of dependent steps is usually cleaner in one session, that splitting by job title causes handoff loss, and that planning and specification share too much context to separate (F-AE-33, F-AE-38). On that reading the framing and requirements work could run in the main session or in a single subagent, with only the checker isolated. The same post that warns against relays also lists pipelines as a fit for subagents (note under F-AE-38), so the slice does not settle this; it does settle that neither stage should be a teammate.
- Whichever is chosen, the handoff evidence applies: pass the original paste and each artifact as files, word for word, never as a summary (F-AE-30, F-AE-31, F-AE-32), and cap the loop (F-AE-25).

Limits. None of these sources examines a prompt-writing pipeline; the nearest are the planner–generator–evaluator harness (AE-01) and the code-review flow (AE-22). The practical differences between Claude Code agent teams and subagents (how each is started, what context each inherits) are documented on the docs site, which is another teammate's slice; this slice has the selection rule and the cost, not the mechanics.

# Where the in-window material is thin

- Role and persona openers: no in-window source addresses them head-on (see Question A).
- A template for briefing another agent: the well-known four-part list (objective, output format, tools and sources, boundaries) is from June 2025 (BG-02). In-window posts repeat parts of it (F-AE-40, F-AE-16) but do not restate it.
- Agent teams in Claude Code: in-window blog coverage is the launch note (AE-32), the selection rule (AE-10, AE-12) and the cost (AE-28). There is no in-window blog post on how to run a team well.
- Emphasis (capitals, "IMPORTANT"): no in-window source discusses it directly; the nearest is the advice to delete repetition and "think hard" lines (F-AE-09).
- Handling ambiguity without asking: Anthropic's published position leans the other way, toward training Claude to pause (F-AE-42). The "choose, log, continue" default rests on one engineer's example prompt and the Opus 5.5 guide (F-AE-43).

# Background, outside the 12-month window

These are older than 2025-11-17 and are not used as evidence above.

- BG-01, Building effective agents, 2024-12-19. Start simple: "we recommend finding the simplest solution possible, and only increasing complexity when needed". On evaluator–optimizer loops: "This workflow is particularly effective when we have clear evaluation criteria, and when iterative refinement provides measurable value." Still cited by name in AE-01.
- BG-02, How we built our multi-agent research system, 2025-06-13. The briefing list: "Each subagent needs an objective, an output format, guidance on the tools and sources to use, and clear task boundaries." What thin briefs cause: "Without detailed task descriptions, agents duplicate work, leave gaps, or fail to find necessary information." Cost: "multi-agent systems use about 15× more tokens than chats". Fit: "some domains that require all agents to share the same context or involve many dependencies between agents are not a good fit for multi-agent systems today". Handoff by reference: "Subagents call tools to store their work in external systems, then pass lightweight references back to the coordinator."
- BG-03, Effective context engineering for AI agents, 2025-09-29. Level of detail: "The right altitude is the Goldilocks zone between two common failure modes." Size: "you should be striving for the minimal set of information that fully outlines your expected behavior". Subagent returns: "returns only a condensed, distilled summary of its work (often 1,000-2,000 tokens)".
- BG-04, Best practices for prompt engineering, 2025-11-10. On roles: "modern models are sophisticated enough that heavy-handed role prompting is often unnecessary"; "Often, being explicit about what perspective you want is more effective"; "Overly specific roles can limit the AI's helpfulness." It lists as a case where a role may help: "You want domain expertise framing for complex topics".

# Could not verify

- Example prompts and code samples on several claude.com pages (AE-12, AE-13, AE-30's figures B to D, AE-39 in part) are shown as images or embeds and are absent from the page text. Whether any of them opens with a role line could not be checked. Nothing above relies on them.
- Three in-window engineering posts were not read, because their titles and index summaries place them outside the topics: "Eval awareness in Claude Opus 4.6's BrowseComp performance" (2026-03-06), "Quantifying infrastructure noise in agentic coding evals" (2026-02-05), "Designing AI-resistant technical evaluations" (2026-01-21).
- Four in-window engineering posts were downloaded and searched but yielded nothing used: "Building strong safety evaluations" (2026-11-13), "Redesigning source control at Anthropic" (2026-10-13), "How we contain Claude across products" (2026-05-25), "Introducing advanced tool use on the Claude Developer Platform" (2025-11-24).
- The claude.com article index reports 320 resources. Posts were chosen from the site map by title; around 30 were downloaded. A relevant post with an uninformative title could have been missed.
- AE-28 attributes the "about seven times" figure for agent teams to Anthropic's cost documentation. That documentation page is in another teammate's slice and was not opened here.
