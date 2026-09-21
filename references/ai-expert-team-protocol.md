# AI Expert Team Protocol for Thesis Problems

## When to escalate

Use `ai-expert-team` for:

- conflict between EYD, template, and supervisor instructions;
- ambiguous citation or source support;
- causal claims or generalization beyond the design;
- serious Bab IV–V argument problems;
- high-risk DOCX operation involving fields, numbering, complex tables, revisions, or layout;
- disagreement that cannot be resolved by the supplied sources.

Do not use a council for a typo, one obvious punctuation error, or a directly documented style change.

## Council contract

The latest user request determines mutation scope. An audit request is read-only. Every handoff must state:

- `from`, `to`, and task reference;
- scope and out-of-scope;
- relevant files/sources;
- allowed tools;
- forbidden edit/commit/push/publish actions;
- evidence required;
- acceptance criteria;
- output fields.

Use one decision owner, 3–5 non-overlapping specialists, and a verifier. Suitable roles include:

- EYD/language reviewer;
- UNDIP template/format reviewer;
- citation/source auditor;
- methodology/claim-calibration reviewer;
- DOCX preservation reviewer;
- evidence verifier.

## Evidence rules

Every specialist report separates:

- verified facts;
- interpretation;
- assumptions;
- uncertainty;
- rejected alternatives;
- risks;
- recommended next action.

Consensus is not verification. A failed or partial verifier result remains failed or partial in the proposal.

## Integration

1. Store case input, roster, handoffs, reports, challenges, verification, and synthesis as persistent Markdown artifacts when a full council is run.
2. Challenge every material recommendation at least once.
3. Convert only verified findings into audit items.
4. Put all proposed edits through the normal proposal/approval gate.
5. Never let expert output directly mutate the DOCX or repository.

## Responsible exit

If evidence is unavailable after bounded retries, stop the claim at `PARTIAL` or `BELUM TERVERIFIKASI`. Name the missing source, attempted checks, safest narrowed recommendation, and next verification step.
