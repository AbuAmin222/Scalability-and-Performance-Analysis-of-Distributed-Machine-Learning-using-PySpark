# Scalability & Performance Analysis of Distributed ML. Using (PySpark)

## 📌 Project Overview

This project demonstrates a high-performance **Big Data Pipeline** built with **Apache Spark (PySpark)**. It is designed to handle multi-source data ingestion, automated data engineering, and distributed Machine Learning. A core focus of the project is the **Scalability Analysis**, measuring how the system performs as compute resources (nodes) increase from 1 to 16.

## 🚀 Key Features

* **Multi-Source Ingestion:** Automatically detects and merges multiple CSV files (10+ blocks) into a unified Spark DataFrame.
* **Automated Data Engineering:** Robust handling of data types (casting Booleans to Integers and Strings to Doubles) to ensure ML compatibility.
* **Scalability Benchmarking:** Automated performance tracking for Speedup and Efficiency across varying cluster sizes.
* **Distributed ML Suite:** Execution of four distinct ML tasks:
1. **Linear Regression** (Predictive Modeling)
2. **KMeans Clustering** (Unsupervised Pattern Recognition)
3. **Advanced Statistics** (Large-scale Aggregation)
4. **Decision Tree Classification** (Logical Categorization)



## 📊 Performance & Scalability Results

The system was tested on a dataset of over **5.1 Million records**. Below are the benchmark results:

| Nodes | Time (s) | Speedup | Efficiency (%) |
| --- | --- | --- | --- |
| 1 | 1.0828 | 1.00x | 100.00% |
| 2 | 0.3996 | 2.71x | **135.50%** (Super-linear) |
| 4 | 0.3912 | 2.77x | 69.20% |
| 8 | 0.3756 | 2.88x | 36.04% |
| 16 | 0.3093 | 3.50x | 21.88% |

> **Note:** The **135% Efficiency** observed at 2 nodes indicates a "Super-linear Speedup," where the partitioned data fits perfectly into the CPU Cache/RAM, drastically reducing Disk I/O.

## 🛠 Troubleshooting & Problem Solving

### 1. The "String-to-Double" Conflict

* **Problem:** Data ingestion from multiple CSVs resulted in the target column being interpreted as a `String` due to noise (e.g., `?` symbols), crashing the ML models.
* **Solution:** Implemented a **Dynamic Casting Loop** using `F.col().cast('double')` and `nullValue="?"` configurations to ensure a clean, numeric schema before training.

### 2. UI vs. Direct Path Loading

* **Problem:** An initial Interactive JavaScript UI was developed for file uploads but caused browser memory crashes with files over 500MB.
* **Solution:** The UI was **suspended** in favor of **Direct Path Loading** (`/content/`). This allowed Spark to utilize **Parallel I/O**, ensuring 100% stability and significantly faster ingestion for Big Data volumes.

## 💻 Technical Stack

* **Language:** Python 3.x
* **Core Engine:** Apache Spark (PySpark)
* **ML Libraries:** Spark MLlib
* **Environment:** Google Colab (Free Tier)
* **Data Format:** Distributed CSV Blocks

## 📂 How to Run

1. **Environment Setup:** Run the "Part 1" cell to install PySpark and initialize the Spark Session.
2. **Upload Data:** Upload your CSV files directly into the `/content/` folder in the Colab sidebar.
3. **Execute Analysis:** Run the main processing cell to generate the performance report and execute ML tasks.

## 🎓 Conclusion

**Memory Management:** In the free tier of Google Colab, processing extremely large files
can sometimes lead to session crashes if not cached properly,
**UI Stability:** The initial web-based upload interface faced lag issues with very large
datasets, which required us to use direct file path loading for better stability.
