# Template Parser and Parser Clerk: simple scorecard

**Evidence reviewed: 16 November 2026**

Parser Clerk scored **72.4% versus 47.1%** on explicit meaning retained correctly: **25.3 percentage points higher**, equivalent to **53.7% more correctly retained content-point occurrences**.

| What matters | Parser Clerk | Template Parser | Simple reading |
|---|---:|---:|---|
| Explicit meaning retained correctly | **72.4% - 249/344** | 47.1% - 162/344 | Clear Parser Clerk advantage on these conversations |
| Qualified inference retained correctly | 6.6% - 6/91 | 5.5% - 5/91 | Both weak; difference too small for a strong conclusion |
| Safeguard violations - lower is better | 2.4% - 2/83 | 3.6% - 3/83 | Slight numerical advantage for Parser Clerk; inconclusive |
| Correct downstream answers in the older, incomplete study | 21.3% - 88/413 | **23.2% - 96/413** | Template Parser slightly ahead; a current comparison is needed |
| Accountable source assessment and belief settlement | Present through Clerk | Not found in reviewed integration | Architecture difference; effectiveness needs direct testing |
| Logical structure and downstream reasoning | Present | Present | Both support these |

**Learn from Template Parser:** preserve assumptions as assumptions, keep question background in scope, localize reference uncertainty, and inspect the connection between a question and its executable query.

**Preserve in Parser Clerk:** broad conversational interpretation, contextual reports and corrections, and the separation between reading a claim and deciding how much to believe it.

## Read the numbers correctly

The new parsing study used 24 selected conversations and 57 turns, Parser Clerk 2.7.9/manual v10.6, and Template Parser's sentence-by-sentence mode. The 53.7% improvement applies only to explicit-content retention. Point occurrences recur across intermediate and final views and are correlated.

The downstream-answer row is a different, older, incomplete study using Parser Clerk 2.7.3/manual v10.3. A correct answer was credited only when its formal query matched the intended question. The row must not be combined with the new parsing scores.

Qualified inference means contextual conclusions that needed to remain qualified. Safeguards are prohibited interpretations checked for accidental assertion, scope leakage, or comparable errors; these are not a broad safety score.

Full details: [comparison](comparison.md) and [evidence boundaries](evidence-notes.md).
