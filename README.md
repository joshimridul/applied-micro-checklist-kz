# Applied microeconomics writing

**Version 1.2.0**

An Agent Skill for Codex and Claude Code that drafts, revises, copyedits, and audits applied-microeconomics papers under Ekaterina Zhuravskaya's *Rules for Good Academic Writing in Applied Economics: A Checklist of Dos and Don’ts*.

## Install and use

### Install without Git

1. [Download `applied-micro-writing.zip`](https://github.com/joshimridul/applied-micro-checklist-kz/releases/latest/download/applied-micro-writing.zip).
2. Open the downloaded ZIP. It contains an `applied-micro-writing` folder.
3. Move that folder to the appropriate location:
   - Codex, all projects: `~/.agents/skills/`
   - Codex, one project: `.agents/skills/` inside the project
   - Claude Code, all projects: `~/.claude/skills/`
   - Claude Code, one project: `.claude/skills/` inside the project
4. Codex detects the skill automatically; restart it if the skill does not appear. In Claude Code, run `/reload-skills` if needed.

On macOS, press Shift–Command–G in Finder and enter the destination path. If the path does not exist, create it first. To update a manual installation, download the ZIP again and replace the installed `applied-micro-writing` folder.

### Install with Git

#### Codex

Install directly from GitHub for the current user:

```sh
mkdir -p ~/.agents/skills
git clone https://github.com/joshimridul/applied-micro-checklist-kz.git ~/.agents/skills/applied-micro-writing
```

Invoke it as `$applied-micro-writing`; Codex may also select it automatically when the request matches its description. Codex detects newly installed skills automatically; restart it if the skill does not appear.

#### Claude Code

Install directly from GitHub for the current user:

```sh
mkdir -p ~/.claude/skills
git clone https://github.com/joshimridul/applied-micro-checklist-kz.git ~/.claude/skills/applied-micro-writing
```

For a project-specific installation, use `.claude/skills/applied-micro-writing/` as the clone destination instead. Invoke it as `/applied-micro-writing`; Claude Code may also select it automatically when the request matches its description. If a newly created skills directory does not appear in the current session, run `/reload-skills`.

#### Update a Git installation

Pull the latest version from GitHub using the path where the skill is installed:

```sh
# Codex
git -C ~/.agents/skills/applied-micro-writing pull --ff-only

# Claude Code
git -C ~/.claude/skills/applied-micro-writing pull --ff-only
```

The repository is named `applied-micro-checklist-kz`; the runtime skill name remains `applied-micro-writing` in both tools.

The examples below use Codex syntax. In Claude Code, start the request with `/applied-micro-writing`, followed by the task.

Example revision request:

> Use `$applied-micro-writing` to revise this introduction under Zhuravskaya's checklist. Preserve the research meaning, estimates, uncertainty, citations, and LaTeX commands. Return clean prose only.

Example audit request:

> Use `$applied-micro-writing` to audit this manuscript under all twelve sections of Zhuravskaya's checklist. Include the exhibits, notes, bibliography, and appendix. Identify what you inspected and what could not be checked. Do not add methodological recommendations.


## Contents

| File | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Runtime instructions and scope |
| [Source checklist](references/memo-checklist.md) | Source-faithful checklist with navigation IDs |
| [Original memo](references/original-memo.pdf) | Eight-page source supplied with the package |
| [Audit template](templates/review.md) | Optional reporting structure for requested audits |
| [Source metadata](source.json) | Attribution, checksum, and package metadata |
| [Codex metadata](agents/openai.yaml) | Optional Codex UI metadata; Claude Code does not require it |

## Attribution

The source memo is by Ekaterina Zhuravskaya of the Paris School of Economics. The checklist and runtime packaging are an adaptation for agent use; they are not represented as authored or endorsed by Zhuravskaya.
