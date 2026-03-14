# Analysis Solar 1

Exploratory data analysis of solar panel sensor data — visualizing irradiation, DC current generation, energy output, phase voltage balance, and AC frequency stability.

## What It Does

Reads time-series data from an SMA solar inverter (sensor SENS0802 + inverter WRHM6Y94) and produces diagnostic plots:

1. **Solar Irradiation** — sensor surface irradiance over the day, with cloud-cover dips visible
2. **DC Current (4 channels)** — amperage from four sensor inputs (A, A1, B, B1), showing proportionality to irradiance
3. **Total Energy Generated** — cumulative watt output across the monitoring window
4. **3-Phase Voltage Difference** — deviation between phase A/B/C voltages (lower = better)
5. **AC Frequency Stability** — grid frequency fluctuations around 50/60 Hz

## Dataset

The notebook expects a semicolon-delimited CSV file named `dd.csv` (ISO-8859-1 encoded) in the project root. The file contains 15-minute interval readings from SMA inverter hardware. The CSV is not included in this repository.

## 🛠 Tech Stack

| Tool | Purpose |
|------|---------|
| 🐍 Python 3.10+ | Runtime |
| 🐼 pandas | Data loading and manipulation |
| 📊 matplotlib | Plotting and visualization |
| 🔢 NumPy | Numeric operations |
| 📓 Jupyter Notebook | Interactive analysis |

## Getting Started

```bash
pip install -r requirements.txt
jupyter notebook Solar_Analysis.ipynb
```

Place your `dd.csv` data file in the project root before running.

## ⚠️ Known Issues

- The dataset (`dd.csv`) is not included in the repository — you need to supply your own SMA inverter export.
- Column names (e.g. `WRHM6Y94.15`) are hardware-specific and may differ across inverter models.
