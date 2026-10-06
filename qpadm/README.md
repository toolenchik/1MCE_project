# qpAdm (classic ADMIXTOOLS)

- qpadm_template.par: Parfile template (details: YES, allsnps: [YES or NO])
- right.txt: Right populations shared by all models (refs)
- models/: One parfile and left-population list per model (target first, then sources)
- run_qpadm.sh: SLURM job that runs qpAdm for all models. Usage: sbatch qpadm/run_qpadm.sh 
- summarize_qpadm.sh: Collects the tail p-value, admixture weights, standard errors and feasibility for every model into `results/qpadm_summary.tsv`, without filtering by p-value. Usage: `bash qpadm/summarize_qpadm.sh qpadm/`
