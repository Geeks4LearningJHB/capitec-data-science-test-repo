# Capitec Data Science Test Repo

Training dataset and starter notebook for the Capitec Data Science Course, prepared by **Geeks4Learning (Pty) Ltd**.

This repository is **public**, so it can be accessed either by cloning it or by loading the data straight from GitHub with pandas — see [Getting Started](#getting-started) below.

---

## Repository structure

```
capitec-data-science-test-repo/
├── data/
│   ├── dim_campaign.csv
│   ├── dim_channel.csv
│   ├── dim_client.csv
│   ├── dim_date.csv
│   ├── dim_geography.csv
│   ├── dim_industry.csv
│   ├── dim_month.csv
│   ├── dim_product.csv
│   ├── fact_campaign_touch.csv
│   ├── fact_client_monthly.csv
│   ├── fact_digital_events.csv
│   └── fact_product_adoption.csv
└── notebooks/
    └── load_data.ipynb
```

### Data dictionary

| File | Type | Description |
|---|---|---|
| `dim_campaign.csv` | Dimension | Marketing campaign details |
| `dim_channel.csv` | Dimension | Communication / marketing channel reference |
| `dim_client.csv` | Dimension | Client / customer profile attributes |
| `dim_date.csv` | Dimension | Calendar date reference table |
| `dim_geography.csv` | Dimension | Geographic / regional reference |
| `dim_industry.csv` | Dimension | Client industry classification |
| `dim_month.csv` | Dimension | Month-level reference table |
| `dim_product.csv` | Dimension | Product reference table |
| `fact_campaign_touch.csv` | Fact | Client-campaign touchpoint events |
| `fact_client_monthly.csv` | Fact | Monthly client-level metrics |
| `fact_digital_events.csv` | Fact | Digital / app interaction events |
| `fact_product_adoption.csv` | Fact | Product adoption / uptake metrics |

This follows a typical star-schema layout: `dim_*` tables describe entities (clients, campaigns, channels, geography, etc.), and `fact_*` tables hold the measurable events and metrics that reference those dimensions.

---

## Getting Started

### Option 1: Clone the repository

**Using GitHub Desktop:**
1. Open GitHub Desktop.
2. Select **File > Clone Repository**.
3. Under the **URL** tab, enter: `https://github.com/Geeks4LearningJHB/capitec-data-science-test-repo.git`
4. Choose a local folder and click **Clone**.

**Using Git on the command line:**
```bash
git clone git@github.com:Geeks4LearningJHB/capitec-data-science-test-repo.git
```
(requires an SSH key set up on your GitHub account)

### Option 2: Load the data directly with pandas

No clone needed — read any CSV straight from GitHub using the raw file URL:

```python
import pandas as pd

url = "https://raw.githubusercontent.com/Geeks4LearningJHB/capitec-data-science-test-repo/main/data/dim_campaign.csv"
df = pd.read_csv(url)
df.head()
```

---

## Requirements

- Python 3.11 or later
- Jupyter Notebook or JupyterLab (bundled with Anaconda)

Install the required packages:

```bash
pip install pandas numpy jupyter jupyterlab
```

If you installed Python via **Anaconda**, `pandas`, `numpy`, and `jupyter` are already included — no extra install needed.

---

## Running `load_data.ipynb`

The `notebooks/load_data.ipynb` notebook loads every CSV in `data/` into a dictionary of pandas DataFrames, and works whether or not you cloned the repository:

- If you **cloned the repo**, it reads the files locally from `../data/`.
- If you **only downloaded the notebook** on its own, it automatically falls back to pulling each file from GitHub's raw URLs, since the repository is public.

**Steps to run it:**

1. Open a terminal (or Anaconda Prompt) and navigate to the `notebooks/` folder:
   ```bash
   cd capitec-data-science-test-repo/notebooks
   ```
2. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
3. Open **`load_data.ipynb`** in the browser tab that opens.
4. Run all cells (**Cell > Run All**, or step through with **Shift + Enter**).
5. On success, you'll see a printed summary of all 12 tables with their row and column counts, followed by preview outputs of a few key tables.

Once loaded, every table is available from the `data` dictionary by name, e.g.:

```python
data["fact_client_monthly"].head()
data["dim_client"].info()
```

### Troubleshooting

| Issue | Fix |
|---|---|
| `ModuleNotFoundError: No module named 'pandas'` | Run `pip install pandas` (or `pip3 install pandas` on Mac) in the same environment you launched Jupyter from |
| Notebook can't find local files | Confirm you opened Jupyter from inside `notebooks/`, so the relative path `../data/` resolves correctly |
| `HTTPError` when loading from GitHub | Check your internet connection, and confirm the repository is still set to Public |

---

## Contact

For access issues or questions about this dataset, reach out to the Geeks4Learning Technical Department facilitator running your induction session.
