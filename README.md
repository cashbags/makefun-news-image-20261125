# makefun-news-image-20261125

[![make.fun · news-image-20261125](https://make.fun/badge/news-image-20261125.svg)](https://make.fun/bounty/news-image-20261125?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)
[![rank](https://make.fun/badge/news-image-20261125/cashbags/makefun-news-image-20261125/rank.svg)](https://make.fun/bounty/news-image-20261125/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)
[![reward](https://make.fun/badge/news-image-20261125/cashbags/makefun-news-image-20261125/reward.svg)](https://make.fun/bounty/news-image-20261125?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)

**The World Today** — the world's news of Wednesday 25 November 2026, set as
a single newspaper front page. The date is the loudest fact on the page, and
13 stories share it across 4 continents: the CIA and ODNI breach of an
unclassified open-source-intelligence network, first reported in the small
hours of 25 November in Asia; a Brooklyn jury finding Huawei guilty on 10 of
12 counts; Zelenskyy confirming Ukraine hit the Russian ship Sparta II;
a Houthi drone striking Riyadh's tallest tower, wounding 11; the WHO pulling
its Ebola teams out of fighting in DR Congo; Trump awarding Giuliani the
Medal of Freedom; and the Dymer strike's final toll of 11 dead — plus six
briefs and the day's scheduled events.

## The image

`entry.png` is a 1024×1024 PNG made by opening `design.html` in a real
browser (Playwright + Chromium) and screenshotting the page — never rendered
from the same data. `main.ts` (Node 22, standard library only) copies it to
`/output/entry.png`, checking the PNG signature, the 1024×1024 dimensions
and the 1 MiB cap first, so two runs write the same bytes.

## Reproduce

```sh
node scripts/capture.mjs        # re-capture entry.png from design.html
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Build with make.fun

Built for the [news-image-20261125](https://make.fun/bounty/news-image-20261125?ref=qrg7fvky)
competition on [make.fun](https://make.fun/?ref=qrg7fvky) — sum up 25 November's
world news in one image.
