# Task Proposals from Codebase Review

## 1) Typo fix task
**Issue:** The README subtitle contains two spelling mistakes: "coveying reccomendations".

**Evidence:** `README.md` line 2.

**Proposed task:**
- Update the README subtitle to: "Simple deployment for conveying recommendations".
- Keep tone and length similar to the original.

**Acceptance criteria:**
- The sentence in `README.md` has no spelling mistakes.
- Markdown renders correctly.

---

## 2) Bug fix task
**Issue:** The Google Maps link in the sidebar uses `target="_blank"` without `rel="noopener noreferrer"`, which enables reverse-tabnabbing and gives the opened page access to `window.opener`.

**Evidence:** `index.html` line 573.

**Proposed task:**
- Add `rel="noopener noreferrer"` to the Google Maps anchor tag.
- Verify the link still opens in a new tab.

**Acceptance criteria:**
- External link keeps `target="_blank"`.
- Link includes `rel="noopener noreferrer"`.
- Manual click test still opens Google Maps.

---

## 3) Code comment/documentation discrepancy task
**Issue:** The comment block labels coordinates as "VERIFIED COORDINATES (searched and confirmed online)", but multiple entries are marked `APPROXIMATE`, which contradicts the all-verified statement.

**Evidence:** `index.html` line 309 and entries at lines 368, 386, 403, 420, 437.

**Proposed task:**
- Rewrite the heading comment to reflect reality (for example: "Mix of verified and approximate coordinates").
- Optionally add a short note on how to upgrade `APPROXIMATE` entries to verified values.

**Acceptance criteria:**
- Top-level data comment is accurate.
- No contradiction remains between header comment and per-place coordinate annotations.

---

## 4) Test improvement task
**Issue:** There are no automated tests guarding the map’s core interactive behavior.

**Evidence:** Repository currently only contains `index.html` and `README.md` logic/docs, with no test files or test scripts.

**Proposed task:**
- Add a lightweight browser smoke test (e.g., Playwright) that:
  1. Loads the page.
  2. Clicks on the map twice and verifies a distance value appears.
  3. Clicks "Clear Pins" and verifies the distance display is removed.

**Acceptance criteria:**
- Test runs in CI/headless mode.
- Test fails if distance display does not appear after two clicks.
- Test fails if clear action does not remove distance display.
