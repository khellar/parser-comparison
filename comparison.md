# Template Parser and Parser Clerk: comparative findings

**Evidence reviewed: 16 November 2026**

## Purpose and main findings

The comparison concerns two complementary team approaches. Template Parser interprets language through a construction catalog and then deterministically emits structured records for downstream consumers. Parser Clerk interprets language contextually under an ingress manual and admits checked records through an evidence-bearing Clerk.

Parser Clerk retained substantially more explicit meaning in the new conversation study. Template Parser demonstrated concrete local strengths in scope, reference uncertainty, modifier coverage, and query handling. Both pipelines support downstream symbolic reasoning.

Template Parser provides attribution and text provenance. The reviewed integration does not provide an equivalent to Clerk's integrated source-assessment and evidence-admission authority. This is an architectural difference, not proof that every Clerk judgment is well calibrated.

## Two studies, kept separate

| | New conversation study | Earlier whole-platform study |
|---|---|---|
| Purpose | Meaning retained in parsing | Answers obtained through each platform |
| Parser Clerk | Release 2.7.9, manual v10.6 | Release 2.7.3, manual v10.3 |
| Template Parser | Commit 24e37182e64a20981d423ed1d851da6de5e3b3e8; sentence walk | Same parser pin; author PeTTaChainer build 4aeefcd61023874ebc333b77b9b96c016c2ed524 |
| Coverage | 24 conversations, 57 turns | Incomplete: 233/315 scheduled case slots scored |
| Question-answer performance scored | No | Yes |

The explicitly selected primary model was gpt-6.1-terra in both comparisons. The new study supplied Parser Clerk with installed bounded conversation history and walked Template Parser sentence by sentence. Alternative manuals and whole-turn diagnostics are supplementary conditions, not additional principal systems.

## Parsing results

| Measure | Parser Clerk | Template Parser |
|---|---:|---:|
| Explicit content correctly retained | 249/344 (72.4%) | 162/344 (47.1%) |
| Qualified inference correctly retained | 6/91 (6.6%) | 5/91 (5.5%) |
| Safeguard violations, lower is better | 2/83 (2.4%) | 3/83 (3.6%) |

The explicit-content difference is 25.3 percentage points, or 53.7% more correctly retained point occurrences. It is not an overall performance score.

Qualified inference covers contextual conclusions that needed to remain qualified. Safeguards are prohibited readings checked for accidental assertion, scope leakage, or similar failures. The small differences in these two rows do not support strong comparative claims.

### Results by kind

Correctly retained explicit and qualified points combined:

| Kind | Parser Clerk | Template Parser |
|---|---:|---:|
| Plain facts and rules | 4/4 | 4/4 |
| Hedges and emphasis | 8/8 | 6/8 |
| One-step reports | 4/6 | 2/6 |
| Reported chains | 52/69 | 17/69 |
| Sarcasm and humour | 27/67 | 16/67 |
| Presupposition and insinuation | 31/87 | 13/87 |
| Requests | 10/10 | 10/10 |
| Identity and names | 15/19 | 16/19 |
| Corrections and temporal updates | 34/45 | 31/45 |
| Competing or dependent sources | 20/28 | 16/28 |
| Later revelations | 43/84 | 29/84 |
| Questions as information | 7/8 | 7/8 |

Each kind contains two conversations. The source mix was eight template-suite conversations, eight Parser Clerk-set conversations, and eight fresh conversations. Kind and source are confounded. These are engineering directions on selected material, not population rankings.

## Useful Template Parser successes

### An assumption remains an assumption

Source excerpt: "I shall assume my conscience is clear."

Template Parser represented a future assumption with the clear-conscience proposition sealed inside its content. Parser Clerk admitted a clear-conscience claim at parsed strength 0.700000, losing the distinct assumption.

A weak P and a strong claim that someone assumes P are different. Preserve the attitude and scope using existing forms where possible.

### Continuity survives inside a question

Source: "Are you still coming?"

Template Parser retained Still within the coming query. Parser Clerk retained the question but omitted the earlier plan or expectation.

