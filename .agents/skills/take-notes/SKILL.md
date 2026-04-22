---
name: take-notes
description: Keep the repository's `notes/` directory updated as a structured roadmap. Use when the user asks to take notes, update planning notes, add roadmap items, create or revise topic todo files, or keep long-term mathematical project notes in the existing `notes/` style.
---

# Take Notes

Use this skill when the user wants persistent planning notes in this repository rather than a transient chat summary.

## Notes Layout

The notes live under `notes/`.

- `notes/todo.md` is the top-level roadmap.
- Each major topic gets its own subfolder under `notes/`.
- Each topic subfolder contains its own `todo.md`.
- This structure is recursive: if a topic-level `todo.md` is still too broad, make subfolders inside that topic, each with its own `todo.md`.

Current topic folders are expected to follow the existing roadmap structure, for example:

- `notes/foundations/todo.md`
- `notes/order-theory/todo.md`
- `notes/algebraic-hierarchy/todo.md`
- `notes/real-analysis/todo.md`

## Style

Keep the notes terse and structured.

- Prefer short headings and short checklist items.
- Use Markdown checklists: `- [ ] item`.
- Keep top-level roadmap items broad.
- Keep topic-level items more concrete and implementation-oriented.
- Avoid nested bullets unless the user explicitly asks for a more detailed hierarchy.
- Prefer updating existing files over creating duplicate note files.
- Prefer recursive folder structure over long flat todo lists when a topic is still too broad.

## Workflow

1. Read `notes/todo.md` first.
2. If the request concerns an existing topic, update that topic's `notes/<topic>/todo.md`.
3. If the request introduces a new major topic, update `notes/todo.md` and create a new topic subfolder with its own `todo.md`.
4. Keep the top-level roadmap and topic folders consistent with each other.
5. When expanding a topic, keep the lower `todo.md` between 10 and 30 checklist items unless the user explicitly wants a different size.
6. When adding a new top-level roadmap from scratch, aim for 10 to 30 broad areas.
7. Before working on a topic in note-taking mode, check whether its current `todo.md` is narrow enough that one unchecked item could reasonably be completed in one session.
8. If it is not narrow enough, first break that topic into subtopics by creating subfolders and a new lower-level `todo.md`, then work from that narrower list.
9. Keep drilling down recursively until the active `todo.md` is session-sized.
10. If the user asks to record progress, mark completed items and add short new unchecked items only when they reflect real next steps.
11. Do not turn the notes into prose documentation. These files are for planning and tracking.

## Naming Conventions

- Use lowercase, hyphenated folder names.
- Name the per-topic file `todo.md`.
- Keep topic titles in Markdown synchronized with the corresponding roadmap entry.

## Preferred Edits

- Update links in `notes/todo.md` when topic folders are added or renamed.
- Preserve stable folder names once they exist.
- If a topic becomes too large for session-sized work, split it into subtopics before attempting the work itself.
- When splitting a topic, make the parent `todo.md` point to the narrower subfolders.
- Stop splitting when a single bullet is concrete enough to plausibly complete in one session.

## Output

When you finish a note-taking request, report:

- which note files were updated
- whether any new topic folders were created
- any major roadmap changes that affect navigation
