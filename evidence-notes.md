# Selected evidence and interpretation boundaries

## Source versions

New conversation study:
- Parser Clerk release 2.7.9, source cf1db12, ingress manual v10.6.
- Template Parser commit 24e37182e64a20981d423ed1d851da6de5e3b3e8, sentence-by-sentence primary condition.
- Explicitly selected primary model: gpt-6.1-terra.
- 24 conversations, 57 turns; eight template-suite, eight Parser Clerk-set, eight fresh.

Earlier incomplete whole-platform study:
- Parser Clerk release 2.7.3, e09e1763fda50c9f4767f680d2b757cf17190dd2, manual v10.3.
- Same Template Parser pin.
- Author PeTTaChainer build 4aeefcd61023874ebc333b77b9b96c016c2ed524.
- 233 of 315 scheduled case slots scored; 413 question opportunities in completed cases.

These historical evaluations are distinct. No fresh model call or paid inference was made for this report.

## Selected trace excerpts

The identifiers below locate point judgments in the archived evaluation. They are not independent repeated trials. The public packet does not include the full archive.

### F2-1-message-3 / p005: assumption

Source excerpt: "I shall assume my conscience is clear".

Parser Clerk retained:
```
(clear-conscience khellar)
parsed_strength: 0.700000
```

Template Parser retained an assume event, its experiencer, future tense, and:
```
(Theme sk_assume_1 (Member sk_conscience_1 clear))
```

The embedded clear-conscience proposition was not independently asserted. The lesson concerns attitude structure, not numerical comparison of truth scales.

### F2-1-message-4 / p002: question continuity

Source: "Are you still coming?"

Template Parser query:
```
(And
  (Member $come_1 come)
  (Agent $come_1 $you_1)
  (Ongoing $come_1)
  (Still $come_1))
```

Parser Clerk's admitted question omitted the earlier expectation conveyed by still.

### E2-1-message-4 / p004: branch scope

Source: "Have you still got my grey scarf, or did I leave that there last winter too?"

Template Parser kept Still and Holder in the first choice reading. Parser Clerk admitted an earlier-possession claim outside that branch at parsed strength 0.900000.

This is a local success, not a claim that all question presuppositions are handled correctly.

### D2-1-message-1 / p007: reference uncertainty

Source context mentions Jules, followed by "He's put the familiar cardboard tunnel beside the carrier."

Template Parser:
```
(Coref sk_he_1 sk_jules_1)
truth: [0.8, 0.9]
```

Parser Clerk named Jules as agent with affirmative source evidence. Reuse the separation of reference uncertainty; do not equate the numerical scales.

### H1-1-message-2 / p003: modifier coverage

Source: "Tod, my new puppy, chewed the sofa."

Template Parser:
```
(Member sk_tod_2 (Narrow puppy (Member new)))
```

Parser Clerk omitted new without declaring the qualification uncovered. Template Parser also incorrectly joined the puppy to an earlier plumber Tod. This does not support a claim of whole-parse correctness.

### E1-1-message-2 / p001: depiction scope

Source: "The instructions show two smiling people doing this together."

Parser Clerk retained the joint activity within the depicted illustration. Template Parser separately asserted the joint activity outside that scope.

### I2-1-message-5 / p001: correction encoding

A later clarification identifies Nicole the human's mother as the Laura who loves horses, correcting an earlier maternal reference.

Parser Clerk admitted explicit revisions. Template Parser declared the correction uncovered. Descendant revaluation was not established merely by this point judgment.

### Earlier whole-platform examples

g5-005: Template Parser retrieved 3 for a question about how many parcels Jezora delivered. Parser Clerk did not produce an eligible quantity answer.

g4-019: Both pipelines answered yes to Guneth being a puls from vels -> nors -> puls and Guneth being a vels. Neither provided an eligible explicit open answer for the unsupported zelmor query.

## Primary implementation references

Pinned source: [Template Parser templates](https://github.com/leungmanhin/semantic-parsing-hitl/tree/24e37182e64a20981d423ed1d851da6de5e3b3e8/templates)

- README.md: commitment semantics, spans, emission and consumer separation.
- catalog/attitude.yaml: sealed non-factive content and factive projection.
- catalog/mention.yaml: mention/reference separation.
- catalog/imperative.yaml: requested acts sealed from actual events.
- tmpl/emit.py: deterministic truth assignment from selected instances.
- tmpl/blocks.py: prefix availability, questions, revision-needed and unfinished withdrawal bookkeeping.
- tmpl/query.py: literal query compilation.
- tmpl/answers.py: bindings and proof-preserving answer grouping.
- tmpl/reason.py: resolved view and staged closure workarounds.
- tmpl/lower.py and tmpl/rules.py: consumer-specific support and generated rules.
- tests/test_rules_engine.py: equivalence and other engine closure tests. Inspection of a test is not a claim that this report reran the engine suite.

## Numerical verification

Explicit-content percentages:
- 249 / 344 * 100 = 72.3837%.
- 162 / 344 * 100 = 47.0930%.
- Difference = 25.2907 percentage points.
- Relative retained-count increase = (249 - 162) / 162 * 100 = 53.7037%.

Qualified inference: 6/91 and 5/91. Safeguard violations: 2/83 and 3/83. Small differences are inconclusive.

Earlier eligible correct answers: 88/413 and 96/413. No eligible answer can include a question-fidelity failure; it is not synonymous with silence.

## Evidence states

- Numeric results: reported from the archived evaluation; counts were rechecked locally, not recollected.
- Selected paired examples: source/output/judgment excerpts inspected.
- Architectural findings: bounded to the pinned implementation reviewed.
- Recommendations: inferences and proposed acceptance conditions, not demonstrated repairs.
- Current live behavior or broad superiority: not established.
- Source reliability calibration and complete revision propagation: need direct tests.
- Complete independent reproduction from this packet: unavailable because the full underlying records are not included.

The report is a learning aid. It must not be used as evidence that its suggested fixes are already implemented.
