# CSCN8020 Assignment 3 - DQN on PongDeterministic-v4

| Item | Value |
|---|---|
| Student Name | Jatinder Pal Singh |
| Student ID | 9083762 |
| Course | CSCN8020 Reinforcement Learning |
| Date | March 28, 2026 |
| Git Repository | https://github.com/jatinder3762/DQN_Assignment3.git |

## Summary

This repository implements Assignment 3 (DQN) for PongDeterministic-v4 using OOP Python and the required helper utility file `assignment3_utils.py`.

Implemented requirements:
1. DQN agent with experience replay and target network.
2. PongDeterministic-v4 environment usage.
3. Frame preprocessing through `assignment3_utils.py`.
4. 4-frame state stacking as CNN input (no frame blending).
5. Default hyperparameters from assignment:
   - Mini-batch size = 8
   - Target update = every 10 episodes
   - Gamma = 0.95
   - Epsilon init = 1.0
   - Epsilon decay = 0.995
   - Epsilon minimum = 0.05
6. Required plots against training steps:
   - Score per episode
   - Average cumulative reward of last 5 episodes
7. Required separate parameter studies:
   - Batch size comparison: 8 vs 16
   - Target update comparison: 3 vs 10 episodes

## Main Files

- `CSCN8020_Assignment3_DQN_Pong.ipynb`: Main notebook (code + markdown + plots + observations).
- `assignment3_utils.py`: Required helper utility for preprocessing.
- `requirements.txt`: Reproducible dependency list.
- `CSCN8020_Assignment3_Report.pdf`: PDF report with assignment title, student details, and repo link.

## Deliverables Included In This Repository

This repository includes all required submission files for Assignment 3:
1. Jupyter notebook implementation: `CSCN8020_Assignment3_DQN_Pong.ipynb`
2. Required utility file: `assignment3_utils.py`
3. Reproducibility dependencies: `requirements.txt`
4. Required report PDF: `CSCN8020_Assignment3_Report.pdf`

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
- For long, stronger training, increase episode count in the notebook.
- Atari environments can require extra install steps for ROM support depending on platform.

## Best Hyperparameter Choice

From the required sweeps, the selected configuration is:
- Mini-batch size: 8
- Target update rate: every 10 episodes

Rationale: this configuration is more stable in early training and aligns with assignment defaults.
