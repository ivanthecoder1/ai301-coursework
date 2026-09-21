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
| Maintainer activity | Repo-facts block: last 5 default-branch commits, maintainer first-response sample, and issue comment thread | Pass if the evidence shows either (a) a maintainer has commented on the issue within the past 60 days, (b) the maintainer first-response sample contains at least one maintainer response within the past 60 days, or (c) the last 5 default-branch commits include recent commits from repository maintainers or established contributors. Fail if the repo shows no maintainer activity across these sources. Unclear if the available evidence cannot establish activity. | required |
| Repo activity | Repo-facts block: last 5 default-branch commit dates | Pass if at least 1 of the last 5 commits was made within the past 90 days of the capture date. Fail otherwise. Unclear if the commit dates cannot be determined. | required |
| Newcomer scope | Issue body, comment thread, and relevant locations in `references/evidence-guide.md` | Pass if the issue defines a concrete deliverable or specific bug/feature change, provides enough detail to identify the implementation boundary, and does not require a major architectural redesign or unresolved product/design decision. Fail if it is explicitly an umbrella/tracking issue, a pure usage/support request, depends on unresolved design debate, has multiple abandoned attempts indicating unsettled scope, or is too underspecified to identify a concrete deliverable. A substantive bug fix or performance fix may still pass when the issue identifies the affected behavior or cause clearly. Unclear if the scope cannot be determined. | required |
| No existing contributor | Repo-facts block: assignees and linked PRs; issue comment thread | Pass if there is no assignee, active claim comment, or open linked PR indicating someone is working on the issue. Fail if any such evidence exists. Unclear if the available evidence cannot determine whether someone is working on it. | required |
| Contribution policy | Repo-facts block: contribution policy and any dedicated AI policy files | Pass if the repository permits AI-assisted contributions, is silent about AI use, or allows AI use subject to conditions such as disclosure, review, testing, or personal responsibility. Fail if the repository explicitly bans AI-generated code or documentation. Unclear if the available evidence cannot establish the policy. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->

Accept if every required check passes. Reject if any required check fails. Treat unclear as fail for required checks.