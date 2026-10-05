# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/55

**Verdict output**

Live-mode run on three candidates (#55, #58, #66), run on 2026-10-04 with
`claude -p "issue-select: grade these candidate first issues: <URL> <URL> <URL>"`.
All three were accepted; #55 ranked first. Pasted verbatim:

````
I have all the evidence I need. Let me grade all three issues now.

---

## Grading Summary

**Today's date:** 2026-10-04 | **Capture date for thresholds:** same

### Repo-level signals (shared by all three)

- **archived:** no
- **last push:** 2026-09-16 (18 days ago — within both the 60-day and 90-day windows)
- **last 5 commits:** all by `Aburke225` (Andrew Burke), newest 2026-09-16 → maintainer-alive ✓
- **AI/contribution policy:** no CONTRIBUTING.md, no AI_POLICY.md, PR template has no AI clause → silence passes ✓

---

### Issue #55 — "Skill extractor fails to detect JavaScript and TypeScript"

| Check | Grade | Evidence |
|---|---|---|
| maintainer-alive | **pass** | Newest commit by Aburke225 on 2026-09-16, 18 days ago < 60-day threshold |
| repo-in-use | **pass** | archived=no; last push 2026-09-16, 18 days ago < 90-day threshold |
| bounded-scope | **pass** | Asks for specific regex fixes in `_detect_languages`/`_detect_tools`; exact failing tests named (`test_javascript_detection` etc.); not an umbrella; no design debate |
| unclaimed | **pass** | No assignees; no open linked PRs (none found in open-PR list); all claim comments are from students → house rule: do not block |
| ai-policy-allows | **pass** | No policy stated; silence passes |
| maintainer-responsive *(preferred)* | **unclear** | All three sampled issues were opened by the maintainer, so they "do not count either way"; no non-maintainer-opened issues were sampled |
| maintainer-in-thread *(preferred)* | **pass** | Issue was opened by Aburke225, the repo's only committer → OWNER/MEMBER |
| newcomer-label *(preferred)* | **fail** | Labels are `bug`, `ingestion`, `tier-1` — no `good first issue` / `help wanted` label |

**Verdict: ACCEPT** — all 5 required checks pass.

---

### Issue #58 — "Bias detector patterns are too narrow to match common phrasings"

| Check | Grade | Evidence |
|---|---|---|
| maintainer-alive | **pass** | Newest commit by Aburke225 on 2026-09-16, 18 days ago < 60-day threshold |
| repo-in-use | **pass** | archived=no; last push 2026-09-16, 18 days ago < 90-day threshold |
| bounded-scope | **pass** | Asks to widen regex patterns in `bias_detector.py`; 9 specific xfailing tests named; no open design debate; not an umbrella issue |
| unclaimed | **pass** | No assignees; no open linked PRs; all claim comments are from students → house rule: do not block |
| ai-policy-allows | **pass** | No policy stated; silence passes |
| maintainer-responsive *(preferred)* | **unclear** | Same as #55 — no non-maintainer-opened issues sampled |
| maintainer-in-thread *(preferred)* | **pass** | Issue was opened by Aburke225, the repo's only committer → OWNER/MEMBER |
| newcomer-label *(preferred)* | **fail** | Labels are `bug`, `safety`, `tier-1` — no `good first issue` / `help wanted` label |

**Verdict: ACCEPT** — all 5 required checks pass.

---

### Issue #66 — "structlog output is not captured by pytest caplog — log assertions fail suite-wide"

| Check | Grade | Evidence |
|---|---|---|
| maintainer-alive | **pass** | Newest commit by Aburke225 on 2026-09-16, 18 days ago < 60-day threshold |
| repo-in-use | **pass** | archived=no; last push 2026-09-16, 18 days ago < 90-day threshold |
| bounded-scope | **pass** | Single, surgical fix: configure structlog in `tests/conftest.py`; exact failing test named; concrete reproduction command given; no design debate |
| unclaimed | **pass** | No assignees; no open linked PRs; all claim comments from students → house rule: do not block |
| ai-policy-allows | **pass** | No policy stated; silence passes |
| maintainer-responsive *(preferred)* | **unclear** | Same as above — no non-maintainer-opened issues sampled |
| maintainer-in-thread *(preferred)* | **pass** | Issue was opened by Aburke225, the repo's only committer → OWNER/MEMBER |
| newcomer-label *(preferred)* | **fail** | Labels are `bug`, `tests`, `tier-1` — no `good first issue` / `help wanted` label |

**Verdict: ACCEPT** — all 5 required checks pass.

---

### Ranking by fit profile

All three accepted. Fit ranking (fit never changed a verdict — it only orders here):

1. **#55** *(top pick)* — labeled `ingestion`, directly in your strongest area. The fix is regex surgery in one Python file (`skill_extractor.py`) with five pinned failing tests to drive TDD. Matches your stated preference for RAG/ingestion/API issues you can close in a week.
2. **#66** *(second)* — labeled `tests`, matching your explicit "want to get better at pytest/async mocks" goal. The fix is a single `conftest.py` change; the scope is the most surgical of the three.
3. **#58** *(third)* — also a bounded regex bug in Python, but the `safety` label doesn't match any of your top-priority areas; rank below the other two.

---

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/55",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Newest commit by Aburke225 on 2026-09-16, 18 days before capture date (< 60-day threshold)"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived=no; last push 2026-09-16, 18 days before capture date (< 90-day threshold)"},
      {"name": "bounded-scope", "grade": "pass", "evidence": "Asks for specific regex fixes in _detect_languages/_detect_tools with five named xfailing tests; not an umbrella; no open design debate"},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, no open linked PRs, no open PRs in thread; all claim comments are from students (house rule: do not block)"},
      {"name": "ai-policy-allows", "grade": "pass", "evidence": "No CONTRIBUTING.md, no AI policy file, no AI clause in PR template; silence passes"},
      {"name": "maintainer-responsive", "grade": "unclear", "evidence": "All sampled issues were opened by the maintainer and do not count; no non-maintainer-opened issues were sampled"},
      {"name": "maintainer-in-thread", "grade": "pass", "evidence": "Issue was opened by Aburke225, the repo's sole committer (OWNER/MEMBER)"},
      {"name": "newcomer-label", "grade": "fail", "evidence": "Labels are bug, ingestion, tier-1 — no good-first-issue or help-wanted label"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/66",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Newest commit by Aburke225 on 2026-09-16, 18 days before capture date (< 60-day threshold)"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived=no; last push 2026-09-16, 18 days before capture date (< 90-day threshold)"},
      {"name": "bounded-scope", "grade": "pass", "evidence": "Single fix: configure structlog in tests/conftest.py; one named failing test with exact reproduction command; no design debate"},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, no open linked PRs, no open PRs in thread; all claim comments are from students (house rule: do not block)"},
      {"name": "ai-policy-allows", "grade": "pass", "evidence": "No CONTRIBUTING.md, no AI policy file, no AI clause in PR template; silence passes"},
      {"name": "maintainer-responsive", "grade": "unclear", "evidence": "All sampled issues were opened by the maintainer and do not count; no non-maintainer-opened issues were sampled"},
      {"name": "maintainer-in-thread", "grade": "pass", "evidence": "Issue was opened by Aburke225, the repo's sole committer (OWNER/MEMBER)"},
      {"name": "newcomer-label", "grade": "fail", "evidence": "Labels are bug, tests, tier-1 — no good-first-issue or help-wanted label"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/58",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Newest commit by Aburke225 on 2026-09-16, 18 days before capture date (< 60-day threshold)"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "archived=no; last push 2026-09-16, 18 days before capture date (< 90-day threshold)"},
      {"name": "bounded-scope", "grade": "pass", "evidence": "Asks to widen specific regex patterns in bias_detector.py; 9 named xfailing tests; no open design debate; not an umbrella issue"},
      {"name": "unclaimed", "grade": "pass", "evidence": "No assignees, no open linked PRs, no open PRs in thread; all claim comments are from students (house rule: do not block)"},
      {"name": "ai-policy-allows", "grade": "pass", "evidence": "No CONTRIBUTING.md, no AI policy file, no AI clause in PR template; silence passes"},
      {"name": "maintainer-responsive", "grade": "unclear", "evidence": "All sampled issues were opened by the maintainer and do not count; no non-maintainer-opened issues were sampled"},
      {"name": "maintainer-in-thread", "grade": "pass", "evidence": "Issue was opened by Aburke225, the repo's sole committer (OWNER/MEMBER)"},
      {"name": "newcomer-label", "grade": "fail", "evidence": "Labels are bug, safety, tier-1 — no good-first-issue or help-wanted label"}
    ],
    "verdict": "accept"
  }
]
```
````

---

## Eval iterations

**Run history**

1. Full run, rubric v1: no score. The harness crashed before grading anything
   (`FileNotFoundError`): on Windows, Python's `subprocess` cannot launch the
   `claude.cmd` npm shim by the bare name `claude`. Fixed by resolving the path
   with `shutil.which("claude")` in `run_eval.py`.
2. `--only issue-06,issue-09,issue-14,issue-20`, rubric v1: 0/1 scored. Three
   items errored on a Windows encoding problem (`UnicodeEncodeError` on `→` and
   emoji in the bundles; fixed by setting `PYTHONUTF8=1`). The one item that
   graded, issue-06, came back reject vs gold accept, failed on
   `maintainer-alive`.
3. `--only issue-06,issue-09,issue-14,issue-20`, rubric v2: 4/4.
4. Full run, rubric v2, saved with `--save-run`: **19/20** (bar: PASS; categories
   claimed 4/4, clear-accept 7/8, dead-repo 3/3, policy 1/1, scope 4/4). This is
   the run in `eval-run.txt`.

**Issue analysis**

issue-19 (zxcalc/zxlive#517, "Selecting large subgraphs in proof mode freezes the
UI"). My rubric decided **reject**; the gold label is **accept**. It failed only on
`bounded-scope`. The body reads: "There are two potential causes which should be
fixed: 1. The matchers are slow for certain rewrites (quadratic instead of linear)
2. UI update is waiting for the matching thread to finish", followed by
"Additional suggestions:" with three more items (multi-processing, matching only
expanded categories, applying the rewrite in a separate thread). The grader
counted five work items and read it against my fail condition "it is an
umbrella/tracking issue listing sub-tasks", recording: "Body lists 5 distinct work
items ... an umbrella issue with sub-tasks". The gold note calls it a
"maintainer-diagnosed performance bug with named causes": one symptom, opened by a
COLLABORATOR who already found the causes, and the "additional suggestions" are
optional. My condition does not tell apart a list of separate deliverables (like
issue-10's megaissue) and a list of causes behind one bug, so the numbered list
pushed it to reject.

**Check rationale**

> | maintainer-alive | Repo facts: "last 5 default-branch commits" (dates and authors) | The newest default-branch commit by a human (or a bot merging a human's PR) is dated within 60 days of the capture date | required |

My first version required two things: a human commit within 60 days AND "at least
2 of the sampled issues got a first maintainer comment within 14 days". In run 2,
issue-06 failed it even though its gold label is accept. Its response sample is
five issues, four of them opened by a maintainer on the capture day with "no
maintainer comment in thread" — a maintainer does not reply to their own issue, so
the sample measured nothing. Commits are the more direct evidence of a living
maintainer (issue-06's newest is 2026-07-14, 22 days before capture), so I kept
the commit test as the required check and moved response speed into a separate
`maintainer-responsive` preferred check that ignores maintainer-opened issues.

**Trade-offs**

The check now gives up catching a repo where the maintainer still commits but
never answers outside contributors: response speed can no longer reject an issue,
only rank it. issue-06 is the case it changes (reject in run 2, accept in run 4,
with `maintainer-responsive` graded unclear). Nothing changed for the dead repos:
in the full run, issue-02 (newest commit 2023-12-09), issue-07 (2025-02-10), and
issue-17 (2021-11-13, archived) all still failed `maintainer-alive` and
`repo-in-use` on commit and push dates alone, so dead-repo stayed 3/3 without the
response-sample condition.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. The issue's fit to your interests and to the time available.

   I picked #55 because I already use every technology the failing tests are about:
   I have built projects with JavaScript, TypeScript, PostgreSQL, and Docker, so I
   know what clues identify them (for example `psycopg2` means PostgreSQL, and
   `FROM` / `EXPOSE` means a Dockerfile). The fix stays in one Python file,
   `ingestion/parsers/skill_extractor.py`, and five named tests tell me when I am
   done, so I think I can reproduce and fix it within a week next to my classes.

2. What the verdict identified correctly, and what you weighed that the rubric could
   not.

   The skill was right that the issue is a real, bounded bug: a maintainer opened it,
   it names the exact file and the failing tests, nobody is assigned, there is no
   linked PR, and the repo had commits 18 days ago. What it could not weigh is that
   a classmate, jing2003, commented a week ago and already reproduced the bug, so I
   am not the first one on it. The house rule says shared issues are fine, so this
   did not change my choice, but it means I should move quickly. It also could not
   know that I care about this area because I have built a RAG project and a
   learning platform that deal with the same kind of text processing.

3. The anticipated difficulty in claiming it.

   The hard part is that other students are already in the thread, so my claim
   comment has to add something instead of repeating them. I plan to reproduce the
   five failures myself on Windows, post my own results, and say which part I will
   focus on (for example the TypeScript and database detection). I also have to be
   careful that my fix makes the five xfail tests pass without breaking the Python
   detection tests that pass today.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
