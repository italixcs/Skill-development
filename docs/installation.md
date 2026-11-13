# Installation and first use

Install the entire `skill-development/` directory, including references, optional display metadata, and license. Installing only SKILL.md leaves required procedures behind.

This repository does not install GitHub MCP, Context7, Repo Cleaner, SkillSpector, or an agent runtime. Configure the capabilities you need in your host.

## Get the source

```sh
git clone https://github.com/italixcs/Skill-development.git
cd Skill-development
```

While the repository is private, this requires authorized GitHub access. Downloading a repository archive is an alternative. Inspect the instructions before installing.

## Codex CLI — personal local skill

From the repository root, using a POSIX shell:

```sh
skill_install_root="$HOME/.agents/skills"
test ! -e "$skill_install_root/skill-development" &&
test ! -L "$skill_install_root/skill-development" &&
mkdir -p "$skill_install_root" &&
cp -R ./skill-development "$skill_install_root/skill-development"
```

The command stops when that destination already exists; it does not replace an existing installation. For an update, compare the folders and use the host's installer or replace only after reviewing your local changes.

Invoke the installed skill in Codex:

```text
$skill-development help me improve this skill; keep changes local.
```

For a repository-scoped skill, the corresponding location is `.agents/skills/skill-development/` inside the target repository. Do not install the same skill into multiple scopes accidentally.

Status: discovery location and invocation checked against [OpenAI's current skills documentation](https://learn.chatgpt.com/docs/build-skills) on 2026-11-13. Copy behavior was tested locally, including preservation of all package bytes and refusal to overwrite. Native Codex discovery and full execution were not tested. This is local skill-folder distribution, not a registered plugin.

## Claude Code — personal local skill

From the repository root, using a POSIX shell:

```sh
skill_install_root="$HOME/.claude/skills"
test ! -e "$skill_install_root/skill-development" &&
test ! -L "$skill_install_root/skill-development" &&
mkdir -p "$skill_install_root" &&
cp -R ./skill-development "$skill_install_root/skill-development"
```

Invoke it in local Claude Code:

```text
/skill-development help me improve this skill; keep changes local.
```

For repository-scoped use, the corresponding location is `.claude/skills/skill-development/`. Account-synced, Cowork, and cloud sessions have different loading rules; a local personal copy does not establish support for those sessions.

Status: path and invocation checked against [Claude Code documentation](https://code.claude.com/docs/en/skills) on 2026-11-13. Copy behavior was tested locally as above. Native discovery and full workflow execution were not tested.

## Windows

Use your host's supported installer, or copy the complete folder into its documented skill location using File Explorer. The two shell examples above require a POSIX shell; they are not PowerShell commands. Do not copy an existing folder over another installation without reviewing local changes.

## ChatGPT Work and manual reading

Use the host's skill installer when it supports the complete package. A plain GitHub folder is not automatically an installed ChatGPT skill or registered plugin.

With an agent that can read the cloned files, explicitly ask it to read `skill-development/SKILL.md` and the relevant references. That manual route was exercised in the local pilot; it does not test automatic discovery or every host.

## First useful result

Ask for a private skill with a concrete recurring task, or point at an existing skill to improve. Provide its intended users and important constraints. The agent should reuse settled context, select available tools, produce the authorized changes, and report actual checks and blockers.

If evaluation requires independent agents that the host cannot provide, the result should identify the blocked comparison. If SkillSpector is missing, public-release security readiness remains incomplete.

See [validation](validation.md) for the exact evidence and limitations.

For a full local setup and a small public-intended development task, follow the [public-skill exercise](public-exercise.md). It installs the workflow skills in a disposable lab and keeps the candidate local.
