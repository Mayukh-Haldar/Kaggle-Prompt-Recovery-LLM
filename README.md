# LLM Prompt Recovery with Gemma

<div align="center">
    <img src="https://i.ibb.co/8xZNc32/Gemma.png">
</div>

**The challenge:** Recover the LLM prompt used to rewrite a given text.

**KerasNLP Models:** [KerasNLP website](https://keras.io/api/keras_nlp/models/)

**About Gemma Models:** Gemma is a collection of advanced open LLMs developed by `Google DeepMind` and other `Google teams`, derived from the same research and technology behind the `Gemini models`.

| Parameters size | Tuned versions    | Intended platforms                 | Preset                 |
|-----------------|-------------------|------------------------------------|------------------------|
| 2B              | Pretrained        | Mobile devices and laptops         | `gemma_2b_en`          |
| 2B              | Instruction tuned | Mobile devices and laptops         | `gemma_instruct_2b_en` |
| 7B              | Pretrained        | Desktop computers and small servers| `gemma_7b_en`          |
| 7B              | Instruction tuned | Desktop computers and small servers| `gemma_instruct_7b_en` |

**Datasets:**
1) [Rewritten texts with Gemma 2B](https://www.kaggle.com/datasets/juanmerinobermejo/rewritten-texts-with-gemma-2b) | Credits: [Juan Merino](https://www.kaggle.com/juanmerinobermejo)

2) [gemma-rewrite-nbroad](https://www.kaggle.com/datasets/nbroad/gemma-rewrite-nbroad) | Credits: [Nicholas Broad](https://www.kaggle.com/nbroad)

3) [LLM Prompt Recovery - Synthetic Datastore](https://www.kaggle.com/datasets/dschettler8845/llm-prompt-recovery-synthetic-datastore) | Credits: [Darien Schettler](https://www.kaggle.com/dschettler8845)

4) [llm-prompt-recovery-data](https://www.kaggle.com/datasets/thedrcat/llm-prompt-recovery-data) | Credits: [Darek Kłeczek](https://www.kaggle.com/thedrcat)

5) [3000 Rewritten texts - Prompt recovery Challenge](https://www.kaggle.com/datasets/dipamc77/3000-rewritten-texts-prompt-recovery-challenge) | Credits: [Dipam Chakraborty](https://www.kaggle.com/dipamc77)


**Evaluation:** For each row in the submission and corresponding ground truth, [sentence-t5-base](https://www.kaggle.com/models/google/sentence-t5/frameworks/tensorFlow2/variations/st5-base) is used to calculate corresponding embedding vectors. The score for each predicted / expected pair is calculated using the [Sharpened Cosine Similarity](https://github.com/brohrer/sharpened-cosine-similarity), using an exponent of `3`. The SCS is used to attenuate the generous score given by embedding vectors for incorrect answers. Do not leave any `rewrite_prompt` blank as null answers will throw an error.

**Requirements:**
* CPU Notebook <= 9 hours run-time
* GPU Notebook <= 9 hours run-time
* Internet access disabled
* Freely & publicly available external data is allowed, including pre-trained models
* Submission file must be named submission.csv
* Submission runtimes have been slightly obfuscated. If you repeat the exact same submission you  will see up to 15 minutes of variance in the time before you receive your score.


*THIS NOTEBOOK IS BASED ON THE "Prompt Recovery with Gemma - KerasNLP Starter" NOTEBOOK! [LINK](https://www.kaggle.com/code/awsaf49/prompt-recovery-with-gemma-kerasnlp-starter)*

**Credits:** Awsaf (Owner); Ashley Chow (Editor); fchollet (Editor); Gusthema (Editor); Martin Görner (Editor); Paul Mooney (Editor); Phil Culliton (Editor).

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Dependencies](#dependencies)
- [Setup Modules & Dependencies](#setup-modules--dependencies)
- [Configuration](#configuration)
- [Reproducibility](#reproducibility)
- [Data Upload](#data-upload)
- [Prompt Engineering](#prompt-engineering)
- [Inference before Fine-Tuning](#inference-before-fine-tuning)
- [Fine-Tuning with LoRA](#fine-tuning-with-lora)
- [Inference after Fine-Tuning](#inference-after-fine-tuning)
- [Test Data](#test-data)
- [Submission](#submission)
- [Save the Custom Model](#save-the-custom-model)
- [Reference](#reference)
- [Solution Notebook](#solution-notebook)

## Overview
The goal of this competition was to recover the original prompt used by Gemma to rewrite given texts. This task involves natural language processing techniques and model training to predict the prompts accurately.

## Dataset
The dataset provided by Kaggle contains pairs of original and rewritten texts. The objective is to predict the prompt used for rewriting based on these pairs.

## Dependencies
The project utilized the following Python libraries:
- `numpy`
- `os`
- `keras`
- `keras_nlp`
- `pandas`
- `matplotlib`
- `seaborn`

You can install the dependencies using the following command:
```
pip install numpy pandas keras keras_nlp matplotlib seaborn
```

## Setup Modules & Dependencies
The first step involves setting up the necessary modules and dependencies required for the project.

## Configuration
Configuration of the environment and setting up necessary parameters for the project.

## Reproducibility
Ensuring that the experiments are reproducible by setting random seeds and fixing other variables.

## Data Upload
Uploading and preparing the data for analysis and modeling.

## Prompt Engineering
Designing and engineering the prompts based on the given texts to improve model performance.

## Inference before Fine-Tuning
Performing inference using the base model before applying any fine-tuning techniques.

## Fine-Tuning with LoRA
Applying LoRA (Low-Rank Adaptation) for fine-tuning the language model to better recover the prompts.

## Inference after Fine-Tuning
Performing inference after the model has been fine-tuned to evaluate improvements.

## Test Data
Preparing and using the test data for final evaluation.

## Submission
Creating the submission file to be evaluated on the Kaggle leaderboard.

## Save the Custom Model
Saving the trained and fine-tuned custom model for future use.

## Reference
Referencing the sources and materials used during the project.

## Solution Notebook
The detailed solution notebook, including all code and explanations, can be found at the following link:
[Link to my Notebook](https://www.kaggle.com/code/mayukhhaldar1/llm-prompt-recovery-final)

Feel free to explore the notebook for a comprehensive understanding of the approach and techniques used in this project.
