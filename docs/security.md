# Security scan evidence

This records the refreshed static scan of the completed v0.1.0 package. It is not certification or a guarantee of safety. The [initial pilot scan](security/skillspector-2026-11-13.json) is retained as historical evidence.

| Item | Recorded value |
| --- | --- |
| Date | 2026-11-13 |
| Scanner | NVIDIA SkillSpector 2.12.0 |
| Mode | Static, LLM disabled |
| Scope | Complete installable skill-development/ directory |
| Configured inspection | 10/10 files; complete |
| Scope exclusions / suppressions | None / none |
| Findings | One LOW EA3; no reported critical/high findings |
| Triage | Author/controller review: false positive; finding retained |

The [sanitized record and full file-hash manifest](security/skillspector-v0.1.0.json) bind this evidence to package identity:

`5f1688f290486e691745f5d25b7258d13327db6217e01078f8477f132d9e4395`

The identity is SHA256 of a JSON-serialized mapping from sorted package-relative paths to their SHA256 file digests, using Python json.dumps(sort_keys=True) defaults. It describes package content, not a repository commit or signature.

## Retained finding

EA3 matched "expand scope" at SKILL.md line 52. The sentence says:

> Do not let a helper silently expand scope, permissions, evaluation budget, or publication actions.

It forbids the behavior the pattern flags. The author/controller recorded a false-positive decision; this was not an independent security audit. The instruction remains unchanged and the finding was not suppressed.

## Reproduction

With the same scanner version available, run from the repository root, using a private report directory outside this package:

```sh
skillspector scan ./skill-development --no-llm --fail-on-incomplete --format json --output /path/to/private-run/security.json
```

Replace the output placeholder first. Inspect the report as well as the exit code. The original scan used these options and an absolute local input path; machine-specific paths are omitted here.

## Limits and freshness

- No semantic analysis, runtime execution, or containment test ran.
- Dependency artifact inspection was not requested; this package has no executable scripts or dependency manifest.
- Static mode may contact OSV for dependency coordinates. No LLM inference was requested.
- The sanitized JSON is a selected projection of the actual raw output. It preserves the finding, scope, mode, completion, hashes, and triage; private raw evidence stays outside this repository.
- A file change inside the package requires checking which evidence is invalidated. Compare the complete file set and hashes, including additions/removals, before reusing this claim.
- Changes to README or other docs outside the scanned package do not alter its content identity.

For a suspected security issue, avoid posting sensitive reproductions or credentials publicly. Report privately to the maintainer through an available private channel.
