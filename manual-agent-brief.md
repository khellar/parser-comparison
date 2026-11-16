# Brief for the agent improving the Parser Clerk manual

## Objective

Use the attached comparison to make targeted, evidence-backed improvements to the current ingress manual. Treat Template Parser and Parser Clerk as complementary team contributions.

Read the current manual and consumer contracts before editing. The measured baseline was release 2.7.9/manual v10.6; later versions may already repair these cases. Do not overwrite newer behavior or assume a historical failure is still present.

## Start here

1. Read [inheritance recommendations](inheritance-recommendations.md).
2. Review the paired cases in [evidence notes](evidence-notes.md).
3. Reproduce the relevant failure with the current manual before choosing a repair.
4. Reuse existing logical forms, identity alternatives, reporting forms, and coverage mechanisms wherever adequate.

## Highest-value manual targets

- Preserve an assumption or attitude involving P instead of substituting a weaker standalone P.
- Keep question background attached to the reading or alternative that licenses it.
- Preserve meaningful continuity words and modifiers; disclose important omissions.
- Keep uncertain reference choices inspectable through existing candidate/rival mechanisms.
- Preserve the distinction between source commitment and evidence for world truth.

## Changes that a manual alone cannot prove

Query compilation, downstream consumer support, premise retrieval, proof reading, correction propagation, source reliability assessment, and duplicate evidence handling require producer-to-consumer tests. Name the failing seam rather than adding instructions that the consumer cannot honor.

## Acceptance

For every proposed manual change, provide:

- The prior behavior on a current build.
- One positive case and one close negative control.
- The interpretation and representation that must survive.
- A downstream query or revision check where relevant.
- The new result, including regressions or remaining gaps.

A test must distinguish the repair from the earlier failure. Do not claim success solely because output is structurally valid.

## Boundaries

These documents are proposals and evaluation findings, not authority to change truth policy or introduce a new grammar. Respect the destination project's current ownership and release process.

Do not copy fixed Template Parser STV numbers into Clerk's epistemic policy. Do not flatten reports, assumptions, directives, or depictions into direct facts. Do not turn the comparison into a general ranking or a claim that one pipeline lacks all reasoning.

Use system names throughout. No changes or submissions to the Template Parser repository are requested.
