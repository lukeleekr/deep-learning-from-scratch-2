# Deep Learning from Scratch 2 Study Materials

## Scope
You are starting from zero in Deep Learning and your long-term direction is COSMOS (Finance AI System Architect). This plan combines:
- This repo chapters (ch01~ch08)
- README lecture and data resources
- finance-oriented examples each week

## Resources from README (priority)

- Deep Learning I lecture page: https://sites.google.com/site/kyunghoonhan/deep-learning-i
- Deep Learning II lecture page: https://sites.google.com/site/kyunghoonhan/deep-learning-ii
- Deep Learning III lecture page: https://sites.google.com/site/kyunghoonhan/deep-learning-iii
- YouTube playlist I: https://www.youtube.com/watch?v=8Gpa_pdHrPE&list=PLBiQZMT3oSxW1RS1hn2jWBgswh0nlcgQZ
- YouTube playlist II: https://www.youtube.com/watch?v=5fwD1p9ymx8&list=PLBiQZMT3oSxXNGcmAwI7vzh2LzwcwJpxU
- YouTube playlist III: https://www.youtube.com/watch?v=kIobK76on3s&list=PLBiQZMT3oSxV3RxoFgNcUNV4R7AlvUMDx
- Equations+figures archive: https://github.com/WegraLee/deep-learning-from-scratch-2/raw/refs/heads/master/equations_and_figures_2.zip
- pretrained weights (ch06/7 style checks): https://www.oreilly.co.jp/pub/9784873118369/BetterRnnlm.pkl
- Errata: https://docs.google.com/document/d/1pzeh5nrP6y6A5WgT9vvxMpe-ai7ZRhU84BdAhdJzuFk/edit?usp=sharing

## Extra resources I recommend (high signal)

- `deep-learning-from-scratch-1` first volume (`github.com/oreilly-japan/deep-learning-from-scratch`) for intuition on gradients and backprop.
- The NumPy stack doc pages you already use (NumPy, Matplotlib).
- A finance framing notebook (I will prepare as exercises): sentiment extraction, macro-event topic clustering, and sequence anomaly checks.

## 8-Session Foundation Sequence (recommended)

### Session 1 — Big picture + Ch 1
- Target: Understand model, loss, gradient, training loop
- Read: `ch01/train.py`, `ch01/two_layer_net.py`
- Lecture: Start with 1 playlist from Deep Learning I and watch first 1–2 foundational lectures.
- Hands-on: run a tiny experiment by changing learning rate and batch size only.
- Finance link: How would a tiny prediction model react to noisy FX labels?

### Session 2 — Dataset representation + similarity
- Target: Vocabulary, corpus statistics, embedding intuition
- Read: `ch02/count_method_*.py`, `ch02/similarity.py`
- Lecture: continue Deep Learning I
- Hands-on: build and inspect a toy dataset of ticker symbols + keywords.
- Finance link: Build a mini co-occurrence table for company names in a short news snippet set.

### Session 3 — Word2Vec core
- Target: CBOW / Skip-gram training objective
- Read: `ch03/simple_cbow.py`, `ch03/simple_skip_gram.py`, `ch03/train.py`
- Lecture: use relevant DL I segments on NLP basics.
- Hands-on: run tiny vocab training and observe nearest-neighbor behavior.
- Finance link: words as symbols: why close embeddings can connect "yield curve", "duration", "liquidity".

### Session 4 — Negative sampling + performance tuning
- Target: why negative sampling works and speed tradeoffs
- Read: `ch04/cbow.py`, `ch04/skip_gram.py`, `ch04/negative_sampling_layer.py`
- Lecture: DL I (mid-late)
- Hands-on: compare full softmax vs negative sampling loss curves on same toy set.
- Finance link: portfolio of entities and sector context; where semantic neighbors can help discovery.

### Session 5 — Intro sequence modeling
- Target: RNN state, backprop through time idea, sequence loss
- Read: `ch05/simple_rnnlm.py`, `ch05/train.py`
- Lecture: begin Deep Learning II playlist
- Hands-on: train short next-word model on small text and inspect prediction drift.
- Finance link: macro sentence completion for risk notes (sanity test, not production).

### Session 6 — Stabilized RNNLM
- Target: gradient clipping, better RNNLM architecture
- Read: `ch06/better_rnnlm.py`, `ch06/train_better_rnnlm.py`, `ch06/clip_grads.py`
- Lecture: Deep Learning II (architecture + training stability)
- Hands-on: compare with/without clipping on same seed.
- Finance link: detect overreactive training behavior from sparse high-volatility tokens.

### Session 7 — Seq2seq core
- Target: encoder-decoder and teacher forcing intuition
- Read: `ch07/seq2seq.py`, `ch07/train_seq2seq.py`, `ch07/show_addition_dataset.py`
- Lecture: Deep Learning III
- Hands-on: create a tiny arithmetic-like mapping task and trace sequence boundaries.
- Finance link: map structured news headline template to short normalized action statements.

### Session 8 — Attention and interpretation
- Target: attention mechanism and interpretability
- Read: `ch08/attention_seq2seq.py`, `ch08/attention_layer.py`, `ch08/visualize_attention.py`
- Lecture: finish DL III key sequences.
- Hands-on: inspect attention heatmaps and explain in plain terms.
- Finance link: what words drove a recommendation in a sample earnings commentary.

## Study cadence template

- 90 minutes / session (recommended max)
- 10 minutes: recall (from last concept note)
- 40 minutes: concept + lecture
- 30 minutes: code run + tiny modification
- 10 minutes: finance mapping and notes

## Concept-note rule

After each session, create/update a note in:
`/Users/lukelee/Study/deep-learning-from-scratch-2/repo/concepts/`
with 5–10 recall Q&A points only.

## Tracking worksheet columns

For each session track:
1. What I thought (one line)
2. What failed and why
3. Which lecture/video helped the most
4. One finance-use case idea
5. Next action

## Starting point for today

If you are ready, we begin with Session 1:
- open `ch01/train.py`
- run it once
- pause and map every loss shape to either data quality, objective mismatch, or model capacity.
