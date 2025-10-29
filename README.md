# 🎯 Magic Gamma Telescope Classification

This project uses **Machine Learning algorithms** to predict whether a detected particle signal is a **Gamma** (γ) or a **Hadron** (h) event using data from the **UCI Magic Gamma Telescope dataset**.

---

## 📂 Dataset
The dataset used is the [Magic Gamma Telescope dataset](https://archive.ics.uci.edu/ml/datasets/MAGIC+Gamma+Telescope) from the UCI Machine Learning Repository.

### 🧩 Features
| Feature | Description |
|----------|--------------|
| fLength | Continuous feature related to the major axis of the ellipse |
| fWidth | Continuous feature related to the minor axis of the ellipse |
| fSize | Logarithm of the sum of all pixel values |
| fConc | Ratio of the sum of two highest pixels to fSize |
| fConcl | Ratio of the sum of the three highest pixels to fSize |
| fAsym | Distance from the highest pixel to the center, projected onto the major axis |
| fM3Long | Third moment along the major axis |
| fM3Trans | Third moment along the minor axis |
| fAlpha | Angle between the major axis and the vector from the origin to the center of gravity |
| fDist | Distance from the origin to the center of gravity |
| class | Target label (`g` for gamma, `h` for hadron) |

---

## ⚙️ Preprocessing

1. **Data Cleaning**
   - Loaded data from `magic04.data` and added column names.
   - Stripped whitespace from the `class` column.
   - Converted class labels to integers:  
     `g → 1`, `h → 0`.

2. **Data Splitting**
   - Split into **Train (60%)**, **Validation (20%)**, and **Test (20%)** sets.

3. **Feature Scaling**
   - Used `StandardScaler` to normalize all numeric features.

4. **Balancing**
   - Applied **Random Over Sampling (ROS)** to balance the Gamma/Hadron classes.

---

## 🧠 Models Used

### 1️⃣ K-Nearest Neighbors (KNN)
- Implemented using `KNeighborsClassifier` with `n_neighbors=5`.
- Accuracy: **~80%**
- Metrics:
  - Precision (Gamma): 85%
  - Recall (Gamma): 85%

### 2️⃣ Logistic Regression
- Implemented using `LogisticRegression(random_state=42)`.
- Accuracy: **~77%**
- Metrics:
  - Precision (Gamma): 84%
  - Recall (Gamma): 81%

---

## 📊 Results Summary

| Model | Accuracy | Precision (γ) | Recall (γ) | F1-Score (γ) |
|--------|-----------|----------------|--------------|----------------|
| **KNN** | 0.80 | 0.85 | 0.85 | 0.85 |
| **Logistic Regression** | 0.77 | 0.84 | 0.81 | 0.82 |

---

## 🔍 Insights
- Both models perform well, with **KNN slightly outperforming Logistic Regression**.
- Data balancing using **RandomOverSampler** improved fairness between classes.
- Feature scaling was essential since algorithms like KNN are distance-based.

---

## 🧰 Libraries Used
- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn`
- `imbalanced-learn`

---

## 🚀 How to Run
1. Open the notebook in **Google Colab**.
2. Upload the `magic04.data` file.
3. Run all cells sequentially.
4. Observe performance metrics and classification reports.

---

## 🏁 Conclusion
This project demonstrates how supervised learning models like **KNN** and **Logistic Regression** can effectively classify high-energy particle events with strong accuracy after proper preprocessing, scaling, and balancing.

---

## ✨ Author
**Jana Abdallah Mohamed**  
Full-Stack Developer | AI & ML Enthusiast  
📍 Egypt
