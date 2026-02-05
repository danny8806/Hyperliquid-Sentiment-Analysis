# Hyperliquid Trader Behavior vs Market Sentiment

This project analyzes how Bitcoin market sentiment (Fear & Greed Index) influences trader behavior and performance on the Hyperliquid exchange.  
The goal is to uncover actionable patterns that can inform smarter trading and risk management strategies.

---

## 📌 Project Objective

Study the relationship between market sentiment and:

- **Trader performance**: PnL, win rate, drawdown proxy  
- **Trader behavior**: trade frequency, position size, leverage proxy, long/short bias  
- Identify behavioral trader segments  
- Derive actionable trading rules of thumb  

---

## 📂 Repository Structure

Hyperliquid-Sentiment-Analysis/
│
├── data/
│   ├── fear_greed_index.csv        # Bitcoin Fear & Greed Index
│   └── historical_data.csv         # Hyperliquid trade-level data
│
├── notebooks/
│   └── PrimeTradeAi_Final.ipynb    # Complete analysis notebook
│
├── outputs/
│   └── *.png                       # Generated charts & tables
│
├── README.md                       # Project overview & instructions
│
└── Trader Behavior vs Market Sentiment summary.pdf   # One-page summary



## 🧪 Datasets Used

### 1. Bitcoin Fear & Greed Index
- **Columns**: `date`, `classification`, `fg_value`  
- Represents overall market sentiment on a daily basis  

### 2. Hyperliquid Historical Trader Data
Trade-level data including:  
- `account`, `symbol`, `side`  
- `trade size`, `execution price`  
- `closed PnL`, `timestamps`, etc.  


## 🧠 Methodology (High-Level)

### Data Preparation
- Loaded both datasets  
- Converted timestamps and aligned data at daily granularity  
- Merged sentiment data with trading data by date  

### Feature Engineering
Daily metrics per trader:
- Daily PnL  
- Win rate  
- Trades per day  
- Average trade size  
- PnL volatility (drawdown proxy)  
- Long/short ratio  
- Leverage proxy  

Both **mean** and **median** statistics were computed due to heavy-tailed distributions.  

### Analysis
- Compared performance and behavior across sentiment regimes  
- Created trader segments:  
  - High vs Low risk exposure  
  - Frequent vs Infrequent traders  
  - Consistent vs Inconsistent profitability  

### Modeling (Optional Bonus)
- Built a simple predictive model using sentiment + behavior features  
- Evaluated using accuracy, F1-score, and ROC-AUC  

---

## 📊 Key Outputs

Sentiment-wise comparison of:
- PnL (mean vs median)  
- Volatility (risk proxy)  
- Win rate  
- Trade frequency  
- Position size  
- Directional bias  

Segment-level performance analysis and actionable strategy recommendations.  

All plots and tables are saved in the `outputs/` directory and embedded in the notebook.  

---

## ⚙️ Setup Instructions

### 1️⃣ Create Conda Environment (Recommended)
```bash
conda create -n primetrade python=3.10
conda activate primetrade
2️⃣ Install Dependencies
bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
(All libraries used are standard and widely available.)

▶️ How to Run the Project
Clone the repository:

bash
git clone https://github.com/danny8806/Hyperliquid-Sentiment-Analysis.git
cd Hyperliquid-Sentiment-Analysis
Ensure datasets are placed inside the data/ folder:

Code
data/
 ├── fear_greed_index.csv
 └── historical_data.csv
Launch Jupyter Notebook:

bash
jupyter notebook
Open and run:

Code
notebooks/PrimeTradeAi_Final.ipynb
Run all cells top-to-bottom to reproduce results.