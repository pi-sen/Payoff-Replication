
Replication Strategy for Buffered PLUS Securities
=================================================

📈 Overview
-----------
This project implements a replication strategy for a structured product known as Buffered PLUS Securities, which is linked to the performance of the S&P 500 index. The objective is to construct a portfolio using bonds, European put options, and a digital put to closely replicate the note's payoff structure using real market data.

💡 Key Features
---------------
- Structured Note Modeling using fixed income and derivative instruments
- Payoff replication using:
  - Zero-coupon bonds
  - European puts (at varying strikes)
  - Digital put option
- Market Data Integration via Bloomberg:
  - SOFR-based risk-free rates
  - Implied volatility surface
  - SP500 dividend yield
- Sensitivity Analysis to assess pricing effects of changing forward rates and volatility
- Pricing Accuracy with close alignment to term sheet values (estimated price: $957.04 vs term sheet: $970.30)

🛠️ Instruments Used
--------------------
| Instrument        | Type         | Strike Price ($) |
|------------------|--------------|------------------|
| Zero-Coupon Bond | Long         | Face Value: 1175 |
| European Put     | Short        | 6696.29          |
| European Put     | Long         | 5996.66          |
| European Put     | Short        | 5396.99          |
| Digital Put      | Short        | 5396.99          |

📊 Data Sources
---------------
- Bloomberg Terminal for:
  - Implied volatility surface
  - SP500 continuous dividend yield
  - SOFR rates (swap discount factors)

🧠 Methodology
--------------
- Calculated risk-free rates via log-discounting from Bloomberg SOFR data
- Used Black-Scholes model to value vanilla options
- Approximated digital option price using its European equivalent
- Constructed replicating portfolio based on payoff decomposition and delta matching

📁 Repository Structure
-----------------------------------
/replication-buffered-plus/
│
├── data/                  # Contains raw market data
├── src/                   # Python or MATLAB/R scripts
├── results/               # Output reports, charts
├── screenshots/           # Bloomberg terminal outputs
├── Replication_Report.pdf # Final report
└── README.txt             # This file

📌 Authors
----------
- Piyush Sen
- Srikari Rallabandi
- Aastha Shah

📄 License
----------
MIT License (or your preferred open-source license)
