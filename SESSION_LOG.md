# Deep Learning Study Session Log

This file records each study session for accountability, recall practice, and iteration history.
## Session: 2026-02-14 13:16:07 KST
- Repository: /Users/lukelee/Study/deep-learning-from-scratch-2/repo
- User language: English
- Study mode: Beginner-first, concept-first
- Action requested: Start study plan and keep session log + concepts
- Log policy: Append every session with topics, concepts covered, outcomes, next steps
 - Q/A: User guessed 'data quality'. Confirmed as first diagnostic priority in most cases; follow-up checks = labels, objective/loss mismatch, then model/optimizer issues.
 - Next concept emphasis: how to distinguish data noise from label noise vs objective mismatch before changing architecture.
 

- Q/A: When model performs badly, choose **1 (data quality) first** as the default diagnosis path. If data is clean and aligned, then check **loss/objective mismatch (2)**.

## Session: 2026-02-18 15:03:34 KST
- Repository: /Users/lukelee/Study/deep-learning-from-scratch-2/repo
- User language: English
- Time log (today): Start ~14:28 KST | End 15:03 KST | Duration ~35 minutes
- Topics covered:
- Ch01 baseline run: `train.py` and `train_custom_loop.py`
- NumPy compatibility fix for modern Python/NumPy: `np.int` -> `int` in `dataset/spiral.py`
- Loss curve interpretation: early fast descent, later diminishing returns
- Core terms: `epoch`, `batch size`, `iterations/updates per epoch`
- LR sweep executed: `0.01, 0.1, 1.0, 3.0, 10.0`
- Batch sweep executed: `5, 10, 30, 100` (with fixed LR)
- What we learned today:
- `epoch` is one full pass over all samples.
- `batch size` is samples per update step, not total dataset size.
- `updates per epoch = dataset_size / batch_size`.
- LR controls update step size (`param -= lr * grad`), and too high LR causes unstable oscillation.
- Sweep means changing one variable across multiple values while holding others fixed.
- Key concepts repeatedly confused (watchlist):
- Difference between `batch size` and `updates per epoch`.
- Fair comparison rule: do not compare only by epochs when update counts differ.
- Training loss alone is insufficient; validation is required for generalization claims.
- Resume point for next session:
- Finish Ch01 with `validation split` + `fixed-total-update` fair comparison, then move to Ch02.
