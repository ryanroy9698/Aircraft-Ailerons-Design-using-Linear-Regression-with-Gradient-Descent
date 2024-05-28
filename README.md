# Aircraft Ailerons Design using Linear Regression and Gradient Descent

The dataset used in this project contains 13750 instances with 40 features describing the airplane's status. The goal is to predict the 'Goal' column, which represents a command that our controller should issue to manage the ailerons of an aircraft. This project implements linear regression using direct solution, full batch gradient descent, and mini-batch gradient descent to achieve this.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Preparation](#data-preparation)
3. [Linear Regression Using Direct Solution](#linear-regression-using-direct-solution)
4. [Full Batch Gradient Descent](#full-batch-gradient-descent)
5. [Mini-Batch and Stochastic Gradient Descent](#mini-batch-and-stochastic-gradient-descent)
6. [Gradient Descent Learning Rate Optimization](#gradient-descent-learning-rate-optimization)
7. [Final Model Selection](#final-model-selection)
8. [Conclusion](#conclusion)
9. [Usage](#usage)

## Project Overview
This project aims to design a controller for aircraft ailerons using supervised learning techniques, specifically linear regression. The dataset used consists of 13750 instances and 40 features, with the target being the 'Goal' column.

## Data Preparation
The dataset is split into training (70%), validation (15%), and test (15%) sets. The data is then standardized to have a mean of zero and a standard deviation of one. The first column of all 1s is inserted into the training, validation, and test sets to account for the bias term in linear regression.

## Linear Regression Using Direct Solution
We implemented the direct solution for linear regression using matrix inversion. The Root Mean Squared Error (RMSE) was calculated for both the training and validation sets.

## Full Batch Gradient Descent
We implemented a full batch gradient descent algorithm with a fixed learning rate of 0.01. The model was trained until the RMSE on the validation set converged to within 1.001 times the RMSE of the direct solution. Training time and RMSE values for both training and validation sets were recorded and analyzed.

## Mini-Batch and Stochastic Gradient Descent
We wrote a function to perform mini-batch gradient descent until the convergence threshold was reached. Various batch sizes were tested to observe their effect on convergence. Plots were created to show RMSE vs. epoch, RMSE vs. time, and total training time vs. batch size.

## Gradient Descent Learning Rate Optimization
We investigated the effect of learning rate on convergence by testing different learning rates for batch sizes that did not initially converge. Optimal learning rates were found for these batch sizes, and the results were reported in a table. Further, the best batch size based on the fastest convergence time was selected, and a range of learning rates were tested.

## Final Model Selection
Based on the findings from the previous parts, we selected the best model and evaluated it on the test set. The model settings and performance metrics were summarized.

## Conclusion
The mini-batch gradient descent method with a batch size of 64 and a learning rate of 0.01 performed the best. This method achieved a low RMSE on the validation set and had efficient training times, making it suitable for real-time applications.

## Usage

### Prerequisites
- Python 3.x
- Scikit-learn
- Numpy
- Matplotlib

### Running the Code
1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/aircraft-ailerons-design.git

2. Navigate to the project directory:
    ```bash
    cd aircraft-ailerons-design
    ```
3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```
4. Run the Jupyter Notebook or Python script to perform feature selection, model training, and evaluation:
    ```bash
    jupyter notebook ailerons_design.ipynb
    ```
