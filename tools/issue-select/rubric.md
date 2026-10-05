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
| maintainer-alive | Repo facts: "last 5 default-branch commits" (dates and authors) | The newest default-branch commit by a human (or a bot merging a human's PR) is dated within 60 days of the capture date | required |
| maintainer-responsive | Repo facts: "maintainer first-response sample" | At least 1 sampled issue opened by a non-maintainer got a first maintainer comment within 14 days. Issues opened by a maintainer do not count either way | preferred |
| repo-in-use | Repo facts: "archived:" on the repo line, "last push to any branch", "latest release" | archived is `no`, AND (last push is within 90 days of the capture date OR latest release is within 365 days of the capture date) | required |
| bounded-scope | Issue body and comment thread; linked PRs and PRs mentioned in comments | The issue asks for one specific change. Fails if ANY of: it is an umbrella/tracking issue listing sub-tasks; the thread shows the design still being debated with no maintainer decision; a maintainer says the fix needs core-internals changes; it is a usage/support question; it has 2 or more closed-unmerged PRs; it is a feature request that names a wish but specifies no behavior, and no maintainer has stated what should be built (a product decision is still open). A short body or missing repro steps alone does NOT fail it | required |
| unclaimed | Repo facts: "this issue: assignees" and "linked PRs"; Comments section (claim comments, mentioned PRs, with dates) | No assignee, AND no open linked PR, AND no open PR mentioned in the comments, AND no "I'll take this / working on this" claim comment dated within 30 days of the capture date. A claim older than 30 days with no PR since counts as abandoned and passes | required |
| ai-policy-allows | Repo facts: "contribution policy" line | The policy does not ban AI-generated/AI-assisted contributions outright. Conditions (disclose, understand, test, human-review) pass; no policy stated passes | required |
| maintainer-in-thread | Comments section: author_association of commenters | At least one OWNER/MEMBER/COLLABORATOR comment in the thread, or the issue was opened by one | preferred |
| newcomer-label | Issue labels | Has a label such as `good first issue`, `help wanted`, `beginner`, or `easy` | preferred |

## Verdict rule

Accept if every `required` check passes; otherwise reject. `preferred`
checks never change the verdict; they only rank accepted issues.

Unclear handling: for maintainer-alive, repo-in-use, and bounded-scope,
`unclear` counts as fail (no evidence of life or of a bounded task is a
reason to walk away). For unclaimed and ai-policy-allows, missing evidence
counts as pass (no assignee listed, no claim comment, or no stated policy
means nothing is blocking you).

In live mode on Path Review, the house rule in scope.md overrides the
claim-comment part of `unclaimed`: classmates' claim comments do not block
an issue.
