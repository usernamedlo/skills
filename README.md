# skills

Agent skills by usernamedlo, for Claude Code and any agent supported by the [skills CLI](https://www.npmjs.com/package/skills).

## Install

One skill:

```bash
npx skills add usernamedlo/skills -g -s <skill-name>
```

All of them:

```bash
npx skills add usernamedlo/skills -g -s '*'
```

Drop `-g` to install into the current project instead of your user directory. List what the repository offers with `npx skills add usernamedlo/skills --list`.

Update installed skills with `npx skills update`.

## Skills

| Skill | Invocation | What it does |
| --- | --- | --- |
| [design-dlo](skills/design-dlo) | `/design-dlo <change>` | Applies a design, visual, UX or UI change request to the code, in the project's house style. |

Each skill's folder has its own README with its dependencies.

## Layout

```
skills/
  <skill-name>/
    SKILL.md      # entry point, with name and description in its frontmatter
    README.md     # human docs: usage and dependencies
    *.md          # reference files the skill points to
```

## License

[MIT](LICENSE)
