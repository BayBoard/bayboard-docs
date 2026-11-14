# BayBoard help documentation

This is a public Mintlify help site. Treat every change as customer-facing
publication material. See [README.md](https://github.com/BayBoard/bayboard-docs/blob/main/README.md) for the local preview,
validation, writing, and screenshot conventions.

This documentation supports a live service used by paying customers. Treat
instructions that affect customer workflows as release-sensitive; do not
publish speculative steps, unsafe recovery advice, or unverified behavior.

## Public-safe content

- Do not add internal host paths, private identifiers, employee or customer
  information, private repository content, or non-public operating details.
- Do not open, copy, or publish environment files, credentials, or tokens.
- Describe only customer-visible behavior that is released now. Verify a new
  feature claim against an approved current source. If that source is not
  available, ask for the smallest confirmation needed rather than guessing.
- Screenshots must be real captures of the app with fictional or demo data.
  Do not create product UI imagery or publish identifiable information.

## Change and publication boundary

- A wording correction supported by the current app may be edited and checked.
- Treat a new or changed feature claim as unverified until its current release
  status is confirmed.
- Work on a branch and open a pull request. Never commit or push directly to
  `main`. Stop at PR-ready unless the repository owner explicitly approves
  merging or publishing; a delegated editing task is not that approval.
- Use `mint validate` and `mint broken-links` for documentation changes.
  A pull request may provide a preview. Merging `main` publishes the help site
  and requires explicit authorization.

## Review before PR-ready

- Keep security finding details, affected identifiers, and dispositions in an
  approved private record. Never put them in public files, PRs, issues, commit
  messages, or fix descriptions; put only a sanitized status in the public PR.
- The standard toolkit is required CI, one cross-family adversarial review
  per PR, Bugbot when usage is available, and Daybreak security checks
  appropriate to the change. General Codex GitHub Code Review is not required.
  Record and skip Bugbot when its usage quota is exhausted; do not describe
  that skip as a clean review. Diagnose other failures and triage findings.
- After consequential fixes, obtain a targeted confirming adversarial review
  of the corrections and their interactions. Do not repeat full reviews or
  repository scans for every small edit without a reason.
- Keep security-relevant Docs review in an approved private channel. Daybreak
  PR security review and default-branch monitoring are separate: an unmerged
  PR needs coverage of its own diff. Run broader scans at meaningful
  integration/release points. Record exact reviewed SHA and scope; pending,
  unavailable, failed, or skipped checks are not clean results. If a public
  review exposes security details, do not repeat them; alert the repository
  owner for private handling. Required security coverage remains a gate.
- For a configured repository scan, inspect the Security Findings dashboard
  separately. Record its last scanned ref and time; keep relevant dispositions
  private. Record "not configured" only when verified; if access is unavailable,
  record "unable to verify" with the reason, not a clean scan. A repository
  scan does not cover an unmerged PR by itself. Track unrelated findings with
  an owner in an approved private tracker or record without blocking every PR.
- Resolve in-scope actionable findings before PR-ready. If required review
  evidence is unavailable, report **not ready** and the exact blocker.

## Automatic review configuration

The approved initial Docs configuration leaves automatic general Code Review,
automatic PR security review, continuous monitoring, and scheduled scans off.
Keep required CI and independent cross-family adversarial review, with Bugbot
when usage is available. Request focused private security checks when a change
affects executable code, deployment configuration, or security-sensitive content.
Required security coverage must address the final relevant diff before merge.
This proportional configuration does not waive security checks or publication
approval. Record actual settings and evidence separately from this intended
policy. Do not publish private security details through review comments.

## Task execution

- Make routine, reversible implementation decisions within the approved
  scope and existing contracts. Ask early about unresolved product decisions,
  material scope changes, or actions requiring additional authorization;
  continue independent safe work while the answer is pending.
- Complete authorized work and required verification before handoff. Stop at
  the requested review or publication boundary, a missing required decision
  or permission, or a concrete blocker; state what remains and why.
- Preserve required security, regression, review, and release checks. Once
  they cover the final change, rerun or expand only for changed code, failure,
  new evidence, unresolved risk, or an explicit requirement.
- Use existing task notes for compact long-task state and verification. Give
  concise evidence and limitations; do not require extra files for small work
  or request hidden reasoning. Revisit settled decisions when new evidence
  or instructions warrant it, and correct discovered mistakes.
- Load skills, references, and tools only when explicitly requested, required
  by governing instructions, or relevant to the current task. Do not bulk
  load capabilities or warm caches at session start. Host-managed discovery
  is separate from agent invocation; these rules do not disable it.

## Security review context

For Code Review, use [SECURITY.md](SECURITY.md) as a threat map. Check
customer-facing instructions against an approved current app source, inspect
screenshots for private data, and verify changed outbound destinations. Treat
model scenarios as hypotheses and keep security finding details in the approved
private record above.
