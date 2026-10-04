# New surface

The new-surface branch of [design-dlo](SKILL.md), run after its step 3. It gathers references, then ends on a proposal the user answers.

## 1. Gather references

References answer what the house style leaves open.

| MCP server | When | For |
| --- | --- | --- |
| `mobbin` | Always | How shipped products solve this screen or flow |
| `inspo` | The project has no design system | Visual composition |
| `21st`, `aceternityui`, `reui` | The project lacks a component the surface needs | Component code, as a reference to rewrite in the house style |

Every query describes the pattern in generic terms, like `settings page with billing tabs`. These servers are third parties: client names, internal product names and code stay out of every query.

Done when you hold 2 or 3 references and can say in one line what you take from each (none, when every server is skipped or does not apply).

## 2. Propose, then stop

Write the proposal in ten lines or fewer:

- **Structure**: the surface's regions, in reading order.
- **References**: each one kept, and what you take from it.
- **Reuse**: the project components and tokens it is built from.
- **Prototype**: only when at least two directions stay plausible, because the references diverge or the house style does not settle the composition. Name the directions in one line and offer `/prototype` to compare them live.

Done when the turn ends on the proposal. Step 3 starts with the user's reply.

## 3. Act on the reply

- **Approved**: return to step 5 of [SKILL.md](SKILL.md) and build the approved structure.
- **Prototype accepted**: load `prototype` for its UI branch, handing it the references and the house style. Once the user picks a variant, return to step 5 and build that variant as real code.
- **Corrected**: revise the proposal and stop again.
