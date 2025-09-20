
# Demo-1: Machine Learning Fundamentals



---

### 🔹 Setup

* Use **Anaconda** (isolates each project).
* Use **Jupyter Notebook** for running code.
* Install scikit-learn in terminal:

  ```bash
  conda install -c anaconda scikit-learn
  ```

---

### 🔹 Machine Learning Process

1. **Load the data**
2. **Preprocess the data**
3. **Train a model**
4. **Evaluate the model**
5. **Make predictions**

---

### 🔹 Code Walkthrough (Iris Dataset)

```python
# Importing necessary libraries
import pandas as pd
from sklearn.linear_model import LogisticRegression

# Load the dataset (Iris.csv from Kaggle)
iris_data = pd.read_csv('Iris.csv')
iris_data.head()

# Split the data into features (X) and labels (y)
X = iris_data.drop(columns=['Id', 'Species'])   # Features: flower measurements
y = iris_data['Species']                        # Labels: flower species

# Create a Machine Learning model
model = LogisticRegression()

# Train the model on the dataset
model.fit(X.values, y)

# Predict using the trained model
predictions = model.predict([[6, 3.0, 5, 2.3]])
print(predictions)
```

---

### 🔹 Explanation

* **pandas (pd)** → Used for loading and manipulating the dataset.
* **LogisticRegression** → ML model from scikit-learn for classification tasks.
* **iris\_data** → DataFrame containing iris flower measurements + species.
* **X** → Input features (SepalLength, SepalWidth, PetalLength, PetalWidth).
* **y** → Labels (Species of iris flower).
* **model.fit()** → Trains the Logistic Regression model.
* **model.predict()** → Predicts species for new flower measurements.

---

