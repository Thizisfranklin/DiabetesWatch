# DiabetesWatch

An exploratory classification project using the Pima Indians Diabetes dataset to compare ways of identifying positive cases from clinical measurements.

| Model | Accuracy | Recall |
|---|---:|---:|
| Decision tree | 0.695 | 0.259 |
| Random forest | 0.734 | **0.519** |
| K-nearest neighbors (k=8) | **0.747** | 0.500 |

*Results reported in the original analysis. Recall matters when the aim is to find more positive cases.*

## Approach

The project examines disguised missing values recorded as zeros, adds missingness indicators and two engineered features, then compares decision trees, random forests, and KNN. See the [notebook](Lab7_Osualaaham.ipynb) for exploration and plots.

`diabetes_classification.py` runs a separate experimental workflow and writes `model_performance.json`:

```bash
pip install pandas numpy scikit-learn
python diabetes_classification.py
```

The included `diabetes.csv` is read from the repository root.

**Limitations:** The script computes imputation medians before splitting and chooses KNN's k using test performance; its test metrics are therefore optimistic. This dataset represents a narrow population. These results are for learning and should not be used for clinical decisions.
