# design-dlo

Applies a design, visual, UX or UI change request to the code, in the project's house style.

```bash
npx skills add usernamedlo/skills -g -s design-dlo
```

## Usage

User-invoked only: type `/design-dlo` followed by the change you want.

- **Retouch** (the surface exists): it changes the code directly.
- **New surface** (the page, section or component does not exist yet): it gathers references, proposes a structure and waits for your answer before writing code.

The project's own design rules (`AGENTS.md`, `CLAUDE.md`, tokens, components) always win over the rules of the skills it loads.

## Dependencies

The skill loads other skills and MCP servers on demand. One that is missing is skipped and named in the final report, so the skill still runs without them.

Skills:

```bash
npx skills add jakubkrehel/skills -g      # pick better-ui, better-layout, better-typography, better-colors, better-writing, better-accessibility
npx skills add emilkowalski/skills -g -s animate
npx skills add nextlevelbuilder/ui-ux-pro-max-skill -g -s ui-ux-pro-max      # needs Python 3
npx skills add microsoft/playwright-cli -g -s playwright-cli
npx skills add mattpocock/skills -g -s prototype
```

MCP servers, used for new surfaces only: `mobbin`, `inspo`, `21st`, `aceternityui`, `reui`.
