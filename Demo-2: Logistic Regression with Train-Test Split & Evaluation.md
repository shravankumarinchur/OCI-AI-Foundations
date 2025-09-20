

# Demo-2: Logistic Regression with Train-Test Split & Evaluation


---

## 🔹 Full Code

```python
# Importing necessary libraries
import pandas as pd
import numpy as np
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import accuracy_score

# Load the dataset (downloaded from Kaggle)
iris_data = pd.read_csv('iris.csv')
iris_data.head()

# Split the data into features (X) and labels (y)
X = iris_data.drop(columns=['Id', 'Species'])
y = iris_data['Species']

# Split into training and testing sets (80% train, 20% test)
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Standardize the features
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

# Create a Logistic Regression model
model = LogisticRegression()

# Train the model
model.fit(X_train_scaled, y_train)

# Predict on test data
y_pred = model.predict(X_test_scaled)

# Evaluate model accuracy
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)

# Predict on new flower measurements
new_data = np.array([[5.1, 3.5, 1.4, 0.2],
                     [6.3, 2.9, 5.6, 1.8],
                     [4.9, 3.0, 1.4, 0.2]])

# Standardize new data
new_data_scaled = scaler.transform(new_data)

# Make predictions
predictions = model.predict(new_data_scaled)
print("Predictions:", predictions)
```

---

## 🔹 Explanation

👉 Compared to **Demo-1**, here we are using a few **extra libraries**:

* `numpy` → for arrays and new data inputs.
* `train_test_split` → to divide dataset into training & testing sets.
* `StandardScaler` → to normalize feature values.
* `accuracy_score` → to evaluate the trained model.

---

### 📦 Libraries

```python
import pandas as pd
```

* **Pandas** → Used for handling datasets (loading CSV, working with rows/columns, etc.).

```python
import numpy as np
```

* **NumPy** → Used for numerical operations and handling arrays (like the new data for prediction).

```python
from sklearn.linear_model import LogisticRegression
```

* **Scikit-learn LogisticRegression** → ML algorithm used here to classify Iris flowers.

```python
from sklearn.model_selection import train_test_split
```

* **train\_test\_split** → Splits dataset into **training set** (to train model) and **testing set** (to evaluate model).

```python
from sklearn.preprocessing import StandardScaler
```

* **StandardScaler** → Normalizes (scales) features so all columns are on a similar scale.

```python
from sklearn.metrics import accuracy_score
```

* **accuracy\_score** → Measures how well the model predicts (fraction of correct predictions).

---

### 📊 Data Handling

```python
iris_data = pd.read_csv('iris.csv')
iris_data.head()
```

* Reads the dataset `iris.csv` into a Pandas DataFrame.
* `.head()` shows the first 5 rows.

---

### ✂️ Features and Labels

```python
X = iris_data.drop(columns=['Id', 'Species'])
y = iris_data['Species']
```

* `X`: Features (input variables → SepalLength, SepalWidth, PetalLength, PetalWidth).
* `y`: Labels (output variable → Species of flower).

---

### 🔀 Train-Test Split

```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

* Splits data into **80% training** and **20% testing**.
* `random_state=42` ensures reproducibility.

---

### ⚖️ Standardization

```python
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

* Scales features so they have **mean = 0** and **standard deviation = 1**.
* Fit on training data (`fit_transform`), then apply same scaling to test data (`transform`).

---

### 🤖 Model Creation & Training

```python
model = LogisticRegression()
model.fit(X_train_scaled, y_train)
```

* Creates a Logistic Regression model.
* Fits (trains) the model using scaled training data.

---

### 📈 Model Evaluation

```python
y_pred = model.predict(X_test_scaled)
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)
```

* Predicts species for test data.
* Compares predictions with actual labels.
* Prints accuracy score.

---

### 🔮 Predictions on New Data

```python
new_data = np.array([[5.1, 3.5, 1.4, 0.2],
                     [6.3, 2.9, 5.6, 1.8],
                     [4.9, 3.0, 1.4, 0.2]])
```

* Creates **new flower measurements** for prediction.

```python
new_data_scaled = scaler.transform(new_data)
```

* Scales new data using the same scaler.

```python
predictions = model.predict(new_data_scaled)
print("Predictions:", predictions)
```

* Predicts flower species for new data.
* Prints results (e.g., `Iris-setosa`, `Iris-virginica`).

---

✅ **Summary:**

* Load dataset
* Split into features (`X`) & labels (`y`)
* Train-test split
* Standardize data
* Train Logistic Regression model
* Evaluate accuracy
* Predict on new data

---

