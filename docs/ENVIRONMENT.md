# Environment & Dependencies

This project runs in the Microsoft Fabric analytics platform, using trial or licensed capacity. Data is staged in a Fabric Lakehouse, and all analysis is done in Fabric Notebooks. Follow the steps below to reproduce the environment and ensure dependencies are met.

---

## 1. Platform Prerequisites

- **Microsoft Fabric account** (trial or licensed)
    - [Start a Fabric trial](https://learn.microsoft.com/en-us/fabric/fundamentals/fabric-trial)
- **Access to Fabric Lakehouse and Notebooks**
    - Permission to create and manage Lakehouses
    - Permission to run Notebooks

## 2. Data Staging

- **Lakehouse:** Your data must be staged in a Fabric Lakehouse. The folder structure used by this project is described in the main [README](README.md).
- **Required dataset:** NYC For-Hire Vehicle Trip Data, January 2025 (CSV/Parquet)
    - Download from: [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
    - Upload to Lakehouse as described in the [README](README.md#b-data-sources)

## 3. Notebook Environment

- **Fabric Notebook Kernel:** Python (recommended) or R (if code provided)
- **Configured Lakehouse:** Attach your Fabric Notebook to the staged Lakehouse

### Required Python Packages

The default Fabric Python environment provides most scientific/data libraries. If you install additional packages, use the notebook’s `%pip` or `%conda` magic commands. Required packages:

- `pandas`
- `numpy`
- `scipy`
- `matplotlib` or `seaborn` (for plotting, if used)
- `statsmodels` (if used for statistical testing)
- `pyarrow` (for Parquet reading, usually preinstalled)

**Example installation cell:**
```python
# Uncomment and run if package is missing
# %pip install pandas numpy scipy matplotlib seaborn statsmodels pyarrow
```

### Optional: R Package Requirements

If you use R notebooks, specify similar packages (`dplyr`, `ggplot2`, etc).

## 4. Optional: Local Development

If you want to prototype code locally (outside Fabric), install Python 3.8+ and the packages above. Use a virtual environment:

```sh
python -m venv .venv
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
pip install pandas numpy scipy matplotlib seaborn statsmodels pyarrow
```

## 5. Versioning and Reproducibility

- **Fabric Notebooks:** Save notebook versions as you iterate.
- **Data:** Ensure you use the correct data version/month.
- **Python Packages:** For strict reproducibility, record exact package versions:
    - `pip freeze > requirements.txt`
    - Or export via Fabric Notebook UI if supported.

## 6. Helpful Links

- [Microsoft Fabric Documentation](https://learn.microsoft.com/en-us/fabric/)
- [Fabric Lakehouse Overview](https://learn.microsoft.com/en-us/fabric/data-engineering/lakehouse-overview)
- [Fabric Notebooks Overview](https://learn.microsoft.com/en-us/fabric/data-engineering/notebooks-overview)

---

**Questions or issues?**  
Open an issue in this repo or contact the project maintainer.
