# Steepest-Descent-and-Newton-s-Method-for-Nonlinear-Minimization

# Nonlinear Function Optimization: Steepest Descent and Newton's Method

This repository contains Python implementations of two fundamental methods for optimizing nonlinear functions:
1. **Steepest Descent (SD)**
2. **Newton's Method**

## Overview

### Steepest Descent (SD)
The Steepest Descent algorithm is an iterative optimization technique that finds the minimum of a function by moving in the direction of the steepest negative gradient. This method is useful for unconstrained optimization problems and is particularly effective when the gradient of the function is available.

Key features:
- Uses the gradient to determine the search direction.
- Iteratively updates the point until a stopping criterion is met (either a maximum number of iterations or a tolerance threshold for convergence).

### Newton's Method
Newton's Method is a second-order optimization algorithm that uses both the gradient and the Hessian matrix (second-order derivatives) to find the minimum of a function. This method converges faster than the Steepest Descent for well-behaved functions, but requires computing and inverting the Hessian matrix.

Key features:
- Utilizes the second-order Taylor expansion of the function for more accurate updates.
- Can achieve faster convergence than gradient-based methods but at the cost of calculating the Hessian matrix.

## How to Run

1. **User Inputs**:
   - `n_var`: Number of variables.
   - `x0`: Initial point as a list of floats.
   - `f`: The function to optimize (entered as a sympy expression).
   - `max_iter`: Maximum number of iterations.
   - `epsilon`: Tolerance level for stopping criteria.

2. **Running the Steepest Descent Algorithm**:
   - The SD method iterates until either the maximum number of iterations is reached or the improvement between steps is less than the defined `epsilon`.
   - The code outputs the solution at each iteration.

3. **Running Newton's Method**:
   - Newton's method solves for the next step by computing the inverse of the Hessian matrix and using it to adjust the current point.
   - The code outputs the solution after each iteration.

## Example

Here is an example output for both methods:

### Steepest Descent (SD):

Using the function $f(x_1, x_2) = 4x_1^2 - 4x_1x_2 + 2x_2^2$

Initial point: $[2, 3]$

Epsilon (ε): $1e-5$

Max Iterations: $3$

Steepest Descent by ε:

        Step 1 : [0, 1.00000000000000]
        
        Step 2 : [0.400000000000000, 0.600000000000000]
        
        Step 3 : [-1.11022302462516e-16, 0.200000000000000]
        
        Step 4 : [0.0800000000000000, 0.120000000000000]
        
Steepest Descent by iteration:

        Step 1 : [0, 1.00000000000000]
        
        Step 2 : [0.400000000000000, 0.600000000000000]
        
        Step 3 : [-1.11022302462516e-16, 0.200000000000000]

### Newton's Method:

Using the function $f(x_1, x_2, x_3) = (40(1/(x_1x_2x_3)))+(40*(x2*x3))+(10*(x1*x2))+(20*(x1*x3))$

Initial point: $[2, 3]$

Epsilon (ε): $10^(-5)$

Max Iterations: $3$

 Step 1 : $[0, 1.00000000000000]$
 
 Step 2 : $[0.400000000000000, 0.600000000000000] 

Final solution: $[0.0, 0.0]$ after 10 iterations.

## License
This project is licensed under the MIT License - see the LICENSE file for details.
