# Evaluating Pre-Trained Models Using TOPSIS for Text Classification

## Overview
This project leverages the TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) approach to evaluate and rank pre-trained NLP models for text classification. By analyzing multiple performance metrics, it aims to determine the most optimal model, balancing both accuracy and efficiency.

## Models Evaluated
The following **pre-trained models** are considered:
- **BERT**
- **XLNet**
- **RoBERTa**
- **ALBERT**
- **DistilBERT**

## Performance Metrics
The models are ranked based on the following metrics:
- **Accuracy (+)** - Higher is better
- **F1 Score (+)** - Higher is better
- **Precision (+)** - Higher is better
- **Recall (+)** - Higher is better
- **AUC-ROC (+)** - Higher is better
- **Log Loss (-)** - Lower is better
- **Perplexity (-)** - Lower is better

*(+ indicates a benefit criterion, - indicates a cost criterion)*

## Methodology
1. **Data Normalization**: Each metric is normalized using vector normalization.
2. **Weight Assignment**: Weights are assigned based on metric importance:
   - Accuracy: **25%**
   - F1 Score: **25%**
   - Precision: **10%**
   - Recall: **10%**
   - AUC-ROC: **10%**
   - Log Loss: **10%**
   - Perplexity: **10%**
3. **Ideal Best & Worst Values**:
   - The best and worst values for each metric are determined.
4. **TOPSIS Score Calculation**:
   - The Euclidean distance from ideal best and worst is calculated.
   - The TOPSIS score is computed using the formula:
     \[ S_i = \frac{D^-}{D^+ + D^-} \]
   - Models are ranked based on their scores.

## Results
The final **TOPSIS scores** and rankings are stored in `topsis_results.csv`. Below is the ranking visualization:

![TOPSIS Ranking](topsis_ranking.png)

## Conclusion
- **BERT** achieved the highest TOPSIS score, making it the best model for text classification in this comparison.
- **RoBERTa and XLNet** achieved high accuracy but fell slightly short than BERT.
- **DistilBERt** ranked lower due to lower precision and recall values.

This analysis helps in selecting the most **balanced** pre-trained model for text classification tasks.

---

