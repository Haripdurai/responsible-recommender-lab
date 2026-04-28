# Responsible Recommender Lab

This project is a hands-on lab on reducing harmful-content exposure in a movie recommender system without retraining the model.

## What This Lab Covers

- Measure baseline exposure of risky content in recommendations.
- Apply post-processing safety mitigations:
  - Filtering
  - Re-ranking by demotion
  - Penalty scoring
- Compare relevance-safety trade-offs using simple evaluation metrics.

## Dataset

The notebook uses the MovieLens small dataset.

- Source: GroupLens MovieLens
- Files are extracted into `ml-latest-small/`.

## Main Notebook

- `L6AIEng+M6T4+lab+outline+prompts+and+commentary.ipynb`

## Quick Start

1. Open the notebook in VS Code.
2. Run cells from top to bottom.
3. Review outputs for:
   - Baseline harmful exposure
   - Exposure after each mitigation
   - Mean score and rank displacement comparisons

## Mitigations Implemented

1. Post-processing filter
- Removes all items labeled harmful before ranking.

2. Re-ranking by demotion
- Multiplies scores by label-based factors.
- Example idea: harmful gets stronger demotion than borderline.

3. Penalty scoring
- Subtracts a fixed penalty by label from each item's score.

## Key Metrics

- Harmful exposure (%): Share of harmful items in top recommendations.
- Borderline exposure (%): Share of borderline items in top recommendations.
- Top-N mean score: Average relevance score of the top N items.
- Rank displacement: How much ranking positions changed from baseline.

## Why This Matters

This lab demonstrates practical trust and safety controls that can be deployed quickly in production ranking pipelines when retraining is not immediately possible.

## Repository Structure

- `L6AIEng+M6T4+lab+just+data.ipynb`
- `L6AIEng+M6T4+lab+outline+prompts+and+commentary.ipynb`
- `ml-latest-small/`

## Notes

- Content risk labels in this lab are synthetic and policy-driven for learning purposes.
- Results should be interpreted as methodology practice, not real-world policy outcomes.
