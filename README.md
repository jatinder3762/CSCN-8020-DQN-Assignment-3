# CSCN8020 Assignment 3 - DQN on PongDeterministic-v4

| Item | Value |
|---|---|
| Student Name | Jatinder Pal Singh |
| Student ID | 9083762 |
| Course | CSCN8020 Reinforcement Learning |
| Date | March 28, 2026 |
| Git Repository | https://github.com/jatinder3762/CSCN-8020-DQN-Assignment-3.git |

## Summary

This repository implements CSCN8020 Assignment 3 using an OOP Deep Q-Network (DQN) solution for Pong. The notebook uses the required `assignment3_utils.py` preprocessing helpers, stacks 4 grayscale frames as CNN input, includes experience replay and a target network, and compares the required hyperparameter settings.

Implemented requirements:
1. DQN agent with experience replay and target network.
2. Pong environment support for `PongDeterministic-v4`.
3. Fallback support for `ALE/Pong-v5` on modern Gymnasium installs when the legacy environment id is unavailable.
4. Frame preprocessing through `assignment3_utils.py`.
5. 4-frame state stacking as CNN input, without frame blending.
6. Default hyperparameters from the assignment:
   - Mini-batch size = 8
   - Target update = every 10 episodes
   - Gamma = 0.95
   - Epsilon init = 1.0
   - Epsilon decay = 0.995
   - Epsilon minimum = 0.05
7. Required plots against training steps:
   - Score per episode
   - Average cumulative reward of last 5 episodes
8. Required separate parameter studies:
   - Batch size comparison: 8 vs 16
   - Target update comparison: 3 vs 10 episodes

## Prerequisite Workshop

The week 6 prerequisite Multi-Armed Bandit workshop was completed first, and the supporting files used from that work are now also included in this repository so the full workflow is easy to explain and show in class.

Generated prerequisite results:
1. Stationary Casino total reward: `1862`
2. Non-stationary Casino total reward: `2557`

The class notes PDF (`6 - Exploration Strategies CA.pdf`) and assignment statement PDF (`CSCN8020_Assignment3.pdf`) are also included in this repository for completeness.

## Professor Files Used

These professor workshop files were added to this repository because they directly support how this assignment was prepared:

- `MultiArmedBandit_Workshop.ipynb`: introductory professor workshop notebook for basic epsilon-greedy bandits.
- `Casino_Challenge_MAB_Workshop.ipynb`: professor competition notebook used for the stationary and non-stationary casino rounds.
- `Professor_MAB_Workshop_README.md`: copied workshop README with the original learning goals and structure.
- `submissions_round1.csv`: generated stationary casino leaderboard output from the workshop notebook.
- `submissions_round2.csv`: generated non-stationary casino leaderboard output from the workshop notebook.

Why these matter for the DQN assignment:

1. The workshop notebooks helped me understand the exploration vs exploitation trade-off before training the DQN agent.
2. The generated CSV files show the actual output produced from those prerequisite exercises.
3. The DQN notebook then builds on that idea by using epsilon-greedy exploration during Pong training.
4. The professor-provided `assignment3_utils.py` file was used in the DQN notebook to preprocess Pong frames before they were sent into the CNN.

Simple class explanation:

- First, I used the professor bandit notebooks to learn why exploration is necessary.
- Then I generated `submissions_round1.csv` and `submissions_round2.csv` from those workshop runs.
- After that, I used the professor utility file `assignment3_utils.py` in my Pong notebook.
- Finally, I trained the DQN with replay memory, a target network, and the required hyperparameter comparisons.

## Main Files

- `CSCN8020_Assignment3_DQN_Pong.ipynb`: Main notebook (code + markdown + plots + observations).
- `assignment3_utils.py`: Professor-provided required helper utility for Pong preprocessing.
- `requirements.txt`: Reproducible dependency list.
- `JatinderPalSingh_9083762_DQN_Assignment3.pdf`: PDF report with assignment title, student details, and repo link.
- `6 - Exploration Strategies CA.pdf`: Week 6 class notes referenced by the assignment.
- `CSCN8020_Assignment3.pdf`: Assignment problem statement.
- `MultiArmedBandit_Workshop.ipynb`: Professor prerequisite bandit workshop notebook.
- `Casino_Challenge_MAB_Workshop.ipynb`: Professor casino challenge workshop notebook.
- `submissions_round1.csv`: Generated stationary casino result used to document prerequisite completion.
- `submissions_round2.csv`: Generated non-stationary casino result used to document prerequisite completion.
- `Professor_MAB_Workshop_README.md`: Supporting workshop description copied with the professor files.

## Deliverables Included In This Repository

This repository includes all required submission files for Assignment 3:
1. Jupyter notebook implementation: `CSCN8020_Assignment3_DQN_Pong.ipynb`
2. Required utility file: `assignment3_utils.py`
3. Reproducibility dependencies: `requirements.txt`
4. Required report PDF: `JatinderPalSingh_9083762_DQN_Assignment3.pdf`

The PDF is intentionally kept in this repo as part of the assignment deliverables.

## How To Run

1. (Recommended) Create and activate a virtual environment:

```bash
python -m venv .venv
```

Windows PowerShell:

```bash
.\.venv\Scripts\Activate.ps1
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

`CSCN8020_Assignment3_DQN_Pong.ipynb`

4. Run all cells from top to bottom.

Notes:
- For longer and stronger training, increase the episode count in the notebook.
- The notebook first tries `PongDeterministic-v4`. If that legacy id is not available, it falls back to `ALE/Pong-v5` with deterministic-style settings.
- The supported setup for this repo is a standard Python 3.10 to 3.12 virtual environment.
- `requirements.txt` now includes `AutoROM.accept-rom-license`, so ROM installation support is part of the environment setup.

## Best Hyperparameter Choice

From the required sweeps, the selected configuration is:
- Mini-batch size: 8
- Target update rate: every 10 episodes

Rationale: this configuration is more stable in early training and aligns with assignment defaults.

## Verified Execution Summary

The notebook was executed successfully in the repo's single `.venv` using CPU-only PyTorch. In this environment, the legacy `PongDeterministic-v4` id was unavailable, so the notebook used its fallback `ALE/Pong-v5` configuration.

Observed executed results:
1. Default run (`batch=8`, `target=10`): final score `-19`, best score `-18`, final average last 5 episodes `-20.0`, total steps `18,681`
2. Batch-size study: `batch=8` slightly outperformed `batch=16`
3. Target-update study: updating every `10` episodes slightly outperformed updating every `3` episodes
