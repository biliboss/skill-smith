> **Arquivado.** Este skill agora mora no plugin [biliboss/skills](https://github.com/biliboss/skills) (`skills/skill-smith/`). Instale com `claude plugin marketplace add biliboss/skills` e `claude plugin install biliboss-skills@biliboss`.

# skill-smith

An agent skill that **creates, updates and adapts other skills** (`SKILL.md`), so the next session does a task right on the first try. Its rules come from [Hermes Agent](https://github.com/NousResearch/hermes-agent), [skillify](https://github.com/Yeachan-Heo/oh-my-claudecode/blob/0564555b63dfedd158669c6799d53743abd7d6bf/skills/skillify/SKILL.md) (oh-my-claudecode) and [skillify-pro](https://github.com/coreyhaines31/makerskills/blob/ea7dd78515839ff11fc24e79ba0c53db2d5fff6c/skills/skillify/SKILL.md) (makerskills). The credits are in [ATTRIBUTION.md](ATTRIBUTION.md).

| Mode | What it does |
|---|---|
| **CREATE** | Turns a workflow from the session, some notes or a new idea into a skill, if it passes a three-question check on whether it is worth one |
| **UPDATE** | Applies one lesson to every skill it affects, with a diff per file, a version bump and a changelog entry |
| **ADAPT** | Ports someone else's skill, after a license check, sorting each part into keep / adapt / add, with credits |

Before creating a new skill, it always tries to patch an existing one, as [Hermes does](https://github.com/NousResearch/hermes-agent/blob/bf0203a794a07aac3ff764972ab9087baa4e4f4e/agent/background_review.py#L469-L497).

## Install

```bash
npx skills add biliboss/skill-smith -g --copy -a claude-code -y
```

This uses the [skills CLI](https://skills.sh). `-g` installs for your user (`~/.claude/skills/skill-smith/`), and `--copy` copies the files instead of linking them. Leave out `-a claude-code` to choose other agents. Then say "skill-smith", "make this a skill" or "update the X skill".

## What's inside

- [SKILL.md](SKILL.md): the procedure.
- [references/adapt.md](references/adapt.md): ADAPT mode in detail.
- [.wiki/](.wiki/README.md): skill-smith's own memory, with its design decisions and lessons from real runs.
- [CHANGELOG.md](CHANGELOG.md): the changes, in [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format, with [SemVer](https://semver.org/spec/v2.0.0.html) versions.

## License

[MIT](LICENSE). Upstream notices are in [ATTRIBUTION.md](ATTRIBUTION.md).
