GridShield – Cost-Aware Electricity Demand Forecasting
**Project Overview**
GridShield is a data analytics project developed during the DecodeX NLD Synapse 2026 National Hackathon. The goal of this project is to predict electricity demand two days in advance while minimizing financial penalties under the Availability-Based Tariff (ABT) framework used in power grid operations.
In the ABT system, forecasting errors have unequal costs. If the forecast is lower than the actual electricity demand, the penalty is 4 times the deviation, while overestimating demand leads to a 2 times penalty. Because of this asymmetric penalty structure, traditional forecasting approaches that only focus on prediction accuracy are not enough.
This project focuses on building a cost-aware forecasting system that considers both prediction accuracy and financial impact.

**Problem Statement:**
Electricity distribution companies must submit a two-day ahead load schedule to the State Load Dispatch Centre (SLDC). These forecasts are generated at 15-minute intervals, which means 192 forecasts are required for two days.
If the forecast deviates from the actual demand, financial penalties are applied.
The main challenge is to design a forecasting system that:
Reduces financial penalties
Maintains reliable forecasts during peak demand hours
Handles sudden changes or structural demand spikes

**Project Approach:**
The project was developed in three analytical stages.
Stage 1 – Cost-Aware Forecasting
The first stage focused on building a forecasting model that aligns with the ABT penalty structure.
Instead of predicting the average demand, the model predicts a slightly higher value (around the 67th percentile) to reduce the risk of expensive under-forecasting.
Key steps included:
Time-based feature engineering
Lag-based demand patterns
Peak-hour identification
Cost-aware forecasting strategy
This stage produced a stable baseline model with controlled forecast bias and minimized penalty.

Stage 2 – Structural Risk Analysis
In the second stage, the model’s performance was analyzed under different conditions to understand how demand volatility affects forecasting results.
Rolling validation and demand pattern analysis revealed a structural surge event on May 31 during peak hours. This event caused several under-forecast violations and highlighted how sensitive electricity demand forecasting can be during high-demand periods.
Stress testing was also performed by simulating higher peak demand to observe how financial penalties change under extreme scenarios.

Stage 3 – Optimization and Governance Constraints
The final stage focused on meeting operational constraints set by decision-makers.
These constraints included:
Maximum number of peak-hour forecast violations
Bias limits for the forecasting system
A cap on average forecast uplift
A trade-off analysis showed that it was not mathematically possible to satisfy all constraints simultaneously without increasing financial penalties significantly.
Instead of artificially adjusting forecasts, the recommended solution is to combine forecasting with operational strategies such as reserve activation or demand-response mechanisms during extreme demand spikes.

**Technologies Used:**
Python
Pandas
NumPy
Matplotlib
Google Colab
Jupyter Notebook

**Key Insights:**
Forecasting models should consider financial risk, not just prediction accuracy
Electricity demand shows strong daily and weekly patterns
Peak demand periods have the highest financial impact
Extreme demand spikes require operational strategies in addition to forecasting

**Conclusion:**
GridShield demonstrates how data science and financial optimization can be combined to build a smarter electricity demand forecasting system.
By aligning forecasting strategies with real-world penalty structures, the system helps reduce financial risk while maintaining reliable power grid operations.
