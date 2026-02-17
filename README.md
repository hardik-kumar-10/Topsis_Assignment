# Topsis_Assignment

# 📊 TOPSIS — Multi-Criteria Decision Making

**TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)**
by **Kumar Kashish** · Roll No: `102317239`

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Streamlit](https://img.shields.io/badge/Streamlit-Web%20App-FF4B4B?logo=streamlit&logoColor=white)](https://streamlit.io/)

---

## 📌 Table of Contents

- [About](#-about)
- [Methodology](#-methodology)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Input / Output Format](#-input--output-format)
- [Installation & Usage](#-installation--usage)
- [Live Demo](#-live-demo)
- [Repository Structure](#-repository-structure)

---

## 🧠 About

This project implements the **TOPSIS** algorithm — a popular Multi-Criteria Decision Making (MCDM) method — as both a **Python package (CLI tool)** and an **interactive Streamlit web application**.

It allows users to rank a set of alternatives against multiple weighted criteria, producing a normalized TOPSIS score (0–1) and a final ranking for each alternative.

---

## 📐 Methodology

TOPSIS ranks alternatives based on their geometric distance from the ideal best and worst solutions.

### Algorithm Steps

| Step | Description |
|------|-------------|
| 1️⃣ Normalize | Build a normalized decision matrix using vector normalization |
| 2️⃣ Weight | Apply user-defined weights to each criterion |
| 3️⃣ Ideal Solutions | Identify the **ideal best** and **ideal worst** values per criterion |
| 4️⃣ Distances | Calculate Euclidean distances from each alternative to ideal best/worst |
| 5️⃣ TOPSIS Score | Compute relative closeness coefficient *(range: 0 to 1)* |
| 6️⃣ Rank | Rank alternatives — **Rank 1 = Best Choice** |

> **Key Insight:** The closer an alternative is to the ideal best (and farther from the ideal worst), the higher its TOPSIS score.

---

## ✨ Features

- 📁 **Upload CSV** data with alternatives and multiple numeric criteria
- ⚖️ **Assign weights** to reflect the importance of each criterion
- 🎯 **Specify impacts** — mark each criterion as beneficial (`+`) or cost (`-`)
- 📈 **Get ranked results** with TOPSIS scores displayed in a clear table
- 💾 **Download results** as a CSV file

---

## 🛠 Tech Stack

| Library | Purpose |
|---------|---------|
| `NumPy` | Fast vectorized mathematical computations |
| `Pandas` | Robust data loading and manipulation |
| `Streamlit` | Interactive web interface |

---

## 📥 Input / Output Format

### Input

| Parameter | Format | Example |
|-----------|--------|---------|
| **CSV File** | First column = alternative names; remaining columns = numeric criteria | `Fund Name, P1, P2, P3, P4, P5` |
| **Weights** | Comma-separated numbers | `2.3,1.7,3.1,0.9,2.6` |
| **Impacts** | Comma-separated `+` (beneficial) or `-` (cost) | `+,-,+,-,+` |

> ⚠️ **Note:** The number of weights and impacts must match the number of criterion columns.

### Output

The result is your original data with **two additional columns** appended:

| Column | Description |
|--------|-------------|
| `Topsis Score` | Relative closeness coefficient (0 = worst, 1 = best) |
| `Rank` | Final ranking (1 = best alternative) |

### Example Output

| Fund Name | P1 | P2 | P3 | P4 | P5 | Topsis Score | Rank |
|-----------|----|----|----|----|----|--------------|------|
| Zeta | 0.66 | 0.46 | 6.15 | 2.91 | 3.45 | 0.6216 | 1 |
| Eta | 0.81 | 0.59 | 5.15 | 5.81 | 4.98 | 0.5669 | 2 |
| Alpha | 0.72 | 0.51 | 5.83 | 8.41 | 1.23 | 0.5337 | 3 |

---

## 🚀 Installation & Usage

### Prerequisites

```
python >= 3.9
```

### 1. Clone the Repository

```bash
git clone https://github.com/Kumarkashish511/Topsis_Assignment.git
cd Topsis_Assignment
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Web App

```bash
streamlit run app.py
```

Open your browser and navigate to `http://localhost:8501`

### 4. Run via Command Line (CLI)

```bash
python -m Topsis_Main <input_csv> "<weights>" "<impacts>" <output_csv>
```

**Example:**

```bash
python -m Topsis_Main example_data.csv "2.3,1.7,3.1,0.9,2.6" "+,-,+,-,+" output.csv
```

| Argument | Description |
|----------|-------------|
| `input_csv` | Path to your input CSV file |
| `weights` | Comma-separated weight values (quoted) |
| `impacts` | Comma-separated `+` / `-` impacts (quoted) |
| `output_csv` | Path for the output results CSV |

---

## 🌐 Live Demo

> 🚀 **[Launch the Live Web App](https://topsisassignment-hebhatunxspobrx3nzxuip.streamlit.app/)**

> <img width="1430" height="712" alt="image" src="https://github.com/user-attachments/assets/b2a9bb6a-4aba-45ce-bd2b-07d7f9857684" />

---

## 📁 Repository Structure

```
Topsis_Assignment/
│
├── Topsis_Main/          # Core TOPSIS algorithm package
│
├── app.py                # Streamlit web application entry point
├── topsis_web.py         # Web interface helper logic
├── example_data.csv      # Sample input data for testing
│
├── pyproject.toml        # Package build configuration
├── MANIFEST.in           # Package manifest
├── requirements.txt      # Python dependencies
└── LICENSE               # MIT License
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
