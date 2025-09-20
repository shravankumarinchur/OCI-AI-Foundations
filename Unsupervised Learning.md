
---

## 🔹 What is Unsupervised Learning?

* A type of **Machine Learning** where the dataset has **no labels** (no correct output is given).
* The algorithm learns the **patterns** and **structures** in data on its own.
* Main goal → **group similar items together** or **detect hidden structures**.

👉 Example:

* Suppose you have shopping data (no labels).
* The algorithm may automatically group:

  * Cluster 1 → Students (low budget, frequent snacks)
  * Cluster 2 → Families (household items, bulk shopping)
  * Cluster 3 → Working professionals (ready-to-eat meals, beverages)

---

## 🔹 Workflow of Unsupervised Learning

1. **Prepare the data**

   * Remove missing values
   * Normalize & scale features
   * Example: Scale height/weight data so both are comparable.

2. **Create similarity metrics**

   * Define how to measure similarity between points.
   * Common metrics: **Euclidean Distance, Cosine Similarity, Manhattan Distance**.
   * Example: Two customers are *similar* if they buy the same type of products frequently.

3. **Run clustering algorithm**

   * Use algorithms like **K-Means, DBSCAN, Hierarchical Clustering**.
   * Example: K-Means divides customers into `k` groups based on purchase history.

4. **Interpret results & adjust clustering**

   * Evaluate how good the clustering is.
   * Example: If customers in the same cluster show very different buying habits, re-adjust `k` or use another algorithm.

---

## 🔹 Key Concept – Similarity

* **Similarity** = how close two data points are.
* Value lies between **0 (completely different)** and **1 (identical)**.
* Example:

  * Customer A → Buys Coke, Pepsi
  * Customer B → Buys Pepsi, Sprite
  * Similarity(A, B) ≈ 0.7

---

## 🔹 Types of Unsupervised Learning

### 1. **Clustering**

Grouping similar data points together.

👉 Example:

* **Market Segmentation**

  * **Input:** Customers’ purchasing history
  * **Process:** Group customers with similar behavior
  * **Output:** Targeted advertisements for each group

---

### 2. **Outlier / Anomaly Detection**

Identifying data points that don’t fit the normal pattern.

👉 Example:

* **Fraud Detection**

  * **Input:** Credit card transactions
  * **Process:** Detect unusually large or suspicious purchases
  * **Output:** Flag as potential fraud

---

### 3. **Recommendation Systems**

Suggesting items based on patterns in user behavior.

👉 Example:

* **Movie Recommendation**

  * **Input:** User viewing history
  * **Process:** Find similar users by genre preference
  * **Output:** Personalized movie recommendations

---

## 🔹 Real-World Applications

* Customer segmentation in marketing
* Fraud detection in banking
* Document/topic clustering in NLP
* Image compression and grouping similar images
* Recommendation engines (Netflix, Amazon, Spotify)

---

✅ **Summary:**

* Unsupervised Learning = finding hidden patterns without labels.
* Key tasks = **Clustering, Anomaly Detection, Recommendations**.
* Depends heavily on **similarity metrics**.
* Useful in real-world where labeling data is expensive or impossible.

---

