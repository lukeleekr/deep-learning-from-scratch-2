# Ch01-01: Epoch, Batch, Learning Rate, and Sweep Design

## Why this matters

This is the first control layer of training quality. Before model architecture work, we must read and control:
- update frequency (`batch`)
- update size (`learning rate`)
- comparison fairness (`what is held constant`)

## Core definitions

- `Epoch`: one full pass over all training samples.
- `Batch size`: number of samples used in one parameter update.
- `Iteration` (or update step): one optimizer update from one batch.
- `Updates per epoch`: `dataset_size / batch_size`.
- `Learning rate (LR)`: step-size multiplier in gradient descent:
  - `new_param = old_param - lr * gradient`

## What we observed in Ch01

- Baseline (`lr=1.0`) showed stable downward training loss.
- High LR (`10.0`) showed strong oscillation and unstable path.
- LR sweep showed:
  - very low LR under-updates (slow/flat progress),
  - mid LR gives stable and efficient descent,
  - very high LR can look temporarily good but path volatility is high.
- Batch sweep showed:
  - smaller batches produced more updates per epoch and faster apparent progress.
  - this comparison is not fully fair unless total updates are fixed.

## Practical diagnosis rules

- If loss decreases smoothly: optimizer settings are likely functional.
- If loss oscillates widely: LR is likely too high (first suspect).
- If comparing batch sizes, do not use epochs alone as fairness anchor.
- Never claim model quality from training loss only; validation is required.

## Finance analogy

- LR is like position adjustment size per signal update:
  - too small: under-react to new information
  - too large: over-react and increase path risk
  - balanced: efficient adaptation with controlled instability

## Recall Questions

1. What is one epoch?
   - One full pass through all training samples.

2. Is `batch size` the total dataset size?
   - No. It is the number of samples per update step.

3. What is the formula for updates per epoch?
   - `dataset_size / batch_size`.

4. In SGD, where does LR enter the update?
   - `param -= lr * grad`.

5. Why is high LR risky even if final loss sometimes looks low?
   - It can cause unstable oscillation and poor convergence reliability.

6. Why is epoch-only comparison across batch sizes unfair?
   - Different batch sizes create different numbers of updates per epoch.

7. What must be checked before claiming model quality?
   - Validation/test behavior on unseen data, not only training loss.

