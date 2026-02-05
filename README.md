## 📌 AIOps Capstone Project (TechCorp Crisis Simulation)

This repository contains an end-to-end **AIOps workflow** that combines **system metrics**, **incident alerts**, and **application logs** to detect hidden threats, discover log patterns, and forecast capacity risks — culminating in an auto-generated **executive intelligence report**.

### What you’ll get

* **Health snapshot** of key infrastructure signals
* **Anomaly detection** on CPU / memory / disk using *Isolation Forest*
* **Log intelligence** using *TF-IDF + KMeans clustering* to identify recurring operational patterns
* **Capacity forecasting** using *SARIMAX* to predict disk saturation timelines
* A generated **Markdown intelligence report** summarizing findings + recommended actions

---

## 📁 Repository Structure

```text
AIOps Final Project/
├─ demo-notebook.ipynb
└─ data/
   ├─ capstone-project/
   │  ├─ system_metrics.csv
   │  ├─ incident_alerts.csv
   │  ├─ application_logs.txt
   │  └─ 2025_AIOps_Intelligence_Report.md   # generated output
   ├─ app_logs.txt
   ├─ cpu_full_a.csv
   ├─ metrics_capacity_planning.csv
   ├─ metrics_intelligent.csv
   ├─ system_resources_clean.csv
   └─ system_resources_raw.csv
```

---

## ⚙️ Requirements

* Python **3.9+**
* Jupyter Notebook / JupyterLab

Core libraries used in the notebook:

* `pandas`, `numpy`
* `matplotlib`, `seaborn`
* `scikit-learn`
* `statsmodels`

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels jupyter
```

---

## 🚀 Quick Start

1. **Clone the repo** and open the notebook:

```bash
jupyter notebook
```

2. **Update the dataset path** in `demo-notebook.ipynb`.

⚠️ The notebook currently contains a Windows absolute path like:

```python
DATA_DIR = r'C:\Users\...\AIOps Final Project\data\capstone-project'
```

✅ Replace it with a relative path (recommended):

```python
DATA_DIR = "data/capstone-project"
```

3. **Run all cells** to generate results and the final report.

---

## 🧠 How the Pipeline Works

### 1) Crisis Assessment (Metrics)

Identifies critical utilization (disk is typically the primary risk in this dataset).

### 2) Anomaly Detection (Isolation Forest)

Detects outliers across CPU/memory/disk and correlates anomalies during high disk pressure.

### 3) Log Intelligence (TF-IDF + KMeans)

Transforms log messages into vectors and clusters them into operational patterns (e.g., error bursts, performance degradation signatures).

### 4) Capacity Forecasting (SARIMAX)

Forecasts disk usage trends and estimates threshold breach dates (e.g., 80% / 90% / 95%).

### 5) Executive Intelligence Report

Writes a Markdown report to:

```text
data/capstone-project/2025_AIOps_Intelligence_Report.md
```

---

## 📄 Output

After running the notebook, you’ll find the generated report here:

* `data/capstone-project/2025_AIOps_Intelligence_Report.md`

It includes:

* current disk level
* anomaly totals + correlations
* log cluster findings
* forecast breach dates
* recommended immediate and short-term actions

---

## ✅ Notes / Tips

* If SARIMAX struggles on your environment, keep `statsmodels` updated and ensure the daily series is interpolated (the notebook already handles smoothing/cleanup steps).
* For real production use, this notebook can be extended into a scheduled pipeline (Airflow/GitHub Actions) and integrated with Prometheus/Loki/ELK.

---

If you want, paste your repo URL (or your desired repo name + description), and I’ll tailor this README section to match your exact GitHub layout (badges, “Results” screenshots section, and a clean `requirements.txt`).
