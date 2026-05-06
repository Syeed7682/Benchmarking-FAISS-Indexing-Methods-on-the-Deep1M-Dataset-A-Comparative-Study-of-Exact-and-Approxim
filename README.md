# FAISS Performance Benchmarking on Deep1M Dataset

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![FAISS](https://img.shields.io/badge/library-FAISS-green.svg)](https://github.com/facebookresearch/faiss)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive analytical comparison of **Approximate Nearest Neighbor (ANN)** search algorithms using the Facebook AI Similarity Search (FAISS) library. This project benchmarks multiple indexing strategies on the **Deep1M** dataset (96-dimensional angular vectors).

---

## 🚀 Project Overview

The objective of this assignment is to evaluate the performance trade-offs (Speed vs. Accuracy vs. Memory) between exact search and various approximation methods across different dataset scales.

### 📊 Evaluated Indices
*   **`IndexFlatIP`**: Brute-force exact search using Inner Product (Baseline).
*   **`IndexIVFFlat`**: Inverted File Index—accelerates search by clustering vectors.
*   **`IndexIVFPQ`**: Inverted File with Product Quantization—drastic memory compression.
*   **`IndexHNSWFlat`**: Hierarchical Navigable Small World graphs—state-of-the-art graph-based search.
*   **`IndexLSH`**: Locality Sensitive Hashing—probabilistic hashing for fast lookups.

---

## ✨ Key Features
- **Multi-Scale Benchmarking**: Comparative analysis on **100K** and **1M** vector subsets.
- **Performance Metrics**:
    - ⏱️ **Build Time**: Time taken to train and populate the index.
    - ⚡ **Query Latency**: Average time per search (measured in milliseconds).
    - 🎯 **Recall@10**: Accuracy relative to the exact ground truth.
    - 🧠 **Memory Usage**: RAM footprint of the serialized index.
- **Hyperparameter Optimization**: Sweep analysis for `nprobe` (IVF) and `efSearch` (HNSW) to find the "sweet spot" in the recall-latency curve.
- **Automated Visualization**: Generates 6 high-quality plots for deep-dive analysis.

---

## 🛠️ Installation & Setup

### Prerequisites
Ensure you have Python 3.8+ installed. It is recommended to use a virtual environment.

### Dependencies
Install the required analytical stack:
```bash
pip install faiss-cpu h5py numpy pandas matplotlib seaborn
```

---

## 📖 How to Run

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/Syeed7682/Benchmarking-FAISS-Indexing-Methods-on-the-Deep1M-Dataset-A-Comparative-Study-of-Exact-and-Approxim.git
    cd Benchmarking-FAISS-Indexing-Methods-on-the-Deep1M-Dataset-A-Comparative-Study-of-Exact-and-Approxim
    ```

2.  **Dataset Acquisition**:
    The script handles the download of the `deep-image-96-angular.hdf5` dataset (approx. 3.5GB) automatically from ANN-Benchmarks.

3.  **Execute Benchmarks**:
    ```bash
    python kha_mo_syeed_asif__2022_3_60_030_assignment_faiss_deep1m.py
    ```

---

## 📉 Results & Insights

The execution generates a series of comparative visualizations:

| Plot Name | Description |
| :--- | :--- |
| `plot1_build_time.png` | Efficiency of index creation across different architectures. |
| `plot2_query_latency.png` | Search throughput analysis (logarithmic scale). |
| `plot3_recall.png` | Accuracy benchmarks (Recall@10). |
| `plot4_memory.png` | RAM efficiency and compression performance. |
| `plot5_recall_vs_latency.png` | The core Speed-Accuracy trade-off scatter plot. |
| `plot6_scalability.png` | Analysis of how performance shifts from 100K to 1M vectors. |

---

## 👨‍💻 Author

**Kha. Mo. Syeed Asif**
- **Student ID**: 2022-3-60-030
- **Course**: CSE488 (Assignment)
- **Institution**: East West University

---

## 📜 License
Distributed under the MIT License. See `LICENSE` for more information.
