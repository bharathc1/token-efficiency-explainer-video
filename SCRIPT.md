# SCRIPT — token-efficiency-explainer

**Voice:** Kokoro (local) am_michael
**Voice direction:** Calm, precise, engineer-to-engineer. Each line hands off to the next.

---

## Line 1 — Hook (Frame 1)

**Time:** 0.0 – 10.0s
**Delivery:** Level and confident; land the number, leave the question open.

    Our agents write as much as before, but read sixty-eight percent fewer tokens. The savings came from how the harness moves context.

## Line 2 — What a turn costs (Frame 2)

**Time:** 10.0 – 20.0s
**Delivery:** Plain, factual.

    A turn is many model calls, and each one re-sends context. Spend per turn fell from three sixty-six to one twenty-two.

## Line 3 — Where it went (Frame 3)

**Time:** 20.0 – 30.0s
**Delivery:** Explanatory, end on the question.

    Most of the drop was cache writes, down seventy-nine percent. A write only pays if something reads it again, so who reuses what?

## Line 4 — Fix 1 (Frame 4)

**Time:** 30.0 – 42.0s
**Delivery:** Teacherly.

    One: order the prompt by who reuses it. Six planner paths now share an identical system prompt, so downstream agents read the router's cache with zero writes.

## Line 5 — Fix 2 (Frame 5)

**Time:** 42.0 – 54.0s
**Delivery:** Steady.

    Two: scope what each worker sees. The planner reads the whole five-hundred-thousand-character persona document, then passes workers only the definitions they need.

## Line 6 — Fix 3 (Frame 6)

**Time:** 54.0 – 64.0s
**Delivery:** A touch of dry surprise on the forty-four.

    Three: match recovery to the failure. One message burned forty-four calls retrying SQL while the Query Runner was down.

## Line 7 — Back to the number (Frame 7)

**Time:** 64.0 – 74.0s
**Delivery:** Resolved, slower.

    Reuse the prefix, scope the context, fit the recovery. Output unchanged, sixty-eight percent fewer tokens. Make it observable.
