# Aave V2 Wallet Credit Scoring System

## Project Overview
This project implements a machine learning-based credit scoring system for wallets interacting with the Aave V2 protocol. The system analyzes historical transaction behavior to assign credit scores between 0 and 1000 to each wallet, where higher scores indicate more reliable and responsible usage patterns.

## Method Chosen
The solution uses a Random Forest Regressor model to generate credit scores based on engineered features from transaction data. This choice was made due to:
- Ability to handle non-linear relationships in transaction patterns
- Robustness against outliers
- Feature importance ranking capabilities
- Good performance with numerical features

## Architecture
1. **Data Loading**: JSON transaction data is loaded and parsed using pandas
2. **Feature Engineering**:
   - Transaction frequency metrics
   - Action type ratios (deposit/borrow/repay)
   - Amount-based features
   - Temporal behavior patterns
   - Risk indicators
3. **Data Processing**:
   - Feature aggregation per wallet
   - Normalization/scaling
   - Missing value handling
4. **Model Training**:
   - Random Forest Regressor
   - Feature importance analysis
   - Score calibration to 0-1000 range
5. **Output Generation**:
   - Wallet scores
   - Distribution analysis
   - Behavioral insights

## Processing Flow
1. Load raw transaction data from JSON file
2. Clean and preprocess transaction records
3. Engineer features per wallet
4. Normalize and prepare features for modeling
5. Train and validate model
6. Generate and calibrate wallet scores
7. Save results and analyze score distribution

## Usage
1. Ensure all requirements are installed:
   ```bash
   pip install -r requirements.txt
   ```
2. Run the Jupyter notebook:
   ```bash
   jupyter notebook wallet_credit_scoring.ipynb
   ```

## Requirements
- Python 3.8+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

The detailed analysis of the scoring results can be found in [analysis.md](analysis.md).
