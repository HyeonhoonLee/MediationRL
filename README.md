# A Reinforcement Learning Framework for Dynamic Mediation Analysis

This repository is the official implementation of the paper [A Reinforcement Learning Framework for Dynamic Mediation Analysis]()(ICML 2023) in Python. 

>📋  **Abstract**: Mediation analysis learns the causal effect transmitted via mediator variables between treatments and outcomes and receives increasing attention in various scientific domains to elucidate causal relations. Most existing works focus on point-exposure studies where each subject only receives one treatment at a single time point. However, there are a number of applications (e.g., mobile health) where the treatments are sequentially assigned over time and the dynamic mediation effects are of primary interest. Proposing a reinforcement learning (RL) framework, we are the first to evaluate dynamic mediation effects in settings with infinite horizons. We decompose the average treatment effect into an immediate direct effect, an immediate mediation effect, a delayed direct effect, and a delayed mediation effect. Upon the identifiability of each effect component, we further develop robust and semi-parametrically efficient estimators under the RL framework to infer these causal effects. The superior performance of the proposed method is demonstrated through extensive numerical studies, theoretical results, and an analysis of a mobile health dataset.

## Learners for Nuisance Functions
1. `probLearner.py`: code to learn density functions, including $r$, $p_m$, and $\pi_b$.
2. `qLearner_Linear.py`: code to learn all $Q$ functions and $\eta$.
3. `ratioLearner.py`: code to learn state ratios, including $\omega^{\pi_e}$, $\omega^{\pi_0}$, and $\omega^{G_0}$.
4. `evaluator_Linear.py`: major code to infer all effect components, including implementations of MR, MIS and DM estimators.

## Other Functions in the Main Folder
1. `_util.py`: helper functions.
2. `policy.py`: example functions to define random policies.
3. `plot.py`: functions used to plot results.

## Scripts to Conduct Experiments
1. `/Toy_1`: There are all code files used for the toy example I, showing the robustness of MR estimators. `toy_example.py` is the corresponding experiment script.
2. `/Toy_2`: There are all code files used for the toy example II, showing the necessity of taking the state transition into account. `toy_example2_iid.py` and `toy_example2_w_S.py` are the corresponding experiment scripts.
3. `/Semi_Synthetic`: There are all code filed used for the semi-synthetic experiments, showing the superior performance of MR estimators. `estimate.py` and `estimate_T.py` are the corresponding experiment scripts.
4. `/Real_Case_Study`: There are codes used in the real case study, including algorithms learning $Q$ function for the behavior policy, from which we obtain the optimal policy. Further, a cross validation script used to get effect estimation for optimal policy is provided.
5. `/Additional_Numerical_Results`: There are codes used in the additional numerical analysis.

## Others
1. `/Natural Decomposition`: Within the folder, we provide codes related to the alternative effect decomposition discussed in Appendix B.

## Steps to Reproduce the Experiments Results
1. Download all the codes in the folder corresponding to the experimentation;
2. Run the experiment script to get the experiment results;
3. Analyze the results and get the figure by running the corresponding code in either `Toy_example.ipynb` or `Summary.ipynb`, whichever is included in the folder.

## Citations
Please cite the following publications if you make use of the material here.
- Ge, L., Wang, J., Shi, C., Wu, Z., & Song, R. (2023). A Reinforcement Learning Framework for Dynamic Mediation Analysis. arXiv preprint arXiv:2301.13348.

```
@article{ge2023reinforcement,
  title={A Reinforcement Learning Framework for Dynamic Mediation Analysis},
  author={Ge, Lin and Wang, Jitao and Shi, Chengchun and Wu, Zhenke and Song, Rui},
  journal={arXiv preprint arXiv:2301.13348},
  year={2023}
}
```
## License

All content in this repository is licensed under the MIT license.
