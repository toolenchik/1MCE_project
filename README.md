# Title: Genetic History of First Millennium CE Populations in Central Asia

This repository contains the scripts and parameter files for the 1MCE project, which uses unpublished and published ancient genomes (the Allen Ancient DNA Resource (AADR v66)) to study the genetic ancestry of individuals from Central Asia dated to the first millennium CE. The analyses: Principal component analysis (smartpca) projects ancient individuals onto present-day genetic variation, ADMIXTURE estimates ancestry proportions without a predefined model, and qpAdm tests explicit admixture models with rotating sets of sources. Genotype data are not included.

## Project context

- Project: 1MCE, Genetic History of First Millennium CE Populations in Central Asia
- Institution: The University of Texas at Austin, Genetical Anthropology Lab

## Repository structure
1MCE/
--data/
--pca/
--admixture/
--qpadm/

## Dependencies

- GNU bash, version 3.2.57(1)-release (arm64-apple-darwin24)
- Python 3.14.7 
- EIGENSOFT 8.0 (smartpca, convertf)
- ADMIXTOOLS 7.0,(qpAdm)
- ADMIXTURE 1.3.0
- PLINK 1.9
- awk, sed, sort, grep, wc
- Linux HPC cluster with SLURM

Run the PCA and export the results for plotting:

```
sbatch pca/run_smartpca.sh
bash pca/evec_to_datagraph.sh pca/results/1MCE_HO.evec > pca/results/pca_datagraph.tsv
```

Run ADMIXTURE for K = 2 to 10 (10 seeds per K) and summarize the runs:

```
sbatch --array=2-10 admixture/run_admixture.sh
bash admixture/summarize_runs.sh
```

Test one qpAdm model, then collect the results from all models:

```
sbatch qpadm/run_qpadm.sh qpadm/models/01.par
bash qpadm/summarize_qpadm.sh qpadm/models
```
## Data

- AADR v66, Source: https://reichdata.hms.harvard.edu/pub/datasets/amh_repo/curated_releases/index.html
  - 1240k panel for qpAdm
  - Human Origins (HO) panel for PCA
  - .anno  metadata file for sample QC

## Author

Sai T
