# ADMIXTURE

- run_admixture.sh: SLURM array job that runs ADMIXTURE with --cv and 10 random seeds for each K. Usage: `sbatch --array=2-10 admixture/run_admixture.sh`
- summarize_runs.sh: Keeps the run with the best log-likelihood for each K and writes `results/cv_table.tsv` (K, best log-likelihood, CV error). Usage: `bash admixture/summarize_runs.sh`

