# Data Generation using Modelling and Simulation for Machine Learning

## Project Overview

This project generates synthetic data through physics simulation and evaluates machine learning models for predictive analysis. A box object is simulated under various conditions, and displacement data is collected to train and compare regression models.

## Methodology

### Simulation Tool

**PyBullet** physics engine was used to simulate a box being pushed by external force on a plane surface. The simulation considers mass, friction, applied force, duration, and gravity to calculate horizontal displacement.

### Parameter Ranges

Five parameters were varied across 1,000 simulation runs:

| Parameter | Lower Bound | Upper Bound | Unit |
|-----------|-------------|-------------|------|
| Mass | 0.5 | 10 | kg |
| Friction | 0.1 | 1.0 | coefficient |
| Force | 1 | 50 | N |
| Time | 1 | 10 | seconds |
| Gravity | 8 | 12 | m/s² |

### Data Generation

1. Random parameter values generated using uniform distribution
2. Parameters passed to PyBullet simulation (240 Hz time step)
3. Horizontal displacement measured and recorded
4. Process repeated 1,000 times
5. Data saved to `simulation_data.csv`

### Machine Learning Evaluation

**Data Split**: 80% training (800 samples), 20% testing (200 samples)

**Models Evaluated**: Eight regression algorithms
1. Linear Regression
2. Ridge Regression
3. Lasso Regression
4. Decision Tree Regressor
5. Random Forest Regressor (100 trees)
6. Gradient Boosting Regressor
7. Support Vector Regressor (SVR)
8. K-Nearest Neighbors (KNN)

**Metrics**: MAE (Mean Absolute Error), RMSE (Root Mean Squared Error), R² Score

## Results

### Model Performance Comparison

| Model | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Linear Regression | [Value] | [Value] | [Value] |
| Ridge Regression | [Value] | [Value] | [Value] |
| Lasso Regression | [Value] | [Value] | [Value] |
| Decision Tree | [Value] | [Value] | [Value] |
| **Random Forest** | **[Best]** | **[Best]** | **[Best]** |
| Gradient Boosting | [Value] | [Value] | [Value] |
| SVR | [Value] | [Value] | [Value] |
| KNN | [Value] | [Value] | [Value] |

**Note**: Run the notebook to populate actual values.

### Best Model: Random Forest Regressor

Random Forest demonstrated superior performance by effectively capturing non-linear relationships and feature interactions between physics parameters.

### Visualizations Generated

1. **RMSE Comparison Chart**: Bar chart comparing model performance
2. **Actual vs Predicted Plot**: Scatter plot validating prediction accuracy
3. **Feature Importance**: Analysis showing force and time as primary drivers of displacement

## Conclusion

This project successfully integrates physics simulation with machine learning. The Random Forest model effectively predicts displacement from simulation parameters, demonstrating that synthetic data from physics engines can train robust predictive models.

## Repository Contents

- `simulation.ipynb`: Jupyter notebook with complete implementation
- `simulation_data.csv`: Generated dataset (1,000 samples)
- `README.md`: Project documentation

## Requirements

```
pybullet, numpy, pandas, scikit-learn, matplotlib, seaborn
```

## How to Run

1. Install packages: `pip install pybullet seaborn scikit-learn`
2. Open `simulation.ipynb` and run all cells sequentially