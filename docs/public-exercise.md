# Run the public-skill exercise

This is the next live check: use Skill Development to build a small skill intended for public distribution, run its evaluation and security steps, and prepare its repository presentation. **Everything stays local.** The exercise does not require making this repository public, creating another GitHub repository, or buying an API subscription. It uses your existing Codex account allowance; parallel agents consume that allowance.

Use a disposable folder, not a project containing real credentials or school/personal files. The resulting skill reviews supplied release-note text for clarity, actionable migration information, and unsupported claims. It should not run commands, browse, or publish anything when used.

## 1. Choose the environment

Recommended on Windows: **WSL2 Ubuntu + Codex CLI**. It provides one Linux environment for the agent, Git, and SkillSpector. On macOS or Linux, use a terminal and skip the WSL step. ChatGPT's connected apps and installed skills do not automatically carry over to a local CLI.

On Windows, open PowerShell as administrator:

```powershell
wsl --install
```

Restart if prompted, open Ubuntu, and finish its account setup. Keep the exercise under the Linux home directory rather than `/mnt/c`.

In Ubuntu:

```bash
sudo apt-get update
sudo apt-get install -y git curl gh
```

On macOS/Linux, ensure Git, curl, and the [GitHub CLI](https://cli.github.com/) are available using your normal package manager.

## 2. Install and sign in

The following are upstream installer commands. Inspect the linked projects and installers before running them. Run in your Linux/macOS terminal:

```bash
curl -fsSL https://chatgpt.com/codex/install.sh | sh
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Reopen the terminal so the installers' PATH changes apply. Then:

```bash
uv tool install --python 3.12 git+https://github.com/NVIDIA/skillspector.git
gh auth login --web
gh auth setup-git
codex --version
skillspector --version
git --version
```

Choose your GitHub account with access to the two source repositories. The scanner command installs the current upstream source, not a version pinned by this guide; record the actual installed version. Static `--no-llm` scanning needs no LLM provider key. It may contact OSV for dependency coordinates.

Run `codex` once and choose **Sign in with ChatGPT**, then exit that initial session. Use the normal permission prompts; the exercise needs local file editing and deliberate tool installation, not unrestricted permissions. Enter credentials only in the provider's own sign-in flow.

## 3. Create the local lab

These commands require a new folder; `mkdir` deliberately refuses an existing lab. Use a different name if you have already run it.

```bash
mkdir ~/skill-development-lab
cd ~/skill-development-lab
mkdir -p reference .agents/skills candidate private-run
gh repo clone italixcs/Skill-development reference/Skill-development
gh repo clone italixcs/Repo-cleaner reference/Repo-cleaner
test -f reference/Skill-development/skill-development/SKILL.md
test -f reference/Repo-cleaner/skills/repo-cleaner/SKILL.md
cp -R reference/Skill-development/skill-development .agents/skills/skill-development
cp -R reference/Repo-cleaner/skills/repo-cleaner .agents/skills/repo-cleaner
printf 'reference/\nprivate-run/\n.agents/\n' > .gitignore
git -C reference/Skill-development rev-parse HEAD > private-run/skill-development-source.txt
git -C reference/Repo-cleaner rev-parse HEAD > private-run/repo-cleaner-source.txt
```

Copy the complete folders, including references. If a source path check fails, stop and inspect the repository layout before copying. `reference/` holds read-only source snapshots, `.agents/skills/` contains the two local workflow skills, `candidate/` is the output project, and `private-run/` holds raw evaluation/scan records. There is no Git remote for the lab.

Start a **fresh** Codex session inside the lab:

```bash
codex -c agents.enabled=true -c agents.max_concurrent_threads_per_session=4
```

Configuration names can change between client versions. If the CLI rejects them, consult its current subagent documentation and use supported settings. Do not substitute a single agent impersonating three participants.

## 4. Run this preflight first

Paste this into the fresh session:

```text
Preflight this local Skill Development exercise; do not build the candidate yet.
Confirm that .agents/skills/skill-development and .agents/skills/repo-cleaner
are discoverable and contain their references. Report the Codex and SkillSpector
versions, current source commit IDs, available native skill-authoring guidance,
and whether you can launch two fresh workers and a fresh blind reviewer.
Check that candidate/ and private-run/ are writable. Do not print credential
values or dump environment variables. Identify missing capabilities precisely.
Keep all work local, with no commit, push, visibility change, or release.
```

Resolve missing capabilities before the full exercise. If skills are only usable through explicit file reads, that can still test the workflow, but record that native discovery was not demonstrated. If independent agents or the scanner are unavailable, the corresponding checks remain blocked. GitHub MCP and Context7 are optional here; use them only for an actual unresolved repository or library question. Local source inspection and authoritative documentation are sufficient for this small task.

## 5. Run the exercise

After preflight passes, paste:

```text
Use Skill Development to create a small public-intended skill named
release-note-review in candidate/skills/release-note-review/. Use the native
skill-authoring guidance available in this client. The skill reviews text I
supply: improve clarity, identify missing actionable migration information,
and flag claims the supplied evidence does not support. Preserve facts and
voice; ask only when missing information blocks a useful review. The resulting
skill needs no network, scripts, external services, or runtime dependencies.

Agree on a concise scope from this brief and research only unresolved points.
Create the complete minimal package and relevant validator checks. Then use
the bundled Skill Bench protocol: predeclare three small synthetic cases
(normal review, missing evidence, and an adjacent out-of-scope request), one
attempt per condition, two fresh workers with equivalent tools/settings,
and a fresh reviewer blind to anonymized conditions. Give the candidate only
to its assigned arm; store controller mappings and raw records in private-run/.
Report whether separation is actually enforced or only instruction based.
Do not retry to obtain a favorable verdict, invent runs, or treat a tie as failure.

Run the installed NVIDIA SkillSpector against the complete candidate skill
with --no-llm --fail-on-incomplete, keeping raw output in private-run/.
Review findings and bind a sanitized summary to the exact scanned file set
and hashes. Do not call the skill secure because a scan passed. If package
bytes change afterward, refresh affected checks and scan evidence.

Use Repo Cleaner to prepare candidate/README.md with meaningful installation,
a real synthetic before/after review example, limits, licensing, and version
notes. Keep documentation proportional; no banner or decorative badges are
needed for this test candidate. Preserve license attribution and use this
exercise's MIT licensing choice for original generated material.

Finish candidate/HANDOFF.md with actual results, tool/source versions, output
paths, unresolved limitations, and the next action. Include a short workflow
coverage table: done, blocked, or not applicable, with evidence. Keep raw logs,
A/B mappings, account details, and credentials out of candidate/. No global
installation, commit, push, publication, visibility change, or release.
```

The three cases are a bounded diagnostic, not a statistically meaningful benchmark. A comparison can reveal a weakness or a tie. That is useful evidence, not a reason to rerun until the skill wins.

## 6. Inspect the handoff

Expected output (additional files need a reason):

```text
candidate/
  README.md
  LICENSE
  HANDOFF.md
  skills/release-note-review/
    SKILL.md
    LICENSE
    references/             # only if the instructions need it
  docs/                     # only for evidence/details too long for README
private-run/                # raw records, outside the distributable project
```

Confirm the skill actually performs a review; documentation about a planned skill is insufficient. The handoff should show completed authoring checks, actual worker/reviewer results, an actual complete static scan or a clear blocker, and usable installation/docs. Claims must match the final package bytes. Public documentation should not expose local account details, credentials, or raw task records.

Send me **the sanitized HANDOFF.md, candidate README, and any unresolved findings or errors**. Include the actual versions and source commit IDs. Do not send authentication files, environment dumps, or raw logs. I can then review what worked, what needed extra reminders, and which instructions deserve revision. Human prompt-writing time would need a separately timed session; this exercise alone does not measure it.

## Verification status and sources

These commands were checked against upstream documentation and the Bash blocks were syntax-checked. They have **not** been run on your computer. Native discovery and the complete exercise remain to be observed.

- [Codex on WSL](https://learn.chatgpt.com/docs/windows/wsl)
- [Codex CLI installation and sign-in](https://learn.chatgpt.com/docs/codex/cli)
- [Local skills](https://learn.chatgpt.com/docs/build-skills)
- [Native subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents)
- [uv installation](https://docs.astral.sh/uv/getting-started/installation/)
- [GitHub CLI authentication](https://cli.github.com/manual/gh_auth_login)
- [NVIDIA SkillSpector installation and scan options](https://github.com/NVIDIA/SkillSpector)