Continuity information matters without establishing that attendance will occur.

### Branch-specific background stays in its branch

Source: "Have you still got my grey scarf, or did I leave that there last winter too?"

Template Parser retained Still and possession inside the first choice reading. Parser Clerk admitted earlier possession as an unconditional claim at parsed strength 0.900000.

Background licensed by one alternative should not automatically become unconditional evidence. Conversely, Template Parser sometimes failed to distinguish genuinely shared background from queried content, so simply enclosing everything in a query is not a complete solution.

### Reference uncertainty is localized

In a passage mentioning Jules, "He's put the familiar cardboard tunnel beside the carrier" received a separate pronoun-to-Jules Coref link with truth [0.8, 0.9] in Template Parser. Parser Clerk directly assigned Jules as agent with affirmative source evidence.

The useful distinction is between mention, candidate referent, and identity evidence. The numerical scales are not interchangeable.

### A modifier is retained

Source: "Tod, my new puppy, chewed the sofa."

Template Parser retained new; Parser Clerk omitted it without marking it uncovered. Template Parser also incorrectly linked the puppy to an earlier plumber named Tod. This is evidence for modifier coverage, not a correct whole parse or a general identity advantage.

## Useful Parser Clerk successes

### Broader contextual coverage

Source excerpts: "Our tickets are definitely for the matinee" and "I booked them myself."

Parser Clerk retained the matinee identification and its emphasis, and the speaker as the ticket-booking actor. Template Parser declared the matinee identification uncovered and retained a booking without the correct ticket patient.

A transparent finite catalog can still omit ordinary conversational meaning.

### Depiction scope

Source: "The instructions show two smiling people doing this together."

Parser Clerk kept the joint activity inside the illustration. Template Parser retained part of the depiction but separately asserted the activity outside that scope.

An event structure is not correct when placed in the wrong report, depiction, hypothetical, or attitude.

### Reported characterization

Source: "Mara called the new song 'a brave choice' after rehearsal."

Parser Clerk retained the reported characterization and timing. Template Parser declared that material uncovered.

### Explicit correction relationships

A later clarification identifying Nicole the human's mother as the Laura who loves horses corrected an earlier maternal reference.

Parser Clerk admitted amendments addressing the earlier reference and assignment. Template Parser declared the correction uncovered.

This demonstrates correction encoding, not complete proof that every dependent conclusion was revalued correctly.

## Architecture and capability matrix

| Capability | Template Parser | Parser Clerk |
|---|---|---|
| Context | Earlier sentences and parsed instances | Bounded installed history and held context |
| Structural checks | Catalog slots, spans, types, emission and lowering | Grammar, records and admission |
| Explicit uncovered content | Unmapped spans and findings | Some explicit outcomes; silent omissions also observed |
| Attitude/report scope | Structured, frequently sealed content | Structured reporting forms and source-bearing records |
| Linguistic commitment | Deterministic values from constructions and wording | Contextual parsed strength under the manual |
| Text provenance | Instance spans and statement links | Arrival and record provenance |
| Assessed source reliability and admission | Equivalent integrated layer not found in reviewed pipeline | Clerk provides the authority and record structure |
| Later reinterpretation | revision-needed findings; withdrawal bookkeeping unfinished | Revision/amendment mechanisms present |
| Symbolic reasoning | PeTTaChainer, generated rules, proofs and answers | Reasoning over admitted representations |
| Query path | Explicit literal queries and answer-variable bindings | Question representation and reasoning route; historical fidelity gap |
| Outcome-based accountability | Not demonstrated in reviewed integration | Relevant architecture exists; comparative live effectiveness unestablished |

"Not found" concerns this pinned integration, not every component or later development. Structural validity does not prove semantic fidelity.

## Oracle versus sensor

Template Parser assigns truth values, but its documented contract is sentence commitment, not world truth. After the model selects a reading and slots, the emitter assigns values using fixed rules.

