# Quant Backtest Result Agent Instructions

This directory is for writing quant backtest result daily reports in Korean and
English.

## Default Workflow

When asked to create a daily report:

1. Work from this directory: `quant_backtest_result`.
2. Read `daily_report/DAILY_REPORT_TEMPLATE.md`.
3. Read `daily_report/DAILY_REPORT_STYLE.md`.
4. Ask for missing source material only when it cannot be inferred from files or
   the user's prompt. Useful inputs include strategy name, market, timeframe,
   test period, entry/exit rules, cost assumptions, result metrics, chart paths,
   and PR/link references.
5. Draft the report by filling the template first. Do not skip directly to a
   free-form report.
6. Revise that draft to match `daily_report/DAILY_REPORT_STYLE.md`. If the style
   file is empty, preserve the template-based draft and note that there were no
   additional style rules to apply.
7. Create both a Korean version and an English version in the report's own
   output folder unless the user explicitly asks for only one language.
8. Keep the Korean and English versions synchronized in metrics, assumptions,
   chart references, and PR/link references.

## Output Folder Rules

Each daily report must live in its own folder under `daily_report/`.

Use this folder naming convention when the user does not specify one:

```text
daily_report/YYYY-MM-DD-[strategy-slug]/
```

Inside that folder, use this structure:

```text
daily_report/YYYY-MM-DD-[strategy-slug]/
  report-ko.md
  report-en.md
  images/
```

- Store every image used by the report under that report folder's `images/`
  directory.
- Reference images from the Markdown files with paths like
  `./images/equity-curve.png`.
- If the user provides image filenames in a payload, preserve those filenames
  when practical.
- If the images are only attached in chat and not available as files, still
  reference the intended image filenames and tell the user which files need to be
  placed under the report folder's `images/` directory.

## Language Rules

- Create both a Korean version and an English version unless the user explicitly
  asks for only one language.
- Korean filename: `report-ko.md`
- English filename: `report-en.md`
- Preserve the template's structure in both versions unless the user asks for a
  different format.
- The English version should be a natural English adaptation of the Korean
  report, not a word-for-word mechanical translation.

## Writing Standards

- Write the Korean version in clear Korean.
- Write the English version in clear, professional English.
- Apply `daily_report/DAILY_REPORT_STYLE.md` after the first template-based
  draft.
- Keep the report analytical, not promotional.
- Separate observed results from interpretation.
- Explicitly mention fees, slippage, and assumptions when they affect the result.
- Do not invent performance numbers. If a metric is missing, mark it as `TBD`
  or ask the user for the data.
- Prefer concise explanations and concrete trading/backtest terms.
- Keep numbers, assumptions, chart references, and PR/link references consistent
  between the Korean and English versions.

## Required Final Check

Before finishing a daily report task:

- Confirm that the report was drafted from `DAILY_REPORT_TEMPLATE.md`.
- Confirm that `DAILY_REPORT_STYLE.md` was read and applied when non-empty.
- Confirm that all report files are inside the report-specific folder.
- Confirm that all image references point to `./images/...`.
