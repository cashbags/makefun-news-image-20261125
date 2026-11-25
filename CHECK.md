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

## Kit check (run 25 Nov ~09:12 WIB, system node v24)

- Command: `node cli/makefun.mjs check --kit . --repo ../entry --transcripts ../transcripts.tar.gz`
- Result: **14 passed, 0 failed, 5 skipped, 5 checked at submission** — exit 0
- `thinking_reproduces`: **97.0%** authored (494 of 509 counted lines; 0 copied,
  0 pasted, 7 read, 8 absent; 1 kit starter line left out); entrypoint
  `main.ts` has 35 authored lines; 7 of 508 text lines unwritten (1.3%,
  limit 40%). Well above the 30% bar.
- `thinking_revised`: design.html takes its final content from 2 messages.
- `thinking_priced`: 1 usage record, priced to a known model (the parent
  session's row; this builder's own rows flush only when its run completes
  — re-attach in a live session before submitting; see below).
- `thinking_in_window`: all 177 timestamps inside the window.
- `thinking_own_work`: 0 lines from another entry's files, 0 from downloads.
- `transcripts_run_record`: pass — scheduled prompt, agent facts, system
  prompt uploaded, instruction files collected (1), no MCP.
- `snapshot`: 9 files, 295,595 bytes — within the intake caps (each file
  ≤ 100 MiB, repo ≤ 512 MiB). No tree-size failure: the 8,192-byte worry
  does not apply to this kit's check.
- `license_osi`: pass (MIT). `entrypoint`: main.ts, node22. `competition_open`: pass.
- At-submission checks (site-side, not run here): repo_public, repo_owner,
  repo_created_after_open, commit_in_repo, duplicate_snapshot. All are
  satisfied by construction: repo is public, owner cashbags = the account's
  GitHub login, created 2026-11-25T02:08:43Z (after the 00:00:00Z opening),
  and the submitted commit must be the **GitHub HEAD**
  `2543fcfc34614423b958f3abb60ed1fd36e0f77a` (verified via get-ref +
  ls-remote) — NOT the local commit fd85678b, which holds the same files
  but is not on GitHub (same pattern as news-image-20261120).
- Bundle: `transcripts.tar.gz`, 1,304,949 bytes,
  sha256 `bb660cc0574a428621bcd6507f3130752b0d6da0be584dfc1370e2bdcbd565d0`
  (prompt-origin scheduled, prompt file, harness muse-app,
  --mcp none, system prompt uploaded).
- Note: `gitleaks is not installed` (site also runs it) — no secrets are in
  the entry files.
