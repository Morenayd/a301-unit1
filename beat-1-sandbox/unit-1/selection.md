# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/11

**Verdict output**

1. #11 — Architecture doc doesn't explain the hybrid retrieval scoring formula. Smallest, best-contained surface: one file (`docs/ARCHITECTURE.md`), an explicit deliverable ("Add a section explaining the scoring logic with an example"), lowest stated effort (2–3 hours), and no production code to break. The real work is reading the retrieval code well enough to describe it — good orientation for a first contribution.

2. #15 — Agent session state is not cleared between reviews. The strongest write-up of the three: the maintainer names the root cause (`Orchestrator` keeps one `ContextManager` and never empties it), the observable symptom, and the fix ("Empty that cache and delete the profile's saved session state when run starts"). Ranked below #11 only because it touches three files inside `agent/memory` internals, and per `CONTRIBUTING.md` a seeded bug likely also requires removing an `@pytest.mark.xfail(strict=True)` marker.

3. #12 — Add snapshot tests for prompt templates. Passes scope — the requested result is specific and one file is named — but it leaves the most to you: the snapshot mechanism and the version-bump convention are both undecided, with no maintainer guidance in the thread. Highest stated effort (3–5 hours).

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/11",
    "checks": [
      {
        "name": "maintainer-active",
        "grade": "pass",
        "evidence": "Collaborator Aburke225 opened and labeled this issue 2026-09-10 and pushed commits through 2026-09-16, 12 days before today."
      },
      {
        "name": "repo-active",
        "grade": "pass",
        "evidence": "Repo not archived; last default-branch commit 2026-09-16 ('chore: track five more manifest entries against the tracker'); 76 open issues."
      },
      {
        "name": "first-issue-scope",
        "grade": "pass",
        "evidence": "Single named file docs/ARCHITECTURE.md with an explicit deliverable: 'Add a section explaining the scoring logic with an example.' Effort 2-3 hours."
      },
      {
        "name": "unclaimed",
        "grade": "pass",
        "evidence": "assignees: []; 0 comments; timeline contains only 'labeled' events, no linked PRs."
      }
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/15",
    "checks": [
      {
        "name": "maintainer-active",
        "grade": "pass",
        "evidence": "Collaborator Aburke225 opened and labeled this issue 2026-09-10 and pushed commits through 2026-09-16, 12 days before today."
      },
      {
        "name": "repo-active",
        "grade": "pass",
        "evidence": "Repo not archived; last default-branch commit 2026-09-16; 76 open issues."
      },
      {
        "name": "first-issue-scope",
        "grade": "pass",
        "evidence": "Root cause and remedy both stated: 'Orchestrator keeps one ContextManager and never empties it' / 'Empty that cache and delete the profile's saved session state when run starts'; three related files in agent/memory, which the rubric permits when the outcome is specific."
      },
      {
        "name": "unclaimed",
        "grade": "pass",
        "evidence": "assignees: []; 0 comments; timeline contains only 'labeled' events, no linked PRs (2026-09-16 update was a repo-wide manifest commit, not a claim)."
      }
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/12",
    "checks": [
      {
        "name": "maintainer-active",
        "grade": "pass",
        "evidence": "Collaborator Aburke225 opened and labeled this issue 2026-09-10 and pushed commits through 2026-09-16, 12 days before today."
      },
      {
        "name": "repo-active",
        "grade": "pass",
        "evidence": "Repo not archived; last default-branch commit 2026-09-16; 76 open issues."
      },
      {
        "name": "first-issue-scope",
        "grade": "pass",
        "evidence": "Specific requested result in one named file tests/unit/test_prompt_templates.py: 'snapshot tests that fail if a template's content changes without a version bump'; test work the rubric allows, though snapshot mechanism is left to the contributor."
      },
      {
        "name": "unclaimed",
        "grade": "pass",
        "evidence": "assignees: []; 0 comments; timeline contains only 'labeled' events, no linked PRs."
      }
    ],
    "verdict": "accept"
  }
]
```
## Eval iterations

**Run history**

- Smoke run: 2/3 scored issues matched the gold labels.
- Full run: 15/20 scored issues matched the gold labels.

**Issue analysis**

I analyzed `issue-01`. My rubric returned `reject`, while the gold label was `accept`. The check that caused the rejection was `first-issue-scope`.

The issue described a documentation task with a clear goal, but it also included a long list of requested updates across several related documentation files. My rubric interpreted that amount of work conservatively and rejected it as too large for a first contribution. The gold label treated it as acceptable because the work was still focused on one documentation goal and the requested changes were described in detail.

**Check rationale**

`first-issue-scope`: "Pass if the issue has a clear, bounded outcome and enough detail for a contributor to understand what to change, even if the change touches several related files. Documentation work, tests, localized bugs, contained features, and focused multi-file updates can pass when the requested result is specific. Fail if the issue is vague, open-ended, architectural, requires broad redesign, spans unrelated subsystems, or leaves major product/technical decisions to the contributor. If the scope cannot be determined from the issue, mark unclear."

I kept this check because I wanted the rubric to distinguish between issues that are broad in size and issues that are actually unclear or unsuitable for a first contribution. The current wording allows focused multi-file work when the expected result is specific, while still rejecting vague, architectural, or open-ended work that would require too much independent design or investigation.

**Trade-offs**

This check still gives up some recall on larger but well-specified issues. In the final run, `issue-01`, `issue-04`, and `issue-19` were still rejected by `first-issue-scope`, even though their gold labels were `accept`.

That shows the check can still be interpreted conservatively when an issue contains a lot of requested work, even if the outcome is bounded. I accept that trade-off because I would rather be cautious about recommending an issue that may be too large for a first contribution.

---

## Selection rationale

**Selection rationale**

1. This issue fits my interests because it involves understanding and explaining a retrieval system, which is relevant to the AI systems work I am currently learning. It is also a focused documentation task on one file with an estimated effort of 2–3 hours, so it looks realistic to complete within the time available.

2. The verdict correctly identified that the issue has a clear deliverable, a small surface area, an active repository, and no existing claim or linked pull request. It also correctly recognized that the task is bounded enough for a first contribution. Outside the rubric, I also considered whether the subject would be useful to me personally, and the hybrid retrieval/scoring topic made this more interesting than a purely mechanical documentation change.

3. I expect the main difficulty in claiming it to be making sure nobody else claims it before I do in Unit 2. Technically, I will also need to read the retrieval implementation well enough to explain the scoring formula accurately rather than only rewriting existing documentation.
