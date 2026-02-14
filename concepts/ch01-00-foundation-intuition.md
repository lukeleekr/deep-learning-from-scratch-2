# Chapter 1: Foundation Intuition (Before Code)

## 1) Why this chapter matters for COSMOS

Before COSMOS can reason over large text corpora reliably, we need to understand how a model turns input numbers into useful outputs and improves over time. This chapter is the foundation for:

- Building reliable training loops
- Reading learning curves to detect underfitting/overfitting issues
- Trusting or overriding model outputs in investment workflows

## 2) Core concepts (beginner first)

### Model (what we train)
A **model** is a parameterized function that maps input to output. Inputs are converted to numbers, and parameters control the mapping.

### Loss (what we minimize)
**Loss** measures how wrong the model is for a specific example. Lower loss means better fit.

### Gradient (how learning signal moves)
A **gradient** tells us the direction each parameter should move to reduce loss.

### Optimizer (the parameter update rule)
An **optimizer** uses the gradient to update parameters step-by-step.

### Training loop (the repeatable process)
1. Predict
2. Compare with target (loss)
3. Compute gradient
4. Update parameters
5. Repeat

## 3) Finance framing

In COSMOS, this loop is the machinery behind any learning-based component:
- Embedding layer quality for finance news retrieval
- News-to-evidence ranking quality
- Language-to-argument generation for investment memos

## 4) What to remember this week

- We are not asking for perfect math first.
- We are building a working mental model:
  - Why parameters move
  - Why accuracy/loss curve shapes matter
  - Why bad curves indicate wrong data, model, or objective

## 5) Recall Questions

1. In one sentence, what is a model doing?
   - A model is a function with trainable parameters that maps inputs to outputs.

2. Why does a model need loss?
   - Loss gives a measurable target for improvement.

3. What does the gradient indicate?
   - Which direction to change parameters to reduce loss.

4. Why do we repeat the training loop many times?
   - Single updates are noisy; repeated updates gradually converge to a better mapping.

5. Why is a stable training loop useful for investment tooling?
   - It makes model behavior auditable and improvable, not a black box.
