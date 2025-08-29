# Time-Series Forecasting: Lorenz System with Feedforward Neural Networks

This repository explores **time-series forecasting** on the chaotic Lorenz system using **fully connected feedforward neural networks**.  
Both **direct multi-step forecasting** and **iterative closed-loop forecasting** strategies are implemented and compared.

---

## Project Overview
- **Lorenz System Simulation**: Synthetic data generated using the Runge-Kutta 4 (RK4) method.
- **Forecasting Approaches**:
  - **Direct Method**: Trains separate models for each prediction horizon (e.g., 1, 5, 10, … steps ahead).
  - **Iterative Method**: Trains a one-step-ahead model and rolls it forward repeatedly in closed loop.
- **Neural Network Implementation**:
  - Custom-built feedforward network with ReLU activations and linear output.
  - Supports **SGD** and **Adam** optimizers.
- **Evaluation**:
  - Root Mean Squared Error (RMSE) for different horizons.
  - Visualization of predictions vs true Lorenz trajectories.

---

## Repository Structure
- `Direct Method.ipynb` → Implements **direct forecasting** for multiple horizons with adaptive windowing.
- `Iterative Method.ipynb` → Implements **iterative closed-loop forecasting** with error accumulation analysis.

---

##  Features
- Lorenz attractor trajectory generation (σ=10, ρ=28, β=8/3).
- Data preparation with sliding windows for supervised learning.
- Manual neural network training loop with:
  - Forward & backward propagation
  - Gradient descent updates (SGD / Adam)
- Performance visualization:
  - Forecasted vs true trajectories across x, y, z dimensions
  - RMSE vs horizon plots

---

## Key Results
- **Direct Method**:
  - Stable performance at short horizons (RMSE_x ≈ 0.13 for 1 step, ≈ 0.27 for 10 steps).
  - Accuracy declines with larger horizons due to compounding dynamics.
- **Iterative Method**:
  - Excellent short-term accuracy (RMSE_x ≈ 0.024 for 1 step).
  - Forecast error grows rapidly with horizon (RMSE_x ≈ 0.28 at 40 steps).

---

## How to Run
1. Clone this repo:
   ```bash
   git clone https://github.com/Aman-Sunesh/Time-Series-Forecasting-Forecasting-the-Lorenz-System-with-Fully-Connected-Feedforward-Networks.git
   cd Time-Series-Forecasting-Forecasting-the-Lorenz-System-with-Fully-Connected-Feedforward-Networks
   ```
2. Install dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn
   ```
3. Open and run the notebooks:
   - `Direct Method.ipynb`
   - `Iterative Method.ipynb`

---

## Example Visualizations
- 3D Lorenz attractor trajectory
- Direct forecast vs true sequence (x, y, z coordinates)
- Iterative forecast degradation over horizon
- RMSE vs horizon plots

---

## Notes
- The models are **pure NumPy implementations** (no PyTorch/TensorFlow).
- Demonstrates the feasibility and limitations of using simple feedforward nets for chaotic system forecasting.
- Could be extended with **RNNs, LSTMs, or Transformers** for improved long-horizon stability.

---

## Author
Developed by **Aman Sunesh**  
- [LinkedIn](https://www.linkedin.com/in/aman-sunesh/)  
- [GitHub](https://github.com/Aman-Sunesh)  

