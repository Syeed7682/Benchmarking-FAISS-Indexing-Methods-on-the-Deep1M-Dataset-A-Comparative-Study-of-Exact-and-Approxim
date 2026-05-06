# FAISS Performance Comparison on Deep1M Dataset

This project implements and benchmarks various Approximate Nearest Neighbor (ANN) search indices using the **FAISS** library on the **Deep1M** dataset. The comparison includes exact search and various approximate methods across different dataset scales (100K and 1M vectors).

## Project Overview

The project evaluates the following FAISS index types:
- **IndexFlatIP**: Exact search using Inner Product (baseline).
- **IndexIVFFlat**: Inverted File Index with Flat storage.
- **IndexIVFPQ**: Inverted File Index with Product Quantization.
- **IndexHNSWFlat**: Hierarchical Navigable Small World graphs.
- **IndexLSH**: Locality Sensitive Hashing.

## Key Features
- **Dataset Scale**: Benchmarks performed on 100,000 and 1,000,000 vector subsets.
- **Metrics Evaluated**:
    - Build Time (seconds)
    - Average Query Latency (milliseconds)
    - Recall@10
    - Memory Usage (MB)
- **Hyperparameter Tuning**: Sweeps for `nprobe` (IVF) and `efSearch` (HNSW) to analyze recall-latency trade-offs.
- **Visualizations**: Comprehensive plots comparing performance across all indices.

## Requirements

To run the script, you need the following Python packages:
```bash
pip install faiss-cpu h5py numpy pandas matplotlib seaborn
```

## How to Run

1.  **Clone or Download**: Ensure the script `kha_mo_syeed_asif__2022_3_60_030_assignment_faiss_deep1m.py` is in your directory.
2.  **Dataset**: The script will automatically attempt to download the `deep-image-96-angular.hdf5` dataset (approx. 3.5GB) from `ann-benchmarks.com`.
3.  **Execute**:
    ```bash
    python kha_mo_syeed_asif__2022_3_60_030_assignment_faiss_deep1m.py
    ```

## Results & Visualizations

The script generates several summary tables and plots:
- `plot1_build_time.png`: Comparison of index creation times.
- `plot2_query_latency.png`: Average search time per query (log scale).
- `plot3_recall.png`: Accuracy (Recall@10) comparison.
- `plot4_memory.png`: RAM footprint of each index.
- `plot5_recall_vs_latency.png`: Trade-off analysis between speed and accuracy.

## Author
**Kha. Mo. Syeed Asif**
ID: 2022-3-60-030
Assignment: FAISS Deep1M Analysis
