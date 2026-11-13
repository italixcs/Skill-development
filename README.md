# Skill Development

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Status: experimental](https://img.shields.io/badge/status-experimental-orange.svg)](docs/release-readiness.md)

Reusable development rules for AI agent skills: research, scope, authoring, evaluation, security review, and release preparation.

Set the process once, then ask your agent to apply it to the next skill. Skill Development coordinates existing tools and keeps the steps proportional to the task. Its intended benefit is less repeated instruction and supervision; time savings have not been measured.

[Installation](docs/installation.md) · [Validation](docs/validation.md) · [Security](docs/security.md) · [Release checklist](docs/release-readiness.md)

## Try it

Clone or download this repository, inspect the complete [skill-development/](skill-development/) folder, then ask an agent with local file access:

```text
Read skill-development/SKILL.md and follow its relevant references.
Help me develop a private skill for reviewing release notes.
Research existing options, agree on the scope, and keep changes local.
```

For an existing skill:

```text
Use Skill Development to prepare this skill for public release.
Check the package, choose relevant evaluation, and use SkillSpector.
Prepare the documentation, report blockers, and do not publish.
```

These are usage examples, not transcripts of completed runs. See [host-specific installation and invocation](docs/installation.md) for Codex and Claude Code routes and their verification status.

> [!IMPORTANT]
> Tools and permissions come from your host. Missing independent agents or SkillSpector block their dependent checks; the workflow never invents a comparison or scan.

## What it coordinates

| Stage | Existing tool or capability | When used |
| --- | --- | --- |
| Research and scope | GitHub MCP, Context7, authoritative web/local sources | New ideas, unresolved facts, meaningful scope changes |
| Authoring and structure | Native skill creator and validator | Create or revise the package |
| Evaluation | Bundled, versioned Skill Bench workflow | Initial validation and meaningful behavior changes |
| Security | NVIDIA SkillSpector | Risk review and public release candidates |
| Presentation | Repo Cleaner | Installation, examples, evidence, or repository presentation needs |
| Publication | Existing Git/GitHub and release tools | Only with explicit authorization |

Research and authoring can use equivalent available capabilities. Skill Bench needs independent workers and a reviewer. SkillSpector must be installed separately. Repo Cleaner is optional; essential factual docs can be prepared without it. No external paid inference is initiated without agreement.

## What changes between tasks

A private skill keeps essential correctness and execution-risk checks. A public release adds distribution, licensing, security evidence, compatibility, and documentation checks.

A spelling fix receives affected checks. A meaningful behavior change receives representative evaluation. The workflow starts at the current stage and reuses decisions and authorization already given.

## A real pilot

In a local Repo Cleaner revision, the skill-assisted worker added guidance for matching public scan claims to the current artifact and scan configuration. It also qualified outdated scan claims as historical. All six existing repository integrity tests passed.

The worker using native authoring guidance alone produced a comparably useful revision. Across three blind-reviewed cases, results were **two ties and one narrow baseline preference**.

That pilot did not measure reduced prompting or supervision across projects. It does not establish output-quality or efficiency gains. See the [method, results, and limitations](docs/validation.md).

> [!NOTE]
> SkillSpector 2.12.0 inspected all 10 package files in static mode on 2026-11-13. One LOW pattern match was retained and triaged as a false positive. See the [scope, hashes, and rationale](docs/security.md). This is not certification or proof of safety.

## Compatibility and limits

- The package follows the Agent Skills folder format. Host installation and invocation still vary.
- Codex and Claude Code copy routes are documentation-checked and locally copy-tested. Native discovery and full workflow execution in those clients remain unverified.
- Explicit instruction reading was exercised in the pilot. Shared files/global capabilities meant best-effort isolation.
- ChatGPT Work distribution is manual/installer-dependent; this repository is not a registered plugin or marketplace listing.
- Static scans do not evaluate runtime containment or every possible attack.
- Raw task inputs, worker artifacts, controller mappings, and unsanitized reports stay outside the repository.

## Package and provenance

[SKILL.md](skill-development/SKILL.md) routes to conditional references. The package contains no executable scripts and does not install tools automatically. The [design decisions](docs/decisions.md) explain its scope.

[MIT license](LICENSE). Skill Bench instructions and contracts are reused from [Italixcs/Skill-Bench](https://github.com/italixcs/Skill-Bench) at commit `2d3b596b3c7d28b92d840e898a0c84e60b2f5577`, with the author's authorization. External tools retain their own licenses.
