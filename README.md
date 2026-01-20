# Dimension Calculation

**Dimension Calculation** is a Python package designed to estimate the *effective dimension* of a dataset using several statistical and geometrical approaches.
It is particularly useful when dealing with high-dimensional data, mixed variable types, or when studying the curse of dimensionality.

## ✨ Features

- Supports **multiple dimension estimation methods**.
- Works with **numerical and categorical data**.
- Automatic preprocessing:
  - Missing value handling,
  - Label encoding for categorical variables,
  - Feature normalisation.
- Designed for **data analysis and research purposes**.

## 📦 Installation

Install the package from PyPI:

```bash
pip install dimension-calculation
```

## 🚀 Quick start

```python
import pandas as pd
import dimension_calculation as dc

df = pd.read_csv("data.csv")

dimension = dc.dimension_calculation(df)

print(dimension)
```

By default, the method `"nearest-neighbour-3"` is used.

## 🧠 Available methods

The `dimension_calculation` function supports the following methods:

* `"variance-ratio"`
* `"n1"`
* `"n2"`
* `"infinite-n"`
* `"MCMC"`
* `"nearest-neighbour-1"`
* `"nearest-neighbour-2"`
* `"nearest-neighbour-3"` *(default)*

Example:

```python
dc.dimension_calculation(df, method="variance-ratio")
```

## 📊 Function signature

```python
dimension_calculation(
    dataframe: pd.DataFrame,
    method: str = "nearest-neighbour-3"
) -> int
```

### Parameters

* **dataframe** (`pd.DataFrame`)
  Input dataset. Must contain at least two columns.

* **method** (`str`)
  Dimension estimation method to use.

### Returns

* **int**
  Estimated effective dimensionality of the dataset.

## ⚠️ Notes and assumptions

* Missing values are automatically replaced with `0`.
* Categorical variables are encoded using `LabelEncoder`.
* Features are scaled to `[0, 1]` using `MinMaxScaler`.
* Some methods rely on random sampling and may produce slightly different results across runs.

## 📚 Research and documentation

This package is based on extensive research into the curse of dimensionality and effective dimension estimation.

You can find the full research materials here:

* 📄 **Research paper (theoretical background)**

  👉 [Dimension - From Curse to Effectivity.pdf](https://github.com/Alexandre-Deroux/Dimension-Calculation/blob/main/Dimension%20-%20From%20Curse%20to%20Effectivity.pdf)

* 📓 **Jupyter Notebook (experiments and implementation)**

  👉 [Dimension Calculation.ipynb](https://github.com/Alexandre-Deroux/Dimension-Calculation/blob/main/Dimension%20Calculation.ipynb)

* 📊 **All data used**

  👉 [Datasets - Dimension Calculation](https://doi.org/10.5281/zenodo.15768001)

## 🛠 Dependencies

* numpy
* pandas
* scikit-learn
* scipy

All dependencies are automatically installed via `pip`.

## 📜 Licence

This project is licensed under the **MIT Licence**.
You are free to use, modify, and distribute this software, provided that the original copyright notice is retained.

## 👤 Author

**[Alexandre Deroux](https://www.linkedin.com/in/alexandre-deroux/en)**

## 💬 Feedback and contributions

This project was developed primarily for research and experimentation.
Feedback, discussions, and improvements are welcome.