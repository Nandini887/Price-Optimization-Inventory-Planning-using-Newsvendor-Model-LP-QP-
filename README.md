# Price-Optimization-Inventory-Planning-using-Newsvendor-Model-LP-QP-
Built a data-driven optimization model combining regression and linear/quadratic programming to determine optimal pricing and inventory decisions under uncertain demand, improving expected profit and operational efficiency.

## Overview
This project extends the classical Newsvendor Model by incorporating price-dependent demand and asymmetric cost structures to optimize both pricing and inventory decisions.

The goal is to determine:
- Optimal quantity to produce
- Optimal price to maximize expected profit under uncertain demand


## Problem Statement
Traditional inventory models assume fixed demand distributions and prices. However, in real-world scenarios:
- Demand depends on price (price elasticity)
- Costs are asymmetric (stockouts vs overstock)

This project builds a data-driven framework to address both challenges.


## Approach

### 1. Demand Modeling
- Built a linear regression model to estimate demand as a function of price  
- Captured randomness using residuals to simulate realistic demand scenarios :contentReference[oaicite:0]{index=0}  

### 2. Scenario Generation
- Generated 99 demand scenarios using regression + residuals  
- Standardized demand at fixed price for optimization  

### 3. Fixed Price Optimization (Linear Programming)
- Optimized production quantity using LP  
- Considered:
  - Production cost
  - Rush order cost
  - Disposal cost  

Result:
- Optimal quantity: ~472 units  
- Expected profit: ~$231/day :contentReference[oaicite:1]{index=1}  

---

### 4. Joint Price & Quantity Optimization (Quadratic Programming)
- Modeled demand as a function of price  
- Solved a QP to jointly optimize price and quantity  

Result:
- Optimal price: ~$0.95  
- Optimal quantity: ~535 units  
- Profit improvement: +1.27% :contentReference[oaicite:2]{index=2}  

---

### 5. Model Validation (Bootstrap Analysis)
- Performed 200 bootstrap simulations  
- Verified stability of optimal decisions  

Key Insight:
- Optimal price and quantity remained consistent across samples  
- Model is robust and reliable  



## Key Insights
- Lowering price slightly increases demand significantly (price elasticity)
- Optimal inventory is below mean demand due to asymmetric costs
- Joint optimization outperforms traditional models consistently  
- Data-driven pricing leads to measurable profit improvement  

---

## Tech Stack
- Python (NumPy, Pandas)
- Optimization: Gurobi
- Statistical Modeling: Regression (OLS)
- Visualization: Matplotlib / Seaborn  



## Business Impact
- Improved profit through better pricing + inventory decisions  
- Reduced risk of overstock and stockouts  
- Enabled data-driven decision-making under uncertainty  
