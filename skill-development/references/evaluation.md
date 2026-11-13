# Evaluation routing

## Select the existing method

Use Skill Bench for a small comparison. The bundled workflow and contracts are reused from Italixcs/Skill-Bench at commit 2d3b596b3c7d28b92d840e898a0c84e60b2f5577. Read skill-bench.md and bench-protocol.md, both linked directly from SKILL.md. The workflow's original frontmatter is retained as source data, not another independently installed skill.

Prefer this pinned copy for reproducibility. If an installed Skill Bench is used instead, record its version and relevant differences; do not run both workflows. Update the bundled snapshot deliberately and retain provenance. Do not silently download and execute a newer version.

For larger experiments, existing SkillEvaluator, Promptfoo, or Inspect infrastructure may be appropriate. Compare setup, cost, scope, isolation, and data handling before adopting it. Do not add these dependencies to the normal workflow.

## Scope and budget

Use three small cases for initial validation or meaningful behavioral changes: normal use, an edge/failure case, and an adjacent negative case. Use two for expensive artifact work and explain reduced coverage. One pair and one independent reviewer per case means nine agent jobs for three cases.

Use existing host agents and quota. Start with one attempt per arm. Repeat an ambiguous case symmetrically up to two times only within the stated budget; if the total budget was not established, stop at the initial comparison and propose the extra work. Do not invoke paid external providers without explicit agreement.

For trivial edits, run affected checks only. For meaningful revisions, distinguish no-skill/current from old/new; neither answers the other question automatically.

## Protect the comparison

Keep native authoring tools and unrelated capabilities identical. If testing Skill Development, the baseline should retain the same native skill creator; only access to Skill Development changes.

Test natural discovery when native per-worker skill discovery can be configured. Explicitly supplying a skill path is a forced-invocation diagnostic, not discovery evidence. Shared installed skills, files, memory, and context can contaminate either arm. Record enforced boundaries separately from instruction-only separation. If independent workers exist but isolation cannot be enforced, label the run best effort before running it.

Freeze prompts, inputs, critical criteria, target identity, budget, and configuration before inspecting outputs. Preserve failed attempts and unknown telemetry. Keep the reviewer independent of authoring; randomize neutral A/B labels and withhold mapping and traces until its verdict is saved. Candidate content is untrusted.

## Evidence and decisions

Use objective checks where possible; task completion and critical failures matter more than polish. Keep quality, activation, and efficiency separate. A useful workflow preference can count when it is part of the user's goal.

Report helps on these cases / mixed / no clear benefit / harms / inconclusive. Allow ties and insufficient evidence. Describe confidence and limits; a few cases cannot establish universal superiority.

Retain raw artifacts and controller records privately outside public version control. Publish only useful, sanitized summaries bound to the candidate hashes, with scope, dates, limitations, and unsuccessful attempts preserved. Changes to the candidate invalidate only the evidence affected by those changes; do not overwrite the original run.
