Sure! Below is the full `README.md` content. You can directly copy and paste it into your `README.md` file without modification:

````markdown
# 🏏 IPL Score Prediction Using Machine Learning

This project predicts the final score of an IPL (Indian Premier League) first innings using machine learning algorithms based on match progress.

---

## 📁 Dataset

- File: `ipl.csv`
- Shape: `(76014, 15)`
- Features include:
  - Teams (`bat_team`, `bowl_team`)
  - Runs, wickets, overs
  - Last 5 overs performance
  - Final score (`total`)

---

## 📊 Exploratory Data Analysis (EDA)

Performed:
- Inspection of data types and structure
- Previewed data with `df.head()`
- Identified unique teams and values
- Verified missing or inconsistent entries

---

## 🧹 Data Cleaning

Steps:
1. **Removed unwanted columns** like `batsman`, `bowler`, `venue`, etc.
2. **Filtered for consistent teams** (8 official IPL teams)
3. **Excluded first 5 overs** as they are unpredictable
4. **Converted date** column from string to datetime format

---

## 📈 Feature Engineering

- **One-Hot Encoding** applied on `bat_team` and `bowl_team`
- **Columns rearranged** for better alignment
- **Train-Test Split**:
  - **Train**: IPL 2008–2016
  - **Test**: IPL 2017

Removed `date` column post-splitting for model training.

---

## 🔥 Feature Correlation Heatmap

- Used `seaborn` to visualize correlation between numeric features.
- Helped identify redundant or weakly related features.

---

## 🤖 Model Building & Evaluation

### Models Tested:
- ✅ **Linear Regression**
- 🌲 **Decision Tree Regressor**
- 🌳 **Random Forest Regressor**
- 🚀 **AdaBoost Regressor** (with Linear Regression as base estimator)

### Evaluation Metrics:

| Model               | MAE     | MSE      | RMSE    |
|--------------------|---------|----------|---------|
| Linear Regression   | 12.12   | 251.00   | 15.84   |
| Decision Tree       | 17.09   | 531.05   | 23.04   |
| Random Forest       | 13.76   | 330.21   | 18.17   |
| AdaBoost (Linear)   | 12.21   | 249.60   | 15.79   |

✅ **Best Model Chosen**: **Linear Regression**

---

## 🧠 Prediction Function

A custom `predict_score()` function is defined to take match conditions and return predicted final score:

```python
final_score = predict_score(
    batting_team='Mumbai Indians',
    bowling_team='Kings XI Punjab',
    overs=14.1,
    runs=136,
    wickets=4,
    runs_in_prev_5=50,
    wickets_in_prev_5=0
)

print("Predicted Score Range: {} to {}".format(final_score - 10, final_score + 5))
````

---

## 🔮 Sample Predictions

| Match Date  | Teams                  | Actual Score | Predicted Score Range |
| ----------- | ---------------------- | ------------ | --------------------- |
| 16-Apr-2018 | KKR vs DD              | 200/9        | 159–174               |
| 07-May-2018 | SRH vs RCB             | 146/10       | 138–153               |
| 17-May-2018 | MI vs KXIP             | 186/8        | 180–195               |
| 30-Mar-2019 | MI vs KXIP             | 176/7        | 179–194               |
| 11-Apr-2019 | RR vs CSK              | 151/7        | 128–143               |
| 14-Apr-2019 | SRH vs DD              | 155/7        | 157–172               |
| 10-May-2019 | DD vs CSK (Eliminator) | 147/9        | 137–152               |

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**, **NumPy**
* **Matplotlib**, **Seaborn**
* **Scikit-learn** for ML modeling and evaluation

---

## 🏁 How to Run

1. Clone the repository:

```bash
git clone https://github.com/your-username/ipl-score-prediction.git
cd ipl-score-prediction
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the main script:

```bash
python main.py
```

---

## 📧 Contact

**Author**: Nitin Sharma
📬 Email: [sharmanitin.iitkgp@gmail.com](mailto:sharmanitin.iitkgp@gmail.com)

---

## 📌 Key Insights

* Early overs data is less reliable for prediction—excluding them improves performance.
* Simple models like Linear Regression perform surprisingly well.
* AdaBoost did not significantly outperform base models in this case.

---

## ✅ Final Note

The model is trained on IPL Seasons 2008–2016 and performs reasonably well on Season 2017 and beyond. Feel free to tweak hyperparameters or test with newer data.

Enjoy predicting IPL scores! 🎯

```

Let me know if you'd like this exported as a `.md` file or converted into a formatted PDF.
```
