# Applied microeconomics writing

**Version 1.2.0 · source-faithful edition**

An Agent Skill for Codex and Claude Code that drafts, revises, copyedits, and audits applied-microeconomics papers under Ekaterina Zhuravskaya's *Rules for Good Academic Writing in Applied Economics: A Checklist of Dos and Don’ts*.

The memo is the skill's sole substantive writing authority. The skill does not import advice from other writing guides or turn a writing request into an econometric, identification, robustness, novelty, or research-validity review.

## Install and use

Keep the `applied-micro-writing` folder intact when installing it.

The commands below use HTTPS. If the repository is private, authenticate with GitHub before cloning it.

### Codex

Install directly from GitHub for the current user:

```sh
mkdir -p ~/.agents/skills
git clone https://github.com/joshimridul/applied-micro-checklist-kz.git ~/.agents/skills/applied-micro-writing
```

Invoke it as `$applied-micro-writing`; Codex may also select it automatically when the request matches its description. Codex detects newly installed skills automatically; restart it if the skill does not appear.

### Claude Code

Install directly from GitHub for the current user:

```sh
mkdir -p ~/.claude/skills
git clone https://github.com/joshimridul/applied-micro-checklist-kz.git ~/.claude/skills/applied-micro-writing
```

For a project-scoped installation, use `.claude/skills/applied-micro-writing/` as the clone destination instead. Invoke it as `/applied-micro-writing`; Claude Code may also select it automatically when the request matches its description. If a newly created skills directory does not appear in the current session, run `/reload-skills`.

### Update

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

> Use `$applied-micro-writing` to revise this introduction under Zhuravskaya's memo. Preserve the research meaning, estimates, uncertainty, citations, and LaTeX commands. Return clean prose only.

Example audit request:

> Use `$applied-micro-writing` to audit this manuscript under all twelve sections of Zhuravskaya's memo. Include the exhibits, notes, bibliography, and appendix. Identify what you inspected and what could not be checked. Do not add methodological recommendations.

## Scope

- The memo concerns writing form in applied microeconomics, not research content.
- A local drafting or editing request remains local; the skill does not append an unsolicited full audit.
- A whole-paper audit covers all twelve memo topics and distinguishes observed findings from checks that require missing or uninspected material.
- Explicit user instructions and supplied venue requirements are retained. Any departure from the memo is identified without rewriting the source rule.
- The memo's expressly personal preferences remain preferences, and its qualified thresholds retain their qualifications.

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

The source memo is by Ekaterina Zhuravskaya of the Paris School of Economics. The checklist and runtime packaging are an adaptation for agent use; they are not represented as authored or endorsed by Zhuravskaya. Rule IDs are navigational additions and do not appear in the memo.

The memo's references to a journal policy and a commercial service are preserved as source statements, not presented as current independent verification.
