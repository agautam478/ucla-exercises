# UCLA MSBA Time-Series Foundation Model Lab

Files:

- `tsfm_foundation_eval_lab.ipynb`: custom foundation model hands-on notebook
- `tsfm_chronos_eval_lab.ipynb`: Using OSS foundation model (zero-shot + eval + LLM-as-judge)
- `requirements.txt`: minimal local dependencies

What this lab teaches:

- Foundation-model workflow for time series: pretrain, zero-shot, few-shot, fine-tune
- Proper time-series evaluation: temporal splits, rolling-origin backtests
- Metrics: MAE, RMSE, sMAPE, MASE
- Why baseline comparisons matter
- Why fine-tuning does not automatically improve results

OSS usage focus:

- Zero-shot forecasting workflow (Chronos path if available; offline fallback if not)
- Metrics + baselines + comparison discipline
- LLM-as-judge for explanation quality (Ollama path if available; fallback heuristic if not)
- Reflection on deployment readiness and monitoring
- Includes a 30-minute student exercise (embedded in the Chronos lab): The Bruins Cold Brew Challenge

Run locally:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook tsfm_foundation_eval_lab.ipynb
```

For the OSS zero-shot + eval + LLM-as-judge path, open **`tsfm_chronos_eval_lab.ipynb`** instead.

Notes:

- The core notebook is CPU-friendly and runs with `numpy` + `pandas`.
- `matplotlib` is optional (plots are skipped if unavailable).
- The Chronos notebook includes an optional section to plug in a real TSFM (Chronos/TimesFM) while reusing the same evaluation harness.

---

## Standalone challenge: Bruins Cold Brew

- **`bruins_cold_brew_challenge.ipynb`** — Standalone student-facing forecasting challenge (30 min).
- **`bruins_cold_brew_demand.csv`** — Dataset for the challenge (daily demand + context variables: date, avg_temp_c, rain_mm, campus_event, promo_flag, exam_period, holiday_break, is_weekend, cups_sold, split).

### Exercise objectives

Students will:

1. Run a **zero-shot forecast** using a foundation-model style forecaster.
2. Compare it against **strong baselines** (e.g. naive, seasonal).
3. **Tune or calibrate** the forecast using recent validation data.
4. Re-evaluate on a held-out test period.
5. Make a **deployment recommendation** (whether the workflow is trustworthy for staffing and inventory).
