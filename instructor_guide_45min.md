# UCLA MSBA Lab: Instructor Guide

Files for the session:

- `tsfm_45min_zero_shot_eval_lab.ipynb`: main 45-minute lab
- `requirements_45min_optional_oss.txt`: optional open-source setup

## Session intent

This lab is not mainly about training a forecasting model. It is about teaching students how to reason about a forecasting system the way a practitioner would:

- understand what zero-shot transfer means
- evaluate model output against strong baselines
- distinguish numeric accuracy from explanation quality
- make a deployment judgment under uncertainty

## Suggested facilitation plan

1. Context and setup: 5 minutes
   - Define zero-shot forecasting.
   - Remind students that time-series evaluation must respect time order.
   - Tell them the goal is not to make the plot "look good"; the goal is to decide whether the system is trustworthy.

2. Zero-shot forecasting: 10-12 minutes
   - Have students run the forecasting section and inspect one forecast window.
   - Ask: "What pattern do you think the model is capturing?"
   - Ask: "What could break this forecast?"

3. Evaluation and baselines: 12-15 minutes
   - Make sure students inspect `score_df`.
   - Ask: "Did the model actually beat the baselines?"
   - Ask: "If the gain is small, is that enough to justify added complexity?"

4. Explanation quality and reflection: 8-10 minutes
   - Contrast the good and bad explanation examples.
   - Emphasize that a strong explanation does not prove strong numerical accuracy.
   - Ask students to make an explicit deploy / do not deploy recommendation.

## Good discussion prompts

- If the model barely beats the seasonal naive baseline, is it worth the added complexity?
- What is the cost of being wrong here: too much inventory, too few staff, or both?
- If the explanation scores highly but RMSE is poor, which signal matters more for deployment?
- What would you monitor after the first day of launch?

## Practical guidance

- If package setup is slow, skip directly to the evaluation outputs already produced in the notebook.
- If students finish early, ask them to tighten the deployment scorecard thresholds and defend them.
- If students get stuck on the business framing, redirect them to the central question: "Would you trust this system to influence a real decision?"
