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

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/23

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
All three URLs are in the scoped repo, so all three are valid candidates. Evidence gathered live via the GitHub API (gh isn't installed here). Graded against rubric.md; Path Review's house rule on claim comments didn't come into play — none of the three has any comment at all.

Shared repo facts (measured against today, 2026-09-21):

Last default-branch commits: 2026-09-16 (×3, Aburke225), 2026-08-24 — repo not archived, pushed 2026-09-16.
Maintainer Aburke225 (COLLABORATOR) commented on issues #52 and #43 on 2026-09-16.
docs/CONTRIBUTING.md + PR template: conventional commits, green CI, xfail-marker removal. No AI ban, no AI_POLICY.md/AGENTS.md.
All three: no assignees, no linked PRs (timelines show label events only), zero comments, opened 2026-09-10.

Accepted, in fit order:

#23 — end-to-end agent test with stubbed tools — best fit: pytest integration testing against an unfamiliar Python codebase plus mock-LLM/agent tooling, which is exactly the testing + AI/LLM tooling the profile wants to grow. No new framework. Preferred checks both pass.
#35 — webhook system for completed reviews — FastAPI route + service layer, REST/backend work squarely in the profile's wheelhouse; ranked below #23 only because it's the largest (8–12 h) and adds less of the testing/LLM skill the profile is targeting. Preferred checks both pass.
#50 — dependency vulnerability scan in CI — accepted and well-specified, but it is pure CI/DevOps work (.github/workflows/ci.yml), the area the profile asked to avoid. Preferred checks both pass.

Rubric tension worth noting (not a verdict change): all three carry tier-3 = "Advanced difficulty" and none carries good first issue; estimates run 3–12 hours. My scope-fit check only asks for a specific observable problem or deliverable, which all three satisfy, so the rubric has no difficulty or size threshold at all. If I want tier-3 issues filtered out of first-issue candidates, that belongs as a new required check in rubric.md, not as an override here.

[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/23",
    "checks": [
      {"name": "scope-fit", "grade": "pass", "evidence": "Names a specific deliverable: 'Add an integration test using stub implementations of all tools and the mock LLM' in tests/integration/test_agent_orchestrator.py"},
      {"name": "stalled-history", "grade": "pass", "evidence": "Timeline shows only 5 label events, no linked PRs; 0 comments; opened 2026-09-10 (11 days old)"},
      {"name": "repo-active", "grade": "pass", "evidence": "Three default-branch commits dated 2026-09-16, 5 days before today"},
      {"name": "available", "grade": "pass", "evidence": "assignees: [], no linked PRs in timeline, 0 comments, issue state open"},
      {"name": "policy-fit", "grade": "pass", "evidence": "docs/CONTRIBUTING.md sets workflow conditions (conventional commits, green CI, xfail removal) and states no AI restriction; no AI_POLICY.md in repo root"},
      {"name": "maintainer-responsive", "grade": "pass", "evidence": "Aburke225 (COLLABORATOR) commented on issues #52 and #43 on 2026-09-16, within 60 days"},
      {"name": "well-specified", "grade": "pass", "evidence": "'There is no test that exercises the full agent lifecycle (plan → execute → synthesize) without live dependencies' plus the target test file"}
    ],
    "verdict": "accept"
  }
]
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

agreement: 13/20 scored items
agreement: 1/7 scored items
agreement: 1/2 scored items
agreement: 0/3 scored items
agreement: 0/3 scored items
agreement: 0/3 scored items
agreement: 3/3 scored items
agreement: 2/3 scored items
agreement: 19/20 scored items

**Issue analysis**

issue-15 — my final rubric decided reject, and the gold label was also reject. The issue looked appealing at first because it had good first issue and help wanted labels, but the history told a different story. It had two linked closed PRs and years of previous contributor attempts and discussion. My earlier rubric focused too much on whether the task itself sounded bounded, so it accepted the issue. I added a separate stalled-history check so the rubric could distinguish a clearly stated task from one that had repeatedly resisted implementation.

**Check rationale**

"| stalled-history | Repo-facts block: linked PRs; issue comment thread | Pass only if the issue has fewer than 2 linked closed PRs and the comment thread does not show multiple abandoned implementation attempts spanning more than 1 year. | required |"

I added this check because a task can look small and well-scoped from its title or description while its history shows that contributors have repeatedly been unable to finish it. I separated this from scope-fit so technical difficulty alone would not cause a rejection, while repeated abandoned attempts could still signal that an issue is a poor first contribution.

**Trade-offs**

This check intentionally gives up some flexibility by using visible historical signals such as multiple closed PRs. A legitimate issue could have two previous closed PRs for reasons unrelated to difficulty and still be a reasonable first contribution. I accepted that trade-off because it fixed the false acceptance of issue-15, while re-running the scope canaries with --only issue-01,issue-15,issue-19 produced 3/3: issue-01 and issue-19 remained accepted while issue-15 was rejected.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. Issue #23 fits both my interests and the time I have available because it involves Python, pytest integration testing, stubbed tools, and a mock LLM/agent workflow. I already have experience with Python and agentic AI, but I want more practice testing unfamiliar production-style code, so it feels like a useful stretch without requiring me to learn an entirely new framework.
2. The verdict correctly identified that the issue is active, available, clearly specified, and has a concrete deliverable. It also ranked it above the other accepted issues because it aligns with my interest in testing and AI/LLM tooling. What the rubric did not really weigh was the tier-3 advanced-difficulty label and whether that difficulty will make the implementation take longer than expected, so I considered that separately when choosing among the accepted issues.
3. I expect claiming it to be relatively straightforward because the live run found no assignee, linked PR, or existing comments on the issue. The main difficulty will probably come after claiming it: understanding the existing agent orchestration and test structure well enough to create an end-to-end test without relying on live dependencies.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
