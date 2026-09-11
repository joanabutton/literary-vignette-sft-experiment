# Literary Vignette SFT Experiment

An academic supervised fine-tuning (SFT) experiment that transforms short factual scene descriptions into atmospheric literary vignettes.

This project was created for the **Deep Learning** course in the **Executive Masters in Business Analytics and AI** at **Porto Business School**. Course instructor: **Andre Santana**.

## Objective

The experiment tests whether SFT can make a model more consistent at rewriting plain scene notes as 60-100 word literary vignettes while preserving source facts. The target behaviour requires atmospheric detail, indirect emotional implication, a restrained literary register, and no major invented plot details.

## Contents

- `final_challenge_sft_platform_guide.ipynb` - experiment guide, Platform evidence log, training-target audit, and held-out evaluation.
- `data/literary_vignette_train.jsonl` - 10 synthetic, manually reviewed training examples.
- `data/literary_vignette_validation.jsonl` - 10 synthetic, manually reviewed validation examples.
- `data/literary_vignette_test.jsonl` - 10 held-out synthetic test examples; this file was not uploaded to the fine-tuning job.

## Experiment design

The same system message and generation settings were used for the base model and the selected fine-tuned checkpoint. Each held-out output was manually scored from 0 to 5 using five binary criteria:

1. Meaning preserved
2. Atmosphere present
3. Emotion implied
4. Literary register
5. Output discipline

The maximum score per model was 50 across the 10 held-out prompts.

## Result

In this small experiment, the base model and the selected fine-tuned checkpoint each scored **33/50**. The training-target audit scored the 10 gold-standard training answers **49/50**, suggesting that the main limitation was the small amount and coverage of training data rather than weak target writing.

This is a course experiment, not a production writing tool. Results should be interpreted cautiously because the dataset is synthetic and contains only 10 examples per split.

## Reproducibility and ethics

The JSONL examples were synthetically created with ChatGPT assistance and manually reviewed. No personal, confidential, or client data is included. The notebook documents the Platform-only workflow; it does not contain API keys or make API calls.

## Acknowledgement

Prepared for academic coursework at Porto Business School. This repository is not an official Porto Business School or OpenAI publication.
