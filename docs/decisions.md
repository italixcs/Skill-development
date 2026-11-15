# Design decisions

Agreed with the project owner on 2026-11-13.

- Coordinate existing tools; do not build a scanner, agent harness, evaluator service, or second complete authoring framework.
- Use one small entry point and references loaded only for the current stage. The initial main file was 77 lines; v0.1.0 is 82 lines. Line count is a design measure, not a quality score.
- Bundle a reviewed Skill Bench workflow so a separate installation is unnecessary. Keep the standalone skill available. Source: commit 2d3b596b3c7d28b92d840e898a0c84e60b2f5577. Copy its instructions and contracts; adjust its protocol link to the local reference. Record future updates deliberately.
- Preserve the existing project MIT license and attribution. The owner authorized bundling their Skill Bench material; external projects are referenced, not vendored.
- Prefer static SkillSpector scans with no semantic inference. Preserve findings and incomplete coverage; unresolved serious findings block public readiness.
- Use GitHub MCP/Context7 where useful, native authoring tools, and Repo Cleaner only for an actual presentation need.
- Missing capabilities block dependent stages while independent work continues. Explicit skill paths are diagnostic invocation, not automatic-discovery evidence.
- Compare initial and meaningful revisions on normal, edge/failure, and adjacent negative cases. Skip full comparisons for trivial edits. Repeats require a stated budget.
- Keep raw runs, source data, and A/B mappings private. Publish only selected sanitized evidence with candidate identity.
- Keep public/private routes distinct. Neither grants publication authority. The initial build stayed local; the owner subsequently authorized a commit/push to main and a Repo Cleaner pass. Visibility changes and a public release remain separate decisions.

## Product success criteria

The owner clarified that reusable development instructions and tool coordination are the intended product. Evaluate workflow fidelity, appropriate tool selection, unnecessary user reminders, scope, and respected boundaries. Better output quality is not the sole success criterion; maintain correctness and honest evidence as guardrails. Do not claim measured time savings without observing them.

## First pilot

Frozen source: Italixcs/Repo-cleaner tree d3da49ae1566f95d39ed76292b384150281df7bd.

Observed gap: existing security-callout guidance asks for tool/date/scope/mode but does not explicitly bind an old report to the current skill artifact. Pilot work will address stale security-scan presentation.

Compare the same public native authoring guidance and input snapshot with and without Skill Development. Use a real local revision, a release-evidence review, and a trivial edit. Preserve common tools and restrictions. Keep workers independent of authoring history and reviewers independent of worker conditions.

The host exposes a shared filesystem and globally available instructions; separation is instruction-only, not enforced isolation. Skill Development is supplied explicitly to its arm, making this a best-effort forced-invocation diagnostic. It does not establish natural discovery or cross-host runtime support.

## Upstream sources consulted

- Agent Skills specification: https://agentskills.io/specification
- OpenAI skill creator: https://github.com/openai/skills/tree/main/skills/.system/skill-creator
- Anthropic skill creator: https://github.com/anthropics/skills/tree/main/skills/skill-creator
- Superpowers writing-skills: https://github.com/obra/superpowers/tree/main/skills/writing-skills
- NVIDIA SkillSpector: https://github.com/NVIDIA/SkillSpector
- NVIDIA SkillEvaluator: https://github.com/NVIDIA/SkillEvaluator
- Promptfoo: https://github.com/promptfoo/promptfoo
- Inspect: https://inspect.aisi.org.uk/

Upstream procedures can conflict. Examples include owning evaluation inside an authoring helper, requiring a failing test before every edit, host-specific metadata, and automatic saving. Select one procedure per stage and retain the actual host/user instruction precedence.

## Completion boundary

The owner requested completion of the usable first version. Separate implementation completion from public visibility, release creation, and optional host-support expansion. Test bounded instruction refinements with focused behavioral checks when no comparative claim is made. Preserve the original paired pilot and its limitations.

## Prompt reuse and v0.1.1

Publish both actual task prompts and the comparable outcome as evidence of reusable instruction, without treating shorter user text as fewer total tokens or measured human savings. Preserve the original pilot and its less favorable verdict. Replace the experimental status badge with a version badge, not a stability claim.

The synthetic study exposed a handling gap: final-file cleanup does not undo a value already printed in tool output. Require value suppression before inspection and record this as a privacy refinement, with focused verification and a fresh package scan. Keep the original study bound to v0.1.0.

Use a disposable local release-note-review project for the next public-workflow exercise. Prepare licensing, evaluation, scanning, and presentation without making any repository public or publishing a release.

## Initial public-release preparation — 2026-11-15

The owner cannot currently run the desktop exercise and requested release preparation. Keep v0.1.1 package bytes unchanged and prepare an initial release with manual-invocation and documentation-checked installation claims. Defer the desktop exercise without presenting it as completed or promising native support. No visibility change, tag, or release is authorized by preparation alone.

Review existing reachable history and licensing provenance, preserve the matched static scan, and prepare release-page text and exact GitHub presentation values. The bundled Skill Bench instruction/protocol content matches the recorded source commit except for the local protocol link. Its source snapshot has no separate root/package license; rely on the owner's previously recorded redistribution authorization and this project's retained MIT license, without inventing an upstream license claim.
