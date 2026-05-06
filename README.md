# Diffusion with finetuned ESM-2 surrogate scorer for antibody design
Phase 0: Benchmarking fitness ablations to select a surrogate scorer. Ablations over mean, sequence, ESM-2 + ridge regression, AbMNPP + ridge regression, ESM-2 + MLP head, computing Spearman, Pearson, RMSE, etc. (ESM-2 w/ ridge regression achieved highest Spearman). Dataset used is AbMAP (Koenig binding, Koenig expression, Warszawski binding)
Phase 1: ESM-2 60M model finetuned on AbMAP datasets for improved antibody fitness prediction. ESM-2 (35M) hyperparameter ablation performed to select most optimal configuration to train 650M model
Phase 2: Generate HER2-targeting candidates via RFdiffusion and ProteinMPNN
Phase 3: Compute Pareto-front scores for top scoring reranked ESM-2 candidates over predicted binding and developability
Phase 4: Independent validation using Chai-1 to evaluate top reranked candidates against a random baseline using ipTM and pTM scores
