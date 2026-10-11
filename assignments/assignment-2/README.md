# Assignment 2: Batch normalization in a detector

## Submitted notebook

[Open the assignment notebook](detection-instrumentation.ipynb)

The submission is a Jupyter notebook (`.ipynb`), exported from Colab with the implemented instrumentation, saved outputs and plots, and the two written answers. The student's downloaded notebook is preserved unchanged.

## Public Hugging Face results

**Hugging Face Space:** https://huggingface.co/spaces/pixle8/IntroAIAssignment2

The three CSV logs are available in the Space's [`runs/` folder](https://huggingface.co/spaces/pixle8/IntroAIAssignment2/tree/main/runs). The Space uses the static SDK; the files link provides direct access to the evidence independently of the dashboard frontend.

## Included run logs

The same logs are included here so the notebook's plotting cells can load them:

- [`runs/bn-seed0.csv`](runs/bn-seed0.csv): batch normalization, seed 0.
- [`runs/bn-seed1.csv`](runs/bn-seed1.csv): batch normalization, seed 1.
- [`runs/no-bn-seed0.csv`](runs/no-bn-seed0.csv): no batch normalization in the FPN and box head, seed 0.

Final validation AP after four epochs:

- BN seed 0: **0.1989123**.
- BN seed 1: **0.2050544**.
- No-BN seed 0: **0.1966507**.

## Reviewing the results

The notebook contains saved AP, activation-statistic, loss-spread, gradient-norm, and gradient-change plots. Part 3 contains the decisions and limitations discussed from the experiments.

For regenerating plots in Colab, upload the three CSV files into a `runs/` directory next to the notebook's working files, then execute the run-log/plotting definitions and the Part 2 plotting cells. The saved CSVs allow plots to be regenerated without rerunning training. A GPU runtime and the notebook's setup cells are needed if rerunning the training experiments.

Additional supporting figures are in [`figures/`](figures/). Smoothness summaries and these supporting figures use steps 500 onward (after learning-rate warmup).
