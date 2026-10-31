# Production — Playtest Plan

*Tidewrack — Fogline Games · design doc · last updated 2026-05-22 · production, playtest*

## Approach
Rolling rounds (PR1–PR9) with a small tester group, led by Isla Bergsdottir, starting the week the slice
ships. Each round's headline issue feeds a fix commit; the rest are logged as minor/polish. The full log is
`playtests/feedback_log.csv`; the headline bugs (input-eat, save corruption, choice-timing, the invisible
flag bug, 1080p overflow) all became real fixes before the demo build.

## Build labels in `playtests/feedback_log.csv`
- `v0.1-vslice` — vertical slice playtests around/after 2026-05-15.
- `demo-wip` — internal demo-candidate builds (June–July) while packing toward the public Next Fest `v0.2-demo-rc` (mid-Aug). Not the public store demo yet.

