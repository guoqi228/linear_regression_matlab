# linear_regression_matlab

## Simple Linear Regression

### 1. View the dataset
![Dataset]( https://raw.githubusercontent.com/guoqi228/linear_regression_matlab/master/fig_1_data.png )

### 2. Gradient descend
```
for iter = 1:num_iters
  error = X'*(X*theta - y);
  theta = theta - alpha/m*error;
  J_history(iter) = computeCost(X, y, theta);
end
```

### 3. Compute cost function
```
error = X*theta - y;
J = sum(error.*error)/(2*m);
```

### 4. Linear fit
![Linear fit]( https://raw.githubusercontent.com/guoqi228/linear_regression_matlab/master/fig_2_linear_fit.png )

### 5. Visualize cost function
![Cost function - surf]( https://raw.githubusercontent.com/guoqi228/linear_regression_matlab/master/fig_3_cost.png )
![Cost function - contour]( https://raw.githubusercontent.com/guoqi228/linear_regression_matlab/master/fig_4_cost_2.png )

## Multiple Linear Regression

### 1. Feature normalization
```
mu = mean(X);
sigma = std(X);
n = length(mu);
for i = 1:n
    X_norm(:,i) = (X(:,i) - mu(i))/sigma(i);
end
```

### 2. Gradient descent
```
for iter = 1:num_iters
    error = X'*(X*theta - y);
    theta = theta - alpha/m*error;
    % Save the cost J in every iteration    
    J_history(iter) = computeCostMulti(X, y, theta);
end
```

### 3. Convergence vs learning rate
![Cost function - Learning rate]( https://raw.githubusercontent.com/guoqi228/linear_regression_matlab/master/fig_5_gradient_descend.png )

### 4. Normal equation (closed form solution)
```
theta = pinv(X'*X)*X'*y;
```

