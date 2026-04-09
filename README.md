## 🚢 Titanic Survival Predictor: A Journey from 58% to 83%

Welcome to my Titanic survival project! This repository contains my implementation of a binary classification pipeline that predicts whether a passenger survived the Titanic shipwreck based on features like age, class, and social status.

## 🚀 The Story of the Project
When I first started this project, I thought I could just throw data at an algorithm and get a perfect score. I quickly learned that **Machine Learning is 20% model selection and 80% data preparation.** Initially, my Support Vector Machine (SVM) was failing with a **58% accuracy**—barely better than a random guess. By the end of this journey, after mastering **Feature Engineering** and **Standard Scaling**, I pushed the performance up to **83.14%**.

---

## 🛠️ What’s Inside?

### 1. Data Cleaning & The "Title" Trick
Raw data is messy. I handled missing values for `Age` and `Embarked`, but the real breakthrough came from the `Name` column.
* **Feature Engineering:** I extracted titles (Mr, Mrs, Master, etc.). This allowed the model to "see" that a "Master" (young boy) had a much higher survival priority than an adult "Mr," even if their other stats were similar.
* **Dropping Noise:** I removed `PassengerId` and `Ticket` numbers to prevent the model from memorizing random patterns.

### 2. The Great Scaling Lesson
This was my biggest "Aha!" moment. I realized that distance-based models like **SVM** and **KNN** were being "blinded" by the large numbers in the `Fare` column.
* **Standardization:** I applied `StandardScaler` to ensure every feature had a mean of 0 and a variance of 1. 
* **The Result:** My SVM score jumped from **58.66% to 83.24%** instantly.

### 3. The Model Tournament
I didn't just pick one model; I held a competition between several architectures:
* **Random Forest (The Champion):** After tuning hyperparameters with `GridSearchCV`, this model became my most stable performer at **83.14%**.
* **SVM (The Runner-Up):** Extremely powerful once scaled.
* **Neural Networks (MLP):** A great learning experience, though it tended to "over-think" (overfit) on this specific small dataset.

---

## 📊 Final Performance Leaderboard

| Model | Accuracy | Note |
| :--- | :--- | :--- |
| **Random Forest** | **83.14%** | **Winner:** Robust and interpretable. |
| **SVM (Scaled)** | **83.24%** | Excellent geometric separation. |
| **Logistic Regression** | **78.80%** | Solid linear baseline. |
| **Naive Bayes** | **77.09%** | Fast, but the "independence" assumption was too simple. |
| **Neural Network** | **78.21%** | A bit of overkill for 891 rows. |

---

## 🧠 Key Takeaways
1. Scale Matters: If you don't scale your data, your SVM is basically guessing.
2. Domain Knowledge Wins: Creating the `Title` feature was more impactful than switching from one complex model to another.
3. Simplicity is Often Better: On smaller datasets, a well-tuned Random Forest often beats a complex Neural Network.


💻 How to Run This
1. Clone this repo.
2. Install dependencies: `pip install -r requirements.txt`.
3. Open `Titanic_Final_Notebook.ipynb` and run all cells.


📬 Connect with Me
If you have questions about my feature engineering or why I chose certain hyperparameters, feel free to open an issue or reach out!

reyaan9900@gamil.com
`![Feature Importance](./images/feature_importance.png)`

This makes your GitHub page look incredibly professional! Ready to push this to the world?
