# UCLA MSBA Time-Series Foundation Model Lab

Files:

- `tsfm_foundation_eval_lab.ipynb`: main hands-on notebook
- `tsfm_45min_zero_shot_eval_lab.ipynb`: 45-minute seminar version (zero-shot + eval + LLM-as-judge)
- `requirements.txt`: minimal local dependencies
- `requirements_45min_optional_oss.txt`: optional OSS deps for Chronos + local judge paths

What this lab teaches:

- Foundation-model workflow for time series: pretrain, zero-shot, few-shot, fine-tune
- Proper time-series evaluation: temporal splits, rolling-origin backtests
- Metrics: MAE, RMSE, sMAPE, MASE
- Why baseline comparisons matter
- Why fine-tuning does not automatically improve results

45-minute version focus:

- Zero-shot forecasting workflow (Chronos path if available; offline fallback if not)
- Metrics + baselines + comparison discipline
- LLM-as-judge for explanation quality (Ollama path if available; fallback heuristic if not)
- Reflection on deployment readiness and monitoring
- Includes a 30-minute student exercise: The Bruins Cold Brew Challenge

Run locally:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook tsfm_foundation_eval_lab.ipynb
```

Notes:

- The core notebook is CPU-friendly and runs with `numpy` + `pandas`.
- `matplotlib` is optional (plots are skipped if unavailable).
- The notebook includes an optional section to plug in a real TSFM (Chronos/TimesFM) while reusing the same evaluation harness.


Standalone challenge files:

- `bruins_cold_brew_challenge.ipynb`: student-facing forecasting challenge
- `data/bruins_cold_brew_demand.csv`: dedicated dataset for the challenge
- `bruins_cold_brew_challenge_solution.ipynb`: notebook-based solution grounded in the challenge outputs
