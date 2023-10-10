# HJ_solver_PDHG
This is an algorithm for solving Hamilton-Jacobi PDEs (where the Hamiltonian is convex with respect to the momentum) using optimization methods. 
For more details, see the paper "Primal-dual hybrid gradient algorithms for computing time-implicit Hamilton-Jacobi equations".

To test the examples in the paper, run the following two lines:
1. Run the main algorithm
  - Code: python3 run_example.py --ndim 1 --epsl 0 --egno 1 --nx 20 --ny 20 --nt 5 --stepsz_param 0.1 --c_on_rho 100 > out.log 2>&1 &
  - Meaning of flags: ndim for dimension of the problem; epsl for the diffusion coefficient; egno for the example number; nx, ny, nt for the grid numbers;
                    stepsz_param for the stepsize in PDHG; c_on_rho for the parameter c in the paper. (For more flags, see the file run_example.py)
2. Plot and compute errors
  - Code: python3 plot_soln.py --ndim 1 --parent_folder Example --egno 1 --epsl 0 --numerical_sol_filename filename.pickle > out_plot.log 2>&1 &
  - Meaning of flags: ndim, egno, epsl are the same with last line; parent_folder is the parent folder we want to save files to;
                    numerical_sol_filename is the filename where we save the numerical solution to (you can find it in the log file in step 1).
  - To compute the error and plot solution, see print_n_plot.py

If you found this useful, please cite our paper:
Meng, T., Hao, W., Liu, S., Osher, S. J., & Li, W. (2023). Primal-dual hybrid gradient algorithms for computing time-implicit Hamilton-Jacobi equations. arXiv preprint arXiv:2310.01605.
