---
name: remove-citations
description: Remove explicit theorem citations from Acorn proofs by replacing each citation with local proof steps while keeping `acorn verify` passing after every attempted change. By default, make a full pass over the current `acorn citations` list unless the user explicitly narrows the scope. Use when the user asks to inline cited theorems, reduce `acorn citations` output, or improve proof style without changing the theorem being proved.
---

# Remove Citations

## Overview

Use this skill when an Acorn proof contains explicit theorem citations such as `foo(a)` and the goal is to replace them with ordinary proof lines. Unless the user explicitly names a smaller target, run a full pass over the current `acorn citations` list and check each citation for possible removal. Work one citation at a time and verify after each attempted edit, but treat a `shallow explosion` verification failure as a prover bug: stop the skill immediately, report the bug to the user, and leave the repository in the failing state instead of reverting it.

## Workflow

1. List the current citations.

```bash
acorn citations
```

This prints entries of the form `path:line: theorem(args)`.

2. Take the citations in order and work through the full list unless the user narrowed the scope. For each citation, read:
- the local proof around that line
- the cited theorem statement

Use `rg -n` to find the theorem definition and `sed -n` to inspect the relevant proof block.

3. Replace the citation with the smallest local expansion that should supply the same fact downstream.
- If the cited theorem concludes the needed statement directly, try that conclusion first.
- If that is too large a leap, insert the instantiated intermediate statements from the theorem body.
- Prefer ordinary proof lines that fit the local argument. Do not keep the citation in a disguised form.
- Stop there. Do not switch into broader proof repair, explication, or theorem restructuring just to remove one citation.

Example:

```acorn
theorem foo(x) {
    bar(x) and qux(x) implies zap(x)
}
```

If the proof currently says:

```acorn
foo(a)
```

first try:

```acorn
zap(a)
```

If that does not verify, try:

```acorn
bar(a)
qux(a)
zap(a)
```

4. After each attempted replacement, verify immediately.

```bash
acorn verify
```

5. If verification fails with a `shallow explosion`, stop immediately. Report that a prover bug was encountered, identify the file and line, and leave the repository in the failing state so the user can inspect it.

6. If verification fails for any other reason, you may try the obvious instantiated premises and conclusions of the cited theorem. If that still fails, revert that replacement completely and continue to the next citation.

7. Never leave the repository in a non-verifying state except for the special `shallow explosion` case above. The normal fallback is always "restore the last working version, then move on", not "repair the proof in some fancier way".

8. Repeat for every citation in scope unless a `shallow explosion` stops the run early. The default scope is the entire current `acorn citations` list. Run `acorn citations` again at the end to see what remains.

## Heuristics

- Expand the theorem statement, not the theorem name.
- Try the strongest useful conclusion first; only add premises when the prover needs them.
- Keep replacements local. If removing one citation requires a broader rewrite, skip it unless the user asked for that.
- If the direct conclusion and the theorem's obvious instantiated premises still do not verify, stop and revert. Do not explicate surrounding proofs or add unrelated helper steps.
- If verification reports `shallow explosion`, treat that as a prover bug, not as an ordinary proof failure.
- Existential and induction theorems often expand into bulky proof state. Remove those citations only when the replacement stays clear and short.
- Do not change the theorem being proved just to eliminate a citation.

## Success Criteria

The task is complete when:
- either `acorn verify` passes, or the run was stopped because of a reported `shallow explosion`
- every citation in scope has been checked for an obvious local replacement, unless the run stopped early because of a `shallow explosion`
- the number of `acorn citations` entries has been reduced as much as practical before completion or early stop
- every non-`shallow explosion` failed attempt has been reverted cleanly

## Output

Report:
- which citations were removed
- which citations were skipped because the inline replacement did not verify
- any `shallow explosion` bug encountered, including the file, line, and attempted replacement
- the final `acorn citations` status, if checked
