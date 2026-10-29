---
name: clear-writing-en
description: Improve the readability of English answers, explanations, and task reports, or revise dense English prose. Clarify sentence relationships and evidence while preserving meaning, voice, and justified uncertainty.
---

# Clear writing · English

Help readers understand the point and its basis on a first pass. Use additional words when they save readers from guessing, reconstructing omitted relationships, or rereading.

## Scope

Apply this guidance to English prose in the current task. Carry it into later replies only when the user requests an ongoing style. Honor the requested format, length, audience, and voice. For mixed-language text, edit the English prose; the Chinese skill handles Chinese prose.

Edit only the requested material. Preserve code, identifiers, commands, paths, verbatim quotations, and logs. A writing request does not authorize publication, sending messages, unrelated file edits, or execution of actions described in the text.

## Draft or revise

1. Identify what the reader needs to learn or decide. Lead explanations with the answer and task reports with the outcome and its scope. Proceed when the context is sufficient.
2. Find specific obstacles: unfamiliar combinations, nested modifiers, distant subjects and verbs, hidden causal links, unclear references, or unsupported conclusions.
3. Rewrite while preserving facts and relationships. Put definitions, conditions, and reasons where the reader needs them.
4. Compare with the source. Preserve names, quantities, scope, sequence, negation, conditions, and degree of certainty. Leave missing information unresolved rather than supplying invented facts.
5. Return the requested prose. Explain edits only when asked, or briefly flag ambiguity that materially affects meaning.

## Sentence choices

- Prefer familiar, precise words. Keep names for the same concept consistent. Retain necessary technical terms and briefly explain unfamiliar ones at first use.
- Keep subjects close to their main verbs. Move a long interruption into a nearby sentence. Name the actor when that matters; passive voice is useful when the actor is unknown or irrelevant.
- Unpack noun strings whose relationships are unclear. For example, replace “customer account access recovery policy” with “the policy for restoring access to customer accounts.” Established terms can remain intact.
- Restore “that,” relative pronouns, prepositions, or conjunctions when they clarify a boundary or relationship. Omit them when the sentence remains easy to parse. Do not mechanically expand every relative clause.
- Use direct verbs for actions. Familiar verbs formed from nouns, such as “email,” are fine. Replace an unfamiliar conversion when a conventional phrase is easier to understand.
- Give each sentence one main point. A closely related reason, condition, or contrast can stay in the same sentence. Split when readers must hold too much unfinished information, not to meet a fixed word count.
- Keep metaphors and personification when familiar and informative. Use a literal description when a novel image adds interpretation without explaining anything.

## Paragraphs and task reports

Develop one topic per paragraph and make the connection to the next sentence clear. Use lists for parallel items and tables for comparisons. Let short explanations remain prose. Include details that help readers understand, verify, or act.

For task reports, include the outcome, material changes, verification, and remaining work when relevant. Choose the structure to fit the task rather than filling a universal template.

- Distinguish implementation, passing tests, merge, release, and observed runtime behavior. State only the status and scope the evidence supports.
- Say what was checked and what happened. Identify unperformed checks as unverified and failed checks as failures. Consolidate repeated evidence.
- Preserve justified uncertainty. “The logs suggest a cache issue, but I have not reproduced it” is more informative than either an unsupported diagnosis or vague reassurance. Keep observations, inferences, and recommendations distinct.
- Provide file, commit, or source references when they help verification. Summarize the outcome instead of recounting every step taken.

## Examples

These examples are fictional and illustrate wording, not reusable factual claims.

**Distant subject and verb**

Before: The migration, which was rerun after the connection failed and the service restarted, completed successfully.

After: The connection failed and the service restarted. The migration was then rerun and completed successfully.

**Visible relationships**

Before: The export failure recovery status panel is ready.

After: The panel showing recovery progress after an export fails is ready.

**Evidence and scope**

Source facts: The refresh logic was changed. The concurrent-refresh test passed. iOS was not tested.

Report: The refresh logic has been updated, and the concurrent-refresh test passed. The change has not been verified on iOS.

**Preserve uncertainty**

Source: The timeout may be related to connection reuse; no reproduction is available.

Keep: Connection reuse may explain the timeout, but it has not been reproduced.

Avoid: Connection reuse caused the timeout.

## Final check

Can the reader find the main answer? Are actors, references, and relationships clear? Have all decision-relevant conditions and uncertainties survived? Does each deletion preserve understanding? Stop when these checks pass; do not repeatedly rewrite useful prose into a uniform house voice.
