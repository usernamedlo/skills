---
name: design-dlo
description: Apply a design, visual, UX or UI change request to the code, in the project's house style.
argument-hint: "The design change you want"
disable-model-invocation: true
---

# design-dlo

Turn a design request into code on one **surface**: the page, section or component the request names. This skill always ends in code; a review with no change wanted belongs to `better-interface`.

The **house style** is the project's own design language: its documented rules, its tokens, its component library, the way its existing surfaces are built. House style outranks every rule a loaded skill prescribes, and skills fill only what it leaves open. A project that writes `active:scale-[0.97]` keeps `0.97` against `better-ui`'s `0.96`.

A skill or MCP server that is unavailable is **skipped**: carry on without it and name it in the report.

## 1. Learn the house style

Read the design rules in the project's `AGENTS.md` / `CLAUDE.md` and every reference file they name. Where nothing is documented, derive the house style from the code: tokens (CSS variables, Tailwind config), the component library, and the two components nearest the surface.

Done when every convention you are about to rely on has a file you can cite for it.

## 2. Classify the request

- **Retouch**: the surface exists, and the request changes how it looks, reads, moves or behaves.
- **New surface**: the page, section or component does not exist yet.

Done when you have stated which one it is, in one line.

## 3. Load the rules

Load `better-ui` and `better-layout`. Then load every row the request touches:

| The request touches | Load |
| --- | --- |
| Motion: transitions, press and hover feedback, enter and exit | `animate`, with the motion part of the request as its argument |
| Type | `better-typography` |
| Color | `better-colors` |
| Copy | `better-writing` |
| Focus, keyboard, hit areas, contrast | `better-accessibility` |
| Forms, navigation, feedback states, charts | `ui-ux-pro-max`, one `--domain` or `--stack` query. The house style stands in for its `--design-system` step. Its script is `scripts/search.py` under the skill's own base directory: use that path when `CLAUDE_PLUGIN_ROOT` is unset. |

Take each skill's rules, values and checks. The process and the output belong to this skill: where a loaded skill prescribes an audit, a report format or a plan file, the steps below replace it.

Done when every matching row is loaded.

## 4. New surface only

A new surface needs references and an approved proposal first: read [NEW-SURFACE.md](NEW-SURFACE.md) and complete it before step 5. A retouch goes straight to step 5.

## 5. Implement

Write the change in the house style, reusing what the project already has. Adding a dependency or installing a registry component needs the user's yes first.

Scope is the surface: the files you write are its code and nothing else. A defect you notice outside it goes on the **spotted** list for the report, unfixed.

Done when every part of the request is visible in the diff and the diff stays on the surface.

## 6. Verify

1. Run the project's type check and lint on the files you touched.
2. Look at the surface. When a dev server is already running, load `playwright-cli` and screenshot the surface, navigating read-only: the server may sit on a production database, so submit nothing. Starting a server is the user's call. With no server running, the surface is **not visually verified**.

Done when the touched files pass type check and lint (or each remaining failure is shown to predate your change), and the surface is either seen in a screenshot that shows the request applied or marked not visually verified.

## 7. Report

- **Changed**: what is different on the surface, with file links.
- **Verified**: what the screenshot shows, or "not visually verified" with the URL to open.
- **Spotted**: defects outside the surface, one line each.
- **Skipped**: every unavailable skill or MCP server.

**Spotted** and **Skipped** appear only when they have something to say.
