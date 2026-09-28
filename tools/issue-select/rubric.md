# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-active | Issue body and comment thread, plus recent repository activity described in the repo-facts block. | Pass if there is evidence of recent maintainer or contributor activity, such as issue/PR responses, merges, or commits within roughly the last 90 days. Fail if the project appears abandoned or maintainers have not responded to recent contribution activity for a long period. If the evidence is insufficient to tell, mark unclear. | required |
| repo-active | Repo-facts block, especially recent default-branch commit dates and recent issue/PR activity. | Pass if the repository shows ongoing development or maintenance, with recent commits, merged PRs, releases, or active issue discussion. Fail if there is no meaningful repository activity for roughly 6 months or more and no evidence that the project is intentionally stable. If activity is ambiguous, mark unclear. | required |

| first-issue-scope | Issue body, labels, linked discussions, and maintainer comments describing the requested work. | Pass if the issue has a clear, bounded outcome and enough detail for a contributor to understand what to change, even if the change touches several related files. Documentation work, tests, localized bugs, contained features, and focused multi-file updates can pass when the requested result is specific. Fail if the issue is vague, open-ended, architectural, requires broad redesign, spans unrelated subsystems, or leaves major product/technical decisions to the contributor. If the scope cannot be determined from the issue, mark unclear. | required |
| unclaimed | Issue body and complete comment thread, including assignment status and comments indicating someone has started or claimed the work. | Pass if no person is currently assigned to the issue and no recent commenter clearly says they are actively working on it or has been given the issue by a maintainer. Fail if the issue is assigned, a contributor has an active claim, or a maintainer has explicitly reserved it for someone else. Do not reject solely because someone previously expressed interest if they later withdrew, were told the issue was available again, or there is clear evidence the claim is stale. If ownership is ambiguous, mark unclear. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
Accept only when all required checks pass.

Reject if any required check fails.

Treat `unclear` as a failure for the final accept/reject verdict. A candidate should only be accepted when there is enough evidence to confidently determine that the repository is active, maintainers are responsive, the issue is appropriately scoped for a first contribution, and the issue is not already being worked on.

When multiple issues are accepted, rank them by first-contribution fit. Prefer, in order, issues with a clearly bounded change, explicit reproduction steps or expected behavior, relevant maintainer guidance, and fewer dependencies on unfamiliar parts of the repository. Ranking does not change the accept/reject verdict.
