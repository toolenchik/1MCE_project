# PCA (smartpca)

- smartpca.par: Parfile that computes PCs on present-day populations and projects ancient individuals (lsqproject: YES).
- modern_pops.txt: HO populations used to compute the PCs.
- run_smartpca.sh: SLURM job that runs smartpca and writes `.evec` and `.eval` files. Usage: sbatch pca/run_smartpca.sh
- evec_to_datagraph.sh: Converts the `.evec` file to a tab-delimited table (ID, Group, PC1 to PC4, Projected) for DataGraph. Usage: bash pca/evec_to_datagraph.sh <file.evec>