Examples include individual facts at [1.0, 0.99], weak hedges at [0.9, 0.7], and unlikely at [0.1, 0.7]. An asserted universal can have strength 1.0 even when false.

The model still makes semantic judgments about constructions, classes, references, and scope. This is a linguistic sensor with a fixed commitment compiler, not a demonstrated world-truth oracle.

Non-factive beliefs, assumptions, and named attributions can keep P sealed inside content rather than independently asserting P. Read-only emitter checks confirmed that behavior for supplied catalog instances; those checks were not fresh model-driven English parses.

Factive constructions such as "knows that P" can also emit P at top level, reflecting linguistic presupposition. That is not independent world verification. A consumer needs to preserve the source and presupposition status at admission.

Three capabilities must remain distinct:

1. Attribution: who is reported to assert P?
2. Provenance: what words and transformation produced the record?
3. Accountability: whose assessed reliability and error history govern its evidential force and later revision?

Template Parser supplies useful attribution and provenance. Clerk supplies the relevant accountability machinery. The presence of that machinery does not prove calibration.

## Logical copulas

| Structure | Finding |
|---|---|
| Membership | Member emitted |
| Class inclusion | Inheritance emitted |
| Conditional implication | Implication emitted, including variable-dependent forms |
| Conjunction | And emitted |
| Identity | Same emitted, distinct from anaphoric Coref |
| Negation | Represented, with consumer and scope limits |
| Equivalence | Generated rules and inspected tests support both directions and denial propagation |
| General English iff parsing | Not established by equivalence-rule evidence alone |
| Disjunction | Declared in substrate; general executable inference not established by this review |
| Similarity | Proposed/opaque declaration; complete parse-to-reasoning capability not established |

Parser Clerk also has logical forms. Different names do not imply absent capability. Check English interpretation, emitted form, and executable inference separately.

## Earlier whole-platform results

| Scored outcome | Parser Clerk | Template Parser |
|---|---:|---:|
| Eligible correct | 88/413 (21.3%) | 96/413 (23.2%) |
| Eligible wrong | 3/413 | 5/413 |
| No eligible scored answer | 322/413 | 312/413 |

No eligible answer includes question-fidelity exclusions, not only engine silence.

| Diagnostic | Parser Clerk | Template Parser |
|---|---:|---:|
| Raw readable answers | 177/413 | 109/413 |
| Passing intended-query check | 91/413 | 101/413 |
| Raw answers excluded by query check | 86 | 8 |

A correct-looking answer to a different formal question cannot be credited to the intended question.

Template Parser correctly retrieved three parcels from a delivery statement where Parser Clerk did not produce an eligible quantity answer. Both pipelines proved a two-step class chain from vels through nors to puls. Both lacked an eligible explicit open answer for the unsupported zelmor question in that case.

The study was incomplete and used an older Parser Clerk release. It identifies a productive query-path repair, not a current general reasoning winner.

## Interpretation limits

- Twenty-four selected conversations, two per kind.
- Source and kind confounded; recurring point occurrences correlated.
- Graders could recognize representation styles.
- A second grader family differed on 15/96 sampled kept-or-lost decisions.
- Small differences are not reliable rankings.
- Alternative models may change behavior.
- Source implementation, local tests, admission, installation and live behavior are different evidence stages.
- Complete inputs, outputs and grading records are not included in this public report packet; independent numerical reproduction is not possible from this repository alone.
- No new model calls were made to prepare this report.

## Shared direction

Preserve broad contextual interpretation and Clerk's separation of parsing from epistemic authority. Inherit explicit scope, inspectable compilation, coverage receipts, source spans, positive and abstention examples, consumer capability declarations, and proof-preserving answers.

The next step is obvious paired probes and narrow repairs at the failing seam, followed by fresh evaluation.

Source: [Template Parser evaluated snapshot](https://github.com/leungmanhin/semantic-parsing-hitl/tree/24e37182e64a20981d423ed1d851da6de5e3b3e8/templates). See [evidence notes](evidence-notes.md) for further provenance and selected trace excerpts.
