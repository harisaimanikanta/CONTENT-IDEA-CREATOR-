# idea-creator

A Claude Code skill that **finds video ideas** for a *Historical WTF* YouTube Shorts channel: real historical events that sound completely made up (cons, hoaxes, absurd wars, impostors, bizarre trials, backfired plans, inventions nobody believed).

It only does ideas. It searches the web, pre-checks the evidence, checks how crowded each topic already is on YouTube Shorts, scores each story against the channel's viral format, and outputs **IDEA CARDS**. To turn a card into a script, give it to the companion skill **[script-writer](https://github.com/harisaimanikanta/VIRAL-SCRIPT-WRITER)**.

## Install

**Option 1: plugin (recommended).** In Claude Code:
```
/plugin marketplace add harisaimanikanta/CONTENT-IDEA-CREATOR-
/plugin install idea-creator@idea-creator
```
Then run `/idea-creator:idea-creator`, or just ask "give me 10 video ideas".

**Option 2: clone the repo.** Open Claude Code inside a clone of this repo. The skill is picked up automatically from `.claude/skills/idea-creator` (a symlink to `skills/idea-creator`).

**Option 3: copy it.** Copy `skills/idea-creator/` to `~/.claude/skills/idea-creator/` to have it in every project.

**Option 4: just paste the link.** Tell Claude "install the skill from https://github.com/harisaimanikanta/CONTENT-IDEA-CREATOR-". It can clone the repo and copy `skills/idea-creator` into `.claude/skills/`.

## Use
- `/idea-creator:idea-creator` gives 10 mixed ideas.
- `/idea-creator:idea-creator 5 backfired plans` gives 5 ideas in that category.
- Each idea comes back as an IDEA CARD (title, cold-open line, true story, doubt beat, reversal, mechanism, fit score, competition, sources, warnings).

## Setup (optional)
The competition check uses `yt-dlp` and needs YouTube network access: `bash skills/idea-creator/scripts/setup.sh` (Claude asks before running it). Without it, the skill estimates competition with web search.

## What's inside
| Path | What |
|---|---|
| `skills/idea-creator/SKILL.md` | The workflow |
| `references/niche.md` | The channel niche and what's wanted / not wanted |
| `references/style-target.md` | The viral format ideas must fit (from 5 reference Shorts, 6.8M–35.1M views) |
| `references/idea-engine.md` | 5-point fit test + IDEA CARD format |
| `references/search-playbook.md` | Search seeds, sources, evidence pre-check, saturation guide |
| `research/idea-bank.md` | Every idea pitched so far (no repeats) + rejected list |
| `research/competition-snapshot.md` | YouTube Shorts competition for 21 topics |
| `scripts/competition_check.py` | Shorts saturation checker (yt-dlp) |
