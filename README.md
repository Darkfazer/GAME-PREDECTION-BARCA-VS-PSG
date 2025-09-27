# ⚽ Champions League Match Predictor: Barcelona vs PSG

A machine learning model that predicts match outcomes for UEFA Champions League fixtures using ELO ratings and team form data.

## 📊 Project Overview

This project implements a machine learning model (Logistic Regression) to predict outcome probabilities for UEFA Champions League matches, specifically focusing on FC Barcelona vs Paris Saint-Germain when played at Barcelona's home stadium.

The model combines the ELO rating system with historical match analysis to generate accurate predictions.

## 🏗️ Methodology & Model

### Data Sources
- `EloRatings.csv`: Historical and current ELO ratings for top football clubs
- `Matches.csv`: Historical match results, scores, ELO ratings, and team form data

### Feature Engineering
The model uses two key features to quantify team strength:

| Feature | Calculation | Rationale |
|---------|-------------|-----------|
| **ELO Difference** | `(Home_Elo + 100) - Away_Elo` | Primary strength metric with +100 home advantage bonus |
| **Form Difference** | `Home_Team_Form(L5) - Away_Team_Form(L5)` | Recent performance momentum |

### Machine Learning Model
- **Algorithm**: Logistic Regression (Binary Classifier)
- **Target**: `P(Home Win)` vs `P(Not Home Win)`
- **Accuracy**: 62.82% on test data
- **3-Way Split**: `P(Not Home Win)` is divided into Draw/Away Win using historical ratios (48.84% of non-home wins are draws)

## 📈 Prediction Results

**Match**: Barcelona vs Paris SG (Home Game for Barcelona)  
**ELO Ratings**: Barcelona = 1945.43, PSG = 1974.94

| Outcome | Team | Probability |
|---------|------|-------------|
| 🏠 Home Win | Barcelona | 53.56% |
| ⚖️ Draw | Draw | 22.68% |
| ✈️ Away Win | Paris SG | 23.76% |

**Conclusion**: The model predicts a home victory for Barcelona.

## 🚀 Future Enhancements

- **Separate Draw Model**: Train dedicated Logistic Regression for draw outcomes
- **Betting Odds Integration**: Incorporate external betting odds data
- **Time Decay**: Weight recent results more heavily in ELO calculations
- **Advanced Features**: Include player injuries, head-to-head history, and tactical formations

## 🛠️ Installation & Usage

### Prerequisites
```bash
pip install pandas numpy scikit-learn matplotlib
