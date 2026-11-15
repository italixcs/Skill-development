# Public release readiness

**v0.1.1 is prepared for an initial public release with manual-invocation and documentation-checked installation limits.** Preparation reviewed on 2026-11-15. The desktop exercise is a follow-up validation task, not a prerequisite for this narrower release. Native client discovery, cross-host reliability, and a complete live public-skill workflow remain unverified.

The intended benefit is reusable development instructions and appropriate tool coordination. Better outputs, faster execution, measured human time savings, universal compatibility, and security certification are not release claims.

## Candidate and checks

Package source: [d14e97c](https://github.com/italixcs/Skill-development/tree/d14e97cce7b957922ee77beba6427ed4c2bba714/skill-development). Subsequent preparation changes affect repository documentation only. The full installable package is the 10-file `skill-development/` folder, including references, metadata, and license.

Package identity: `8d99d42133a1417a12236728988d97d5594b6806d1207bdcaf9a2d41a2976780`.

This identity and its definition are recorded with every file digest in the [v0.1.1 scan manifest](security/skillspector-v0.1.1.json). A final release must preserve that complete file set and those bytes, or refresh the affected evidence.

| Check | Status and evidence |
| --- | --- |
| Package structure and resources | Passed the existing structural validator; required references resolve |
| Installation copy behavior | Both documented personal-copy routes preserve all 10 files and refuse existing destinations, including broken symlinks |
| Native installation/discovery | Unverified; routes are documentation-checked and copy-tested, not runtime-certified |
| Task behavior | Focused checks and a one-pair prompt-substitution study recorded in [validation](validation.md); isolation and study limits retained |
| Security scan | Existing 2026-11-13 SkillSpector 2.12.0 static scan still matches the unchanged package; all 10 files inspected, no exclusions or suppressions |
| Security triage | One LOW EA3 match in an explicit prohibition, retained and triaged as a false positive; no reported critical/high findings; no semantic or containment test |
| Licensing and attribution | Root/package MIT licenses match; bundled Skill Bench source verified against its recorded commit, with only its protocol link adjusted |
| Public files and history | Reviewed the four commits reachable from main before this preparation: 43 distinct text blobs and one branding JPEG; no private run files tracked and no obvious credential/signed-URL/account-path patterns detected |
| Documentation and visuals | Purpose, installation, examples, both comparison prompts, scan limits, and release text prepared; banner/SVG received local image inspection; native GitHub responsive/light/dark rendering unverified |
| Live public-skill exercise | Deferred until the owner can use a desktop; [setup and prompts](public-exercise.md) are ready |
| Public visibility and release | Not performed; explicit authorization still required |

The history review is a bounded author/controller review, not a forensic audit or proof that no sensitive information exists. It covers reachable main history, not inaccessible or unreachable Git objects. The new preparation diff is reviewed separately before saving. Static scanning and local file checks do not certify safety or cross-host operation.

## Licensing and distribution

Original project material is MIT-licensed. Skill Bench instructions are reused from the owner's [source revision](https://github.com/italixcs/Skill-Bench/tree/2d3b596b3c7d28b92d840e898a0c84e60b2f5577), with redistribution authorization recorded in [decisions](decisions.md). That snapshot has no separate license file in its root or skill folder; do not describe it as independently verified upstream MIT licensing. The package includes this project's MIT license and preserves the source attribution.

NVIDIA SkillSpector, Repo Cleaner, native authoring tools, and research connectors are not bundled executable dependencies. They retain their own terms and must be available separately when needed. Skill Bench instructions are bundled; a separate Skill Bench installation is unnecessary.

Use GitHub's ordinary source archive for the release. Users install the complete `skill-development/` subfolder. No custom installer, executable, extra release archive, or paid inference service is required by the package. Account limits and externally configured tools still apply.

## Prepared publication handoff

- Version/tag: `v0.1.1`.
- Release title: **Skill Development v0.1.1 — reusable skill development workflow**.
- Release body: [prepared release notes](releases/v0.1.1.md), using absolute repository links so they also work on a GitHub release page.
- Target: the reviewed preparation commit reported in the handoff; do not create the tag against an unchecked moving branch head.
- Assets: normal GitHub source archives; no additional binaries or attachments.
- Compatibility statement: manually exercised instruction reading; Codex/Claude Code routes documentation-checked and copy-tested; native discovery and full client workflows unverified.

When publication is authorized, recheck the target commit and package identity, make the repository public only as authorized, then create the tag/release at that exact commit. Read back visibility, tag target, release text, and source package contents. No publication or visibility change is authorized merely by this checklist. Do not replace the version badge with “stable” or “secure” based on these checks.

## GitHub presentation values

These values are prepared, not applied. Current About text and topics were inspected; settings were left unchanged.

- About: `Reusable development rules for AI agent skills: scope, tool selection, evaluation, security review, and release preparation.`
- Suggested topics: `agent-skills`, `ai-agents`, `developer-tools`, `workflow`, `skill-development`, `evaluation`, `codex`, `claude-code`.
- Homepage: leave unset unless a real documentation site exists.
- Social preview: optional; the README banner exists, but no GitHub social-preview setting was applied.

[Repository settings](https://github.com/italixcs/Skill-development/settings)
