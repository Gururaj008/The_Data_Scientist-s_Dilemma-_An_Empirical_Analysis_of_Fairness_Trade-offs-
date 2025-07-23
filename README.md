# ⚖️ The Data Scientist's Dilemma: Fairness Trade-offs and Side-Effects in Bias Mitigation

<p align="center">
  <img src="https://img.shields.io/badge/Fairness-Aware-blue" />
  <img src="https://img.shields.io/badge/Paper-Published-brightgreen" />
  <img src="https://img.shields.io/badge/Python-3.9+-blue" />
  <img src="https://img.shields.io/badge/License-MIT-lightgrey" />
</p>

## 🔍 Overview

**Can fixing one kind of bias make another worse?**  
This repository explores the often-overlooked trade-offs in algorithmic fairness interventions. We present a large-scale empirical study comparing **pre-, in-, and post-processing** mitigation strategies across three real-world datasets and five machine learning models. Most importantly, we introduce **holistic evaluation tools** that reveal the *unintended side-effects* these interventions may cause.

📘 **Accompanying Paper**:  
> **The Data Scientist's Dilemma: An Empirical Analysis of Fairness Trade-offs and Unintended Mitigation Consequences**  
> Gururaj H C, Nithya A S, Dr. Vasudha Hegde  
> 📧 Contact: gururaj008@gmail.com

---

## 🧠 Key Contributions

- 📊 **Systematic Benchmarking** of 3 fairness paradigms (Reweighing, Exponentiated Gradient, Calibrated Equalized Odds)
- 🔀 **Model Diversity**: 5 models (LR, RF, GBM, SVM, MLP) on 3 datasets (Adult, COMPAS, German Credit)
- ⚠️ **Unintended Consequences**: Visualization tools (dumbbell plots, interaction heatmaps) to detect side-effects
- 🌐 **Intersectional Fairness**: Pre-processing that accounts for identity intersections like “Non-White Female”

---

## 📈 Datasets

We use 3 canonical fairness datasets:

| Dataset        | Task                      | Protected Attributes      |
|----------------|---------------------------|---------------------------|
| **Adult**      | Income > $50K             | Gender, Race, Age         |
| **COMPAS**     | Recidivism prediction     | Gender, Race, Age         |
| **German Credit** | Creditworthiness        | Gender, Age               |

---

## ⚙️ Mitigation Methods Compared

| Stage          | Technique                  | Library Used |
|----------------|----------------------------|--------------|
| **Pre**        | Reweighing (Single & Intersectional) | AIF360 |
| **In**         | Exponentiated Gradient     | Fairlearn    |
| **Post**       | Calibrated Equalized Odds  | Fairlearn    |

---

## 📉 Visual Insights

### ✅ Pareto Trade-offs
See how each method moves on the **accuracy ↔ fairness** frontier.

### 🧬 Dumbbell Plots
Quantify how each method changes fairness **across all attributes**, not just the target.

### 🌡️ Interaction Heatmaps
Diagnose **side-effects**—discover when fixing one bias unintentionally worsens another.

---

## 🔬 Sample Results

| Dataset        | Model | Mitigation                   | Accuracy | Gender_EOD | Race_EOD | Age_EOD |
|----------------|-------|------------------------------|----------|------------|----------|---------|
| Adult          | GBM   | Reweighing (Intersectional)  | 0.856    | 0.016      | 0.010    | 0.033   |
| COMPAS         | GBM   | Reweighing (Intersectional)  | 0.672    | 0.017      | 0.043    | 0.024   |
| German Credit  | GBM   | Reweighing (Age)             | 0.753    | 0.045      | N/A      | 0.026   |

📊 *Note: EOD = Equal Opportunity Difference (closer to 0 is fairer). Lower values indicate more equitable outcomes between protected groups.*

---

## 📊 Results Files

| File | Description |
|------|-------------|
| [`pivot_table_summary.csv`](./pivot_table_summary.csv) | Aggregated fairness and accuracy results across all models, datasets, and mitigation strategies. |
| [`full_results.csv`](./full_results.csv) | Full set of raw results for all combinations of model, dataset, and fairness method. Useful for detailed analysis or reproduction. |

---

## 🛠️ Tools Used

- [Fairlearn](https://fairlearn.org/)
- [AI Fairness 360](https://aif360.mybluemix.net/)
- [SHAP](https://github.com/slundberg/shap) for interpretability
- Scikit-learn, Matplotlib, Pandas, Seaborn

---

## 📜 Citation

If you use this work in your research, please cite:

```bibtex
@article{gururaj2025dilemma,
  title={The Data Scientist's Dilemma: An Empirical Analysis of Fairness Trade-offs and Unintended Mitigation Consequences},
  author={Gururaj H C and Nithya A S and Vasudha Hegde},
  journal={[H C, G. (2025). The Data Scientist's Dilemma: An Empirical Analysis of Fairness Trade-offs and Unintended Mitigation Consequences. Zenodo. https://doi.org/10.5281/zenodo.15959985]},
  year={2025}
}
```

---

## 🤝 Acknowledgements

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/)
- [ProPublica](https://www.propublica.org/) for the COMPAS dataset
- Inspiration from the fairness research community: [Hardt et al.], [Barocas et al.], and others.

---

## 📬 Contact

**Gururaj H C**  
📧 gururaj008@gmail.com  
💬 [LinkedIn](#)
