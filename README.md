## 📈 Scenario Based Sales Forecasting with Synthetic Evaluations

A modular ML framework that combines predictive modeling with simulation-based evaluation using synthetic future data.

This project is designed to model sales and profit using real historical data (left side) and assess model performance under various hypothetical scenarios using synthetic data (right side). This dual-model approach enables robust, forecasting when actual future outcomes are unavailable.

---

## 🧠 Key Features
- 🔄 **Synthetic Data Generation**
   Learn market dynamics by simulating future delivery, pricing, or supply chain disruptions.

- 📊 **ML Forecasting Model**
   Predict sales and profit using structured temporal, categorical, and financial features.

- 🧪 **Scenario Based Simulation**
   Evaluate model sensitivity under user-defined market shocks (e.g., bullwhip effect, overstock, supply disruption).

- 🔁 **Retraining Loop**
   Improve model reliability using simulation-driven retraining on synthetic deviations.

---

## 🔬 ML & Simulation Process Flow

1. **Historical Data Ingestion**
   - Real data from 4 years used to train baseline models.
   - Preprocessing includes:
     - Temporal feature engineering (lag, rolling means, day of week, month)
     - Z-score normalization & outlier handling
     - Categorical encoding and interaction features

2. **Left Side Forecasting Model (EGA Core)**
   - Model: RandomForestRegressor
   - Target Variables: Sales (log-transformed), Profit
   - Features:
     - Order & shipment dates
     - Discount levels, state/month interactions
     - Rolling sales, lag features, log-sales
   - Train/Test Split: Based on time (<= 2021 vs >= 2022)
   - Evaluation Metrics: MSE, R²

3. **Right Side Synthetic Data Generation**
   - Purpose: Simulate future trends (e.g., 2022–2023) using a “what-if” logic
   - Scenarios Supported:
     - 🟠 Bullwhip (demand spikes)
     - 🔵 Market Clash (sudden drops)
     - 🟣 Overstock (delay + excess)
     - 🔴 Supply Chain Disruption (shipment delays)
   - Method:
     - Apply multipliers or shocks to test set features (e.g., lag sales, delay, volume)
     - Use same feature schema as left-side model

4. **Scenario Evaluation & Visualization**
   - Predict performance under each scenario
   - Visualize actual vs simulated predictions:
     - Sales & profit line charts
     - Scenario overlays
   - Compare model sensitivity across extreme conditions

5. **Error Feedback & Retraining**
   - Use scenario-based deviations to refine the base model
   - Track residual patterns for:
     - Hyperparameter tuning
     - Feature re-weighting

