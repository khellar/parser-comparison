# Template Parser and Parser Clerk: a shared learning report

A comparison of two complementary parsing pipelines, written to identify useful mechanisms, concrete failure modes, and improvements the team can make.

- [One-page scorecard (PDF)](parser-scorecard.pdf)
- [Scorecard in Markdown](scorecard.md)
- [Detailed comparison](comparison.md)
- [Recommendations for the manual and post-parsing pipeline](inheritance-recommendations.md)
- [Brief for the agent improving the manual](manual-agent-brief.md)
- [Selected examples and evidence boundaries](evidence-notes.md)

## Main result

On 24 selected conversations, Parser Clerk correctly retained **249/344 explicit-content points (72.4%)**, compared with **162/344 (47.1%)** for Template Parser. That is **25.3 percentage points higher**, or **53.7% more correctly retained point occurrences**. It is not an overall intelligence or reasoning score.

Template Parser supplied useful local successes in assumption scope, question background, uncertain references, modifier coverage, and an inspectable question-to-query path. An older, incomplete whole-platform study slightly favored Template Parser on eligible correct answers. The studies must remain separate.

## Scope and reproducibility

Evidence reviewed: 16 November 2026. New parsing study: Parser Clerk release 2.7.9/manual v10.6; Template Parser commit `24e37182e64a20981d423ed1d851da6de5e3b3e8`; same explicitly selected primary model, gpt-6.1-terra.

This repository contains the report, recommendations, and selected short examples. It does **not** contain the complete conversation archive, parser outputs, grading records, credentials, or internal coordination records. Consequently, the numerical results cannot be independently reproduced from this repository alone. Conclusions are bounded accordingly.

These are proposed improvements, not adopted manual changes or demonstrated fixes. The Template Parser maintainer has not reviewed or endorsed this report.

## Source repository

[Template Parser source](https://github.com/leungmanhin/semantic-parsing-hitl), with the [evaluated templates snapshot](https://github.com/leungmanhin/semantic-parsing-hitl/tree/24e37182e64a20981d423ed1d851da6de5e3b3e8/templates).

This report repository does not modify the Template Parser repository.

## License

The report documents are available under the [MIT License](LICENSE). Source projects retain their own licenses.
