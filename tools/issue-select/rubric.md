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
| scope-fit | Issue title and issue body | Pass if the issue names a specific observable problem to fix or a specific deliverable to produce. Examples include fixing a described bug, adding a named feature, updating identified documentation, or adding a specified test. Otherwise fail. | required |
| stalled-history | Repo-facts block: linked PRs; issue comment thread | Pass only if the issue has fewer than 2 linked closed PRs and the comment thread does not show multiple abandoned implementation attempts spanning more than 1 year. | required |
| repo-active | Repo-facts block: dates of the last 5 default-branch commits | Pass if at least 1 default-branch commit occurred within the last 90 days | required |
| available | Issue assignees, linked pull requests, issue body, and comment thread | Pass if there is no active linked pull request implementing the same issue and the issue has not been explicitly closed to new contributors. In Path Review live mode, ignore student claim comments as required by scope.md. | required |
| policy-fit | Repository contribution/policy information in the repo-facts block | Pass if the repository permits the contribution workflow required for this course, including AI-assisted development. Fail if the repository explicitly prohibits AI-generated or AI-assisted code/documentation, restricts required tooling, or otherwise states a contribution policy incompatible with completing the issue through the course workflow. | required |
| maintainer-responsive | Issue comment thread and repo-facts block, especially recent maintainer comments on open issues | Pass if a maintainer has commented on this issue or another recent issue within the last 60 days | preferred | 
| well-specified | Issue body and maintainer comments | Pass if the problem or expected outcome is described clearly enough to understand the contribution goal | preferred |


## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
Accept only if every required check passes. If a required check is unclear, it fails. Preferred checks never change the verdict and are used only to rank accepted issues.