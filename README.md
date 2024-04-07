This MATLAB code computes an optimal feedback controller for the Kuramoto Sivashinsky Equation with zero Dirichlet and Neumann boundary conditions, discretised using finite differences. 
The objective to minimize is the space-time averaged energy.
 
Gradient descent is used to compute the optimum controller. The derivatives of the objective function w.r.t the feedback matrix elements are provided by the function 'MSS', which uses 
adjoint Preconditioned Multiple Shooting Shadowing (PMSS)* to compute all derivatives simultaneously. The time stepper ODE45 is used to integrate the non-linear, linearised and adjoint equations. 
The function 'svds' is used to compute the singular value decomposition of the state transition matrices (for computing a block diagonal preconditioner that speeds up the iterative solution to the linear matrix system). 
GMRES is used for the iterarive solution to the PMSS matrix system (in MATVEC form). 
 
The code outputs the uncontrolled solution contour, and the objective on each iteration. Upon convergence of the algorithm, the controlled solution contour is also plotted, as well as the feedback matrix

 * https://royalsocietypublishing.org/doi/10.1098/rspa.2020.0322
