## Introduction  
---------------

The **RT-IoT2022** dataset is a cybersecurity dataset designed for detecting intrusions and anomalies in IoT (Internet of Things) networks. It contains a mix of numerical and categorical features extracted from network traffic, which makes it a great candidate for tree-based ensemble models.

These are the questions I've gone through on my notebooks:

1. **Columns Composition via Pie-Chart.** <br/>
2. **Descriptive Statistics.** <br/>
3. **Pairplot KDE for float columns based on Target.** <br/>
4. **Pairplot KDE for numerical columns based on Target.** <br/>
5. **Correlation Plot.** <br/>
6. **Most 20 correlated columns.** <br/>
7. **Packages.** <br/>
8. **Data Preprocessing with ColumnTransformer and using Train Test Split.** <br/>
9. **Modeling with Stratified.** <br/>

**Citation: [RT-IoT2022](https://archive.ics.uci.edu/dataset/942/rt-iot2022). (2024). UCI Machine Learning Repository.** <br/>
--------------------------------------------------------------------------------------------------------------------


### I. How to import the dataset via pip.
--------------------------------------------------------------------------------------------------------------------
```
!pip install ucimlrepo
Import the dataset into your code 
from ucimlrepo import fetch_ucirepo 
  
# fetch dataset 
rt_iot2022 = fetch_ucirepo(id=942) 
  
# data (as pandas dataframes) 
X = rt_iot2022.data.features 
y = rt_iot2022.data.targets
  
  
# metadata 
print(rt_iot2022.metadata) 
  
# variable information 
print(rt_iot2022.variables)

```
--------------------------------------------------------------------------------------------------------------------
**XGBoost** and **LightGBM**, are the most popular gradient boosting frameworks used also by a large number of Kagglers on competition. Each has its own advantages depending on the use case:

### **1. XGBoost (Extreme Gradient Boosting)**
**Advantages:**
- **Highly Optimized**: Implements optimized gradient boosting with parallel tree boosting.
- **Regularization (L1 & L2)**: Reduces overfitting through built-in L1 (Lasso) and L2 (Ridge) regularization.
- **Handling Missing Values**: Automatically learns how to deal with missing values.
- **Tree Pruning (Depth-wise Growth)**: Prevents overfitting by pruning trees based on a threshold.
- **Custom Objective Functions**: Supports user-defined loss functions.
- **Distributed Computing Support**: Works with Spark, Hadoop, and Dask for large-scale training.

**Best for:** 
- **General gradient boosting applications.**
- **Tabular data with numerical & categorical features.**
--------------------------------------------------------------------------------------------------------------------
### **2. LightGBM (Light Gradient Boosting Machine)**
**Advantages:**
- **Faster Training**: Uses histogram-based learning and leaf-wise tree growth, making it faster than XGBoost.
- **Memory Efficient**: Requires less memory due to its histogram-based approach.
- **Good for Large Datasets**: Scales well to large datasets with high dimensionality.
- **Handles Categorical Features Natively**: Can directly process categorical data without encoding.
- **Efficient Parallelism**: More efficient than XGBoost when training on large datasets.

**Best for:** 
- **Large-scale datasets.**
- **low-latency applications.**
--------------------------------------------------------------------------------------------------------------------

