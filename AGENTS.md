# Workspace Routing Instructions

When the user says they want to create a "quant backtest result daily report",
or uses a close Korean/English variant such as:

- "quant backtest result daily report 만들고 싶어"
- "퀀트 백테스트 결과 데일리 리포트 만들어줘"
- "backtest daily report 작성"

route the task to `quant_backtest_result`.

For that request:

1. Change the working directory to `quant_backtest_result`.
2. Read `AGENTS.md` in that directory before doing any work.
3. Follow the local report workflow and use `daily_report/DAILY_REPORT_TEMPLATE.md`
   as the source template unless the user provides a more specific template.
4. Keep generated daily-report files inside `quant_backtest_result/daily_report`
   unless the local `AGENTS.md` says otherwise.

