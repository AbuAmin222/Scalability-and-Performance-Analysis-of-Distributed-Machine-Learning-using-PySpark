# Scalability & Performance Analysis of Distributed ML. Using (PySpark)

## 👥 Group Members

* **Dia El-din Amin Habib** (120210319)
* **Khaled Zai-El-Din** (120212536)
---

## 📌 Project Overview

This project is a high-performance Big Data pipeline built with **Apache Spark (PySpark)** and deployed on the **Google Colab** cloud platform. It is designed to handle multi-source data ingestion, automated data engineering, and distributed Machine Learning. The system processes over **5.1 million records** to demonstrate the power of cloud scalability.

## 🚀 Key Features

* **Multi-Source Ingestion:** Automatically merges 10+ CSV data blocks into a single Spark DataFrame.
* **Automated Data Engineering:** Handles schema casting (e.g., converting strings to doubles) to ensure 100% model stability.
* **Performance Benchmarking:** Automated tracking of execution time, Speedup, and Efficiency across 1, 2, 4, and 8|16 machines.
* **Distributed ML Suite:** Execution of four distinct tasks using **Spark MLlib**:
1. **Linear Regression** (Predictive Modeling)
2. **KMeans Clustering** (Unsupervised Recognition)
3. **Advanced Statistics** (Large-scale Aggregations)
4. **Decision Tree Classification** (Logical Categorization)



## 📊 Scalability Results

The system was tested on a dataset of Millions records. Results show a significant performance boost as nodes increase:

| Nodes | Time (s)  | Speedup | Efficiency   |
| 1     | 1.0828s   | 1.00x   | 100.00%      |
| 2     | 0.3996s   | 2.71x   | 135.50%      |
| 4     | 0.3912s   | 2.77x   | 69.20%       |
| 8     | 0.3756s   | 2.88x   | 36.04%       |

## 🛠 Troubleshooting & Solutions

* **Data Type Conflicts:** We solved "String-to-Double" errors caused by noise (like `?` signs) by implementing a dynamic casting loop with `nullValue` configurations.
* **Memory Management:** To avoid browser crashes with files over 100MB, we transitioned from a JavaScript-based UI to **Direct Path Loading**, allowing Spark to utilize parallel I/O for maximum stability.

## 💻 Technical Stack

* **Core Engine:** Apache Spark (PySpark)
* **ML Library:** Spark MLlib
* **Cloud Platform:** Google Colab
* **Language:** Python

## 📂 How to Run

1. **Environment Setup:** Run the initialization cell to install PySpark and start the Spark Session(First code block).
2. **Upload Data:** Place your CSV files directly into the `/content/` folder in the Colab sidebar.
3. **Execute:** Run the main processing cell to generate the scalability report and ML results(Secound block code).

## 🔗 Project Links

* **Video Demonstration:** [https://youtu.be/izR4qq4uCRk], [https://youtu.be/6MwFrhZ-eHI]
* **Google Colab:** [https://colab.research.google.com/drive/1XKvZGnXCkXOfMB-RJseka-7eMC05ymLU?usp=sharing]

---

*Developed for the 
- Cloud and Distributed Systems course (SICT 4313)
- Dr. Rebhi S. Baraka
- Software Development Specializations 
- International Technology(IT) College
- Islamic University of Gaza.
