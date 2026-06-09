# Response-to-Reviewers & Revision  -  Reference

## Editable scope (content lock)
Editable: wording, clarity, structure, interpretation, framing, limitations, and the discussion. **Frozen:**
every number, table value, figure, statistic, CI, and citation fixed by `results_lock.json` and
`protocol_lock.json`. A prose change must never move a frozen value.

## Response-to-reviewers format
For each numbered point in `peer_review_register.json` (and each CA issue):
1. **Reviewer comment**  -  quoted verbatim.
2. **Response**  -  what was done, professional and non-defensive; if declined, a courteous evidence-based reason.
3. **Change in manuscript**  -  the revised text quoted, with its new location.

Group by reviewer; keep a running map so no point is missed. Coach the student to draft each response; model
one, then have them write the rest.

## Back-route handling (true analytic gaps)
A point is a back-route when answering it changes a number (new sensitivity analysis, added confounder,
re-specified model). Do not edit prose to fake it. Instead:
1. open a dated amendment noting the reviewer point and the analysis required;
2. return to Pipeline 2 (emp-04/05/06); run the analysis; re-issue `results_lock.json` with an incremented
   `lock.version` and the amendment recorded;
3. resume here, **rebind to the new lock version**, update the affected Results/Discussion text to the
   reissued numbers, and note the amendment (and the lock version) in the manuscript and the response letter.

## Lock-compliance check (before finishing V2)
Diff every number and citation in V2 against the locks. If anything differs without a logged amendment, it is
a violation  -  revert it. Record the clean diff result as a complianc