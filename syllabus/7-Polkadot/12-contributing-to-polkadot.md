---
title: Contributing to the Polkadot SDK
description: PBA, Fellowship, Contributing guide
duration: 60 min
---

# Contributing to the Polkadot SDK

---

<img style="width: 1100px" src="assets/img/7-Polkadot/Contributing/intro.png" />
<!-- check size -->






---
## Overview
<pba-flex center>
- Synchronous vs asynchronous
- Why is asynchronous backing desirable?
<!-- .element: class="fragment" data-fragment-index="1" -->
- High level mechanisms of async backing
<!-- .element: class="fragment" data-fragment-index="2" -->
- The unincluded segment, and prospective parachains
<!-- .element: class="fragment" data-fragment-index="3" -->
- Async backing enabling other roadmap items
<!-- .element: class="fragment" data-fragment-index="4" -->
</pba-flex>
---
## Synchronous Backing Simplified
<img rounded style="width: 1000px" src="assets/shallow-dive-asynchronous-backing/synchronous_backing_simplified.svg" />
> How is this synchronous?
<!-- .element: class="fragment" data-fragment-index="1" -->
Notes:
- The dividing line between the left and right is when a candidate is backed on chain
- Approvals, disputes, and finality don't immediately gate the production of farther candidates.
  So we don't need to represent those steps in this model.
---
## Async Backing Simplified
<div class="r-stack">
<img rounded style="width: 1100px" src="assets/shallow-dive-asynchronous-backing/async_backing_simplified_1.svg" />
<img rounded style="width: 1100px" src="assets/shallow-dive-asynchronous-backing/async_backing_simplified_2.svg" />
<!-- .element: class="fragment" data-fragment-index="1" -->
<img rounded style="width: 1100px" src="assets/shallow-dive-asynchronous-backing/async_backing_simplified_3.svg" />
<!-- .element: class="fragment" data-fragment-index="2" -->
</div>
> How is this asynchronous?
<!-- .element: class="fragment" data-fragment-index="3" -->
Notes:
- Our cache of parablock candidates allows us to pause just before that dividing line, on-chain backing
- Why is backing asynchronous in this diagram?
---
## The Async Backing Optimistic Collator Assumptions
<pba-flex center>
1. "The best existing parablock I'm aware of will eventually be included in the relay chain."
1. "There won't be a chain reversion impacting that best parablock."
<!-- .element: class="fragment" data-fragment-index="1" -->
</pba-flex>
<br />
<br />
> The Stakes Are Low
<!-- .element: class="fragment" data-fragment-index="2" -->
Notes:
Best is determined by a process similar to the BABE fork choice rule.
Brief BABE fork choice rule review
---
