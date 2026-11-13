# Validation record

Date: 2026-11-13. Status: completed experimental v0.1.0. The initial pilot did not demonstrate output-quality uplift; reduced prompting and supervision were not measured. Its workers did not commit, push, install, release, or change remote settings.

## Completed v0.1.0

Current package identity: `5f1688f290486e691745f5d25b7258d13327db6217e01078f8477f132d9e4395`. The entry point is 82 lines. All 10 distributed files are recorded in the [refreshed scan manifest](security/skillspector-v0.1.0.json).

The final instruction refinement makes workflow fidelity explicit, keeps supplied-evidence reviews narrow, and separates implementation completion from public-release decisions. Three fresh, explicitly instructed task workers exercised the affected behavior:

| Focused task | Observed artifact | Verification |
| --- | --- | --- |
| Finish a private skill from an approved brief | Usable release-note-review folder and a completion note; missing public-only tools did not prevent completion | Controller inspected structure/scope; separate artifact reviewer passed it, with execution-claim limits |
| Assess a supplied static-report claim | Short scoped answer, preserving synthetic-report and execution limits | Separate artifact reviewer passed it |
| Correct one spelling error | Exact expected README content, with no extra project files | Controller exact-content/file-set assertions passed; separate reviewer confirmed final spelling but lacked retained before-state evidence for an independent delta judgment |

These are bounded behavioral smoke checks, not a new paired comparison, automatic-discovery test, or proof of time savings. Filesystem separation was instruction-only. Artifact review does not establish every internal tool decision or absence of all external actions.

The final package passed the existing structural validator, resource/link checks, and copy-install checks. SkillSpector 2.12.0 completed a refreshed static scan of all 10 package files; the same LOW EA3 prohibition match remains at SKILL.md line 52, triaged without suppression. See [security evidence](security.md).

## Initial pilot candidate

Package identity: `25cbda2a7683318cd206a8851a7e92a7ad3f226ecb841c7716140cf5e2d58845`.

This is SHA256 of a JSON-serialized sorted mapping from package-relative paths to file SHA256 digests, using Python json.dumps(sort_keys=True) defaults. The private run retains the full manifest.

The package has 10 files: a 77-line entry point, seven conditional references, optional Codex display metadata, and MIT license. No executable scripts or dependency manifest.

## Checks

- Existing skill-creator quick validator: passed against the authored directory.
- Relative links: 13 checked initially; zero broken. Final documentation links checked separately.
- Frozen package identity: unchanged after the pilot.
- These establish structural properties, not native discovery or cross-host runtime behavior.

## Initial SkillSpector scan

NVIDIA SkillSpector 2.12.0 completed a static-only scan with --no-llm and --fail-on-incomplete. It reported all 10 files fully inspected in the configured scope, without exclusions or suppressions. No semantic inference ran.

One LOW EA3 match remains: "expand scope" in SKILL.md line 49. The sentence explicitly prohibits helpers from silently expanding scope, permissions, evaluation budget, or publication actions. The author/controller triaged it as a false positive; the instruction and finding remain intact, with no suppression.

No critical/high findings were reported. This is not proof of safety, runtime containment, semantic coverage, or vendor endorsement. Triage was not an independent security audit. Dependency artifact inspection was not requested; the package has no executable scripts or dependency manifest.

## Paired pilot

The primary product goal is a reusable development process: appropriate tool selection, proportional checks, fewer repeated instructions, and respected authorization. Output quality remains a correctness guardrail. The pilot below primarily compared resulting artifacts and is insufficient to assess that primary workflow benefit. Its original verdicts are preserved.

The same native authoring guidance and frozen inputs were used with and without explicit Skill Development access. Each case had one worker per condition and a fresh independent reviewer. Rubrics and random A/B mappings were saved before execution; verdicts were saved before revealing the mapping.

| Case | Baseline | With Skill Development | Blind verdict |
| --- | --- | --- | --- |
| Real Repo Cleaner revision | Added artifact/file-hash currency guidance and historical scan labeling; 6 tests passed | Added artifact/configuration currency guidance and historical scan labeling; 6 tests passed | Tie |
| Release-evidence review | Rejected synthetic, stale, incomplete evidence; concise next steps | Rejected the same evidence; broader release-review detail | Narrow baseline preference |
| Single README spelling correction | Exact requested correction only | Exact requested correction only | Tie |

Frozen Repo Cleaner source tree: `d3da49ae1566f95d39ed76292b384150281df7bd`. All 49 seed blobs matched that upstream tree. The real revision addresses scan claims becoming stale after distributed skill content changes. Both proposed revisions preserve historical reports and avoid claiming a fresh scan. The same six-test repository suite was independently rerun for both candidates.

The release case was explicitly synthetic: mismatched subject hash, 70% coverage, excluded reference, and an unresolved HIGH test entry. That entry is not a vulnerability finding about the real source.

## Interpretation and limits

Original pilot verdict: **no clear output-quality benefit on these cases**. Both conditions met the main requirements. The small baseline preference concerned concision and careful distinction between synthetic entries and genuine findings, not a demonstrated general regression. This does not establish whether reusable instructions reduce user prompting or supervision.

- Workers and reviewers shared a filesystem and global capabilities. Separate directories and instructions were not enforced isolation.
- The target was explicitly supplied: best-effort forced-invocation diagnostics, not natural-discovery evidence. Unwanted automatic activation was not tested.
- Bounded offline workers could not delegate or contact external services. This did not test live orchestration of all integrations.
- Minor-edit outputs establish edit scope; absent execution traces prevent a comparative claim about verification effort.
- Both release workers received the same clarification allowing read-only shell access because no local text reader was exposed. This occurred before input review; substantive commands remained prohibited.
- Worker model/reasoning identifiers, per-worker timings, tokens, and costs were unavailable. No efficiency advantage is claimed.
- No fresh scan of the changed Repo Cleaner packages, native-host runtime test, or responsive/theme browser verification was established.
- One attempt per condition per case; no repeats or selected-best results.

## Next work

### Repository presentation pass

After the owner authorized a main-branch push, Repo Cleaner was applied to the public-facing documentation. The README now explains the reusable-process goal, requirements, examples, actual pilot, and limitations. Installation and public security evidence were added without changing the 10-file scanned skill package.

Both documented POSIX copy commands were exercised in temporary destinations: all package bytes matched, an existing destination was preserved, and a broken symlink was refused. A final path check covered 26 relative links with no missing targets. A targeted public-file check found no machine-specific workspace paths, temporary signed-URL patterns, or common credential-token patterns; this is not a dedicated secrets audit.

Markdown converted successfully to an HTML approximation. Chromium could not launch because its process-singleton socket was denied (Operation not permitted), so desktop/mobile and light/dark rendering were not verified. GitHub About/topics values are prepared, not applied: the connector has no repository-settings writer, the local CLI is unauthenticated, and the connected browser was unavailable.

Keep the candidate small. Before effectiveness claims, test a real tool-coordination task with required capabilities and stronger isolation. Any release-review refinement should target the observed extra detail and synthetic-finding wording, followed by affected checks.

See [release readiness](release-readiness.md) for remaining publication work and [installation](installation.md) for route-specific evidence. Raw inputs, diffs, verdicts, mapping, and unsanitized reports remain outside this repository. The public [security summary](security.md) and manifest retain the scoped scan evidence.
