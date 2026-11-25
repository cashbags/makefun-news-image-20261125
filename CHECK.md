# Check record — news-image-20261125

Entry: "The World Today" — Wednesday 25 November 2026, 13 stories, 4 continents.
Repo: https://github.com/cashbags/makefun-news-image-20261125 (to be created after opening; verified 404 on GitHub at ~09:00 WIB 25 Nov).

## Capture (real browser only)

- Command: `node scripts/capture.mjs` (Playwright + Chromium, headless)
- Result: `entry.png` 1024x1024, 265,472 bytes (limit 1,048,576), PNG signature OK
- sha256: `c961a21f7e25ff48e019ac183dfb6fa6d8cddf0e2ea0a422f6058c776be4726a`
- Viewed at full size and at 300 px: masthead, date line, lead headline and
  all six story headlines still read at 300 px; all 6 briefs, the scheduled
  strip and the footer fit inside the 1024x1024 frame (first capture ran
  long and was cut off mid-strip; layout was tightened and re-captured).

## Determinism (two runs of main.ts)

- `MAKEFUN_OUTPUT_DIR=/tmp/run1 node main.ts` -> sha256 c961a21f7e25ff48e019ac183dfb6fa6d8cddf0e2ea0a422f6058c776be4726a
- `MAKEFUN_OUTPUT_DIR=/tmp/run2 node main.ts` -> sha256 c961a21f7e25ff48e019ac183dfb6fa6d8cddf0e2ea0a422f6058c776be4726a
- `cmp` identical; both match `entry.png` in the repo. Byte-identical.

## Tree

- Submitted files: main.ts, entry.png, design.html, scripts/capture.mjs,
  README.md, DESIGN.md, LICENSE (CHECK.md kept in the repo too).
- Tree bytes (7 files, excl. CHECK.md): 293,775 — entry.png dominates
  (265,472). The 20261117 entry shipped a 231,849-byte entry.png and passed
  its kit check, so the tree cap is read from the kit check's own report,
  not assumed from 8,192.
- `node_modules/` + `package.json` / `package-lock.json` (Playwright for
  the capture script) are build tools only and are NOT committed.

## Kit check

(To be filled after the bundle + kit check run.)
