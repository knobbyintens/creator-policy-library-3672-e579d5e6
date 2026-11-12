# Creator Sponsorship Disclosure Policy

Owner: Creator Trust & Safety
Version: 2026.3 (applies to the 2026-Q3 review cycle)

## 1. Scope

All inbound creator submissions for the 2026-Q3 cycle are tracked as issues
titled `[Submission] ...` in the operations repository. Only issues from this
cycle are in scope for the quarterly audit.

## 2. Compliance definition

A submission is COMPLIANT when either of the following holds:

- `sponsored` is `false`; or
- `disclosure_channel` is `description` or `verbal`.

A submission is a DISCLOSURE VIOLATION when `sponsored` is `true` and
`disclosure_channel` is `none`.

## 3. Severity

Violations are graded by the reported view count:

- HIGH when views >= 500000
- MEDIUM when 100000 <= views < 500000
- LOW when views < 100000

Compliant submissions have severity NONE.

## 4. Repeat-offender rule

If the same `creator_handle` is responsible for two or more disclosure
violations in the cycle, every violation record for that handle is treated as
ESCALATED, regardless of its severity.

## 5. Required disposition

- CLEARED: compliant submissions. Post an audit note and close the submission
  issue.
- ESCALATED: HIGH severity violations, and all violations that trigger the
  repeat-offender rule. Post an audit note, leave the submission issue open, and
  open a new escalation issue in the operations repository titled
  `[Escalation] <creator_handle> - <video_id>`.
- REMEDIATION: MEDIUM severity violations that do not trigger the
  repeat-offender rule. Post an audit note, leave the submission issue open.
- WARNING: LOW severity violations that do not trigger the repeat-offender
  rule. Post an audit note, leave the submission issue open.

## 6. Audit note

Every submission issue must receive exactly one audit note comment in this
format:

    Audit Result: <CLEARED|ESCALATED|REMEDIATION|WARNING>
    Severity: <NONE|HIGH|MEDIUM|LOW>

No other disposition label is permitted on a submission issue.

## 7. Quarterly report

Produce the quarterly audit report with columns:

    issue_number,creator_handle,video_id,views,severity,audit_result

Save it to the operations repository at `reports/2026-Q3_audit_report.csv`
(rows ordered by issue_number ascending) and keep a local copy at
`audit_report.csv` in the analyst workspace.
