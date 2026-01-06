# Cora Node Classification Challenge

## Overview
Predict research topics of academic papers in the Cora citation network. Node classification with 80% training data and 20% held-out test set.

## Task
- Nodes: 2,708 papers
- Edges: 5,429 citations  
- Features: 1,433 bag-of-words
- Classes: 7 research topics
- Train: 2,166 nodes (80%), Test: 542 nodes (20%)

## Dataset

| File | Description |
|------|-------------|
| data/nodes.csv | Node features (node_id + 1433 features) |
| data/edges.csv | Edge list (source, target) |
| data/train.csv | Training data (node_id, features, target) |
| data/test.csv | Test data (node_id, features) |
| submissions/sample_submission.csv | Submission format example |

## Evaluation
Macro F1-Score - treats all 7 classes equally.

## Rules
- Must use GNN methods (GCN, GAT, GraphSAGE, etc.)
- Any framework allowed (DGL, PyG, etc.)
- No external data or pretrained embeddings
- No using test labels
- Inference under 60 seconds

## Repository Structure

```
gnn-challenge/
├── data/
│   ├── nodes.csv
│   ├── edges.csv
│   ├── train.csv
│   └── test.csv
├── submissions/
│   └── sample_submission.csv
├── starter_code/
│   ├── baseline.py
│   ├── prepare_data.py
│   └── requirements.txt
├── README.md
├── scoring_script.py
├── update_leaderboard.py
└── LICENSE
```

## Getting Started

```bash
pip install -r starter_code/requirements.txt
cd starter_code
python prepare_data.py  # Downloads Cora and creates train/test split
python baseline.py      # Trains GCN and generates submission
```

## Submission Format

CSV with two columns:
```csv
node_id,target
0,3
5,1
12,6
```

## How to Submit

1. Fork this repository
2. Clone your fork locally
3. Run your model and save predictions to `submissions/your_team_name.csv`
4. Commit and push to your fork
5. Create a Pull Request
6. GitHub Actions will automatically score and update the leaderboard

## Leaderboard

See [leaderboard.md](leaderboard.md)

| Rank | Team | Macro F1 | Method |
|------|------|----------|--------|
| 1 | Baseline | 0.8763 | 2-layer GCN |
