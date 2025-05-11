# 💳 Fraud Detection System

This project is a machine learning-based **Fraud Detection System** that identifies potentially fraudulent financial transactions. It includes data preprocessing, exploratory data analysis, feature engineering, multiple classification models, model evaluation, and deployment using Streamlit.

---

## 📂 Project Structure

- `Fraud_Analysis_Dataset.csv`: Input transaction dataset.
- `fraud_detection.py` / `.ipynb`: Main notebook/script with preprocessing, modeling, and evaluation.
- `app.py`: Streamlit web app for deployment.
- `fraud_detection_model.pkl`: Serialized logistic regression model used in deployment.

---

## 📊 Dataset Description

The dataset contains simulated transaction data with the following attributes:

| Column | Description |
|--------|-------------|
| step | Time step (1 step = 1 hour) |
| type | Type of transaction (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER) |
| amount | Transaction amount |
| nameOrig/nameDest | Sender/Receiver (dropped) |
| oldbalanceOrg/newbalanceOrig | Sender's balance before/after |
| oldbalanceDest/newbalanceDest | Receiver's balance before/after |
| isFraud | Target variable (1 = Fraud, 0 = Legitimate) |

---

## ⚙️ Technologies Used

- Python (Pandas, NumPy, Matplotlib, Seaborn, scikit-learn)
- Imbalanced-learn (`RandomUnderSampler`)
- Streamlit (for app deployment)
- Pickle (for model serialization)

---

## 📈 Exploratory Data Analysis (EDA)

- Visualized transaction types and fraud distribution
- Observed that fraud mostly occurs in `TRANSFER` and `CASH-OUT`
- Noted correlation between balances and fraud
- Feature engineering for fraud probability scoring

---

## 🛠️ Feature Engineering

- `balanceOrigDiff`: `oldbalanceOrg - newbalanceOrig`
- `balanceDestDiff`: `oldbalanceDest - newbalanceDest`
- `amount_to_orig_balance_ratio`
- `amount_to_dest_balance_ratio`
- `fraud_risk_score`

---

## 🤖 Models Trained

| Model | Accuracy | Notes |
|-------|----------|-------|
| Logistic Regression | 92.12% | Final selected model |
| Random Forest | 99.56% | Overfitting |
| Gradient Boosting | 99.34% | Overfitting |
| Support Vector Machine | 80.52% | Underperformed |
| K-Nearest Neighbors | 92.77% | Not used in final deployment |

**Final Model:** Logistic Regression (after GridSearchCV tuning)

---

## ⚖️ Class Imbalance Handling

Used **Random Under Sampling** to balance `isFraud` (since fraudulent transactions were heavily underrepresented).

---

## 🚀 Deployment

- Deployed using **Streamlit**
- Web interface takes input features and predicts fraud
- Includes styling and interactivity for a user-friendly experience

---

## 📦 Installation

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
pip install -r requirements.txt
streamlit run app.py
```

---

## 📸 Screenshots (Optional)

*Add screenshots or a demo video link here to showcase your Streamlit app.*

---

## 👨‍💻 Author

**Ravi Sakharkar**  
Supervised by: *Dr. Mahendra Gourisaria*

---

## 📜 License

This project is licensed under the MIT License.
