# 🌸 Iris Data Visualization using Density & Contour Plots

## 📌 Overview

This project demonstrates how to visualize data distribution and relationships using **Density Plots (KDE)** and **Contour Plots** on the Iris dataset.

The goal is to understand patterns, clusters, and feature relationships using Python visualization libraries.

---

## 🎯 Objective

* Analyze distribution of numerical data using density plots
* Compare distributions across categories
* Visualize relationships between variables using contour plots
* Identify clusters, patterns, and correlations

---

## 📊 Dataset

The **Iris dataset** contains:

* 150 samples of iris flowers
* 3 species:

  * Setosa
  * Versicolor
  * Virginica
* 4 numerical features:

  * Sepal Length
  * Sepal Width
  * Petal Length
  * Petal Width

👉 In this project, we focus on:

* **Petal Length**
* **Petal Width**

---

## 📘 Theory

### 🔹 Probability Density

Probability density describes how data is distributed over a continuous range.
Higher peaks indicate higher concentration of data points.

---

### 🔹 Histogram vs Density Plot

| Histogram           | Density Plot             |
| ------------------- | ------------------------ |
| Uses bars           | Smooth curve             |
| Depends on bin size | Continuous               |
| Less accurate shape | Better distribution view |

---

### 🔹 KDE (Kernel Density Estimation)

* A method to estimate probability density
* Produces a smooth curve
* Helps identify distribution patterns clearly

---

### 🔹 Contour Plot

* Represents 2D density
* Lines connect points of equal density
* High-density regions indicate clusters

---

## 💻 Implementation

### 🔹 Step 1: Import Libraries

```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris
```

---

### 🔹 Step 2: Load Dataset

```python
iris = load_iris()
df = pd.DataFrame(iris.data, columns=iris.feature_names)
df['species'] = iris.target
```

---

### 🔹 Step 3: Convert Labels

```python
df['species'] = df['species'].map({
    0: 'setosa',
    1: 'versicolor',
    2: 'virginica'
})
```

---

### 🔹 Step 4: Density Plot

```python
sns.kdeplot(data=df, x='petal length (cm)', fill=True)
plt.title("Density Plot of Petal Length")
plt.show()
```

---

### 🔹 Step 5: Overlay Density Plot

```python
sns.kdeplot(data=df, x='petal length (cm)', hue='species', fill=True)
plt.title("Distribution by Species")
plt.show()
```

---

### 🔹 Step 6: Contour Plot

```python
sns.kdeplot(
    data=df,
    x='petal length (cm)',
    y='petal width (cm)',
    fill=True
)
plt.title("Contour Plot")
plt.show()
```

---

## 📈 Results

* Density plots show how petal length is distributed
* Overlay plots compare species distributions
* Contour plots reveal relationships between features

---

## 🧠 Interpretation

### 🔹 Density Plot Insights

* Setosa → smallest petal length
* Virginica → largest petal length
* Versicolor → intermediate values

👉 Indicates strong feature separation

---

### 🔹 Overlay Insights

* Clear separation for Setosa
* Slight overlap between Versicolor and Virginica

👉 Shows partial clustering

---

### 🔹 Contour Plot Insights

* Three distinct clusters visible
* High-density regions represent species groups
* Strong relationship between petal length & width

👉 Indicates:

* Features are correlated
* Data is well-clustered

---

## 🎯 Conclusion

Density and contour plots effectively visualize data distribution and relationships.

The Iris dataset shows clear clustering based on petal features, making it highly suitable for classification tasks in machine learning.

---

## 🛠️ Tools Used

* Python
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

---

## 📂 Project Structure

```
📁 iris-density-contour
 ┣ 📄 README.md
 ┣ 📄 iris_analysis.ipynb
 ┣ 📄 report.pdf
```

---

## ⭐ Future Improvements

* Add more features for visualization
* Use pair plots and heatmaps
* Apply machine learning classification

---

## 🙌 Author

Your Name Here
