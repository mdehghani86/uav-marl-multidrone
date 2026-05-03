# Cooperative Multi-Drone Routing via Attention-Based MARL

Code-companion site for the manuscript

> **Cooperative Multi-Drone Routing under Deadlines and Battery Constraints
> via Attention-Based Multi-Agent Reinforcement Learning.**
> Mohammad Dehghani, Northeastern University, 2026 (under review at *Expert
> Systems with Applications*).

🌐 **Live site:** [https://mdehghani86.github.io/uav-marl-multidrone/](https://mdehghani86.github.io/uav-marl-multidrone/)
📄 **Paper PDF:** [paper.pdf](paper.pdf)

## Headline result

A trained attention-based MARL agent (v3.4-bc) beats the strongest classical
dispatching heuristic (auction + battery-aware nearest-neighbour, H3) by
**+4.38% in mean total reward** on a 17-cell saturation grid (4250 evaluation
episodes per method, five seeds), while recording **zero battery-depletion
crashes** and discriminating premium-tier customers **1.97× more sharply**
than the heuristic.

## What's in this repo

| Path | Contents |
|---|---|
| `index.html` | Project landing page with figure viewer + comparison table |
| `paper.pdf` | Compiled manuscript |
| `figures/fig1_heuristic_comparison.html` | Per-cell heuristic baseline comparison |
| `figures/fig2_column_chart.html` | Headline KPI bar chart |
| `figures/fig3_training_curves.html` | Convergence curves by Attn-MARL version |
| `figures/fig4_architecture.html` | Attention multi-agent policy architecture |
| `figures/fig5_env_diagram.html` | Environment diagram |
| `figures/fig6_scenario_heatmap.html` | Per-cell reward heatmap |
| `data/saturation_summary_v3_1.csv` | Per-method aggregate KPIs (raw) |

## Method summary

Five incremental design improvements move an attention-based MARL agent from
a –25% deficit to a +4.38% lead over the strongest heuristic on the same
scenario grid:

1. **Battery-feasibility action mask** — eliminates 1.78 crashes/ep
2. **Per-customer cost-and-slack features** — closes the gap to heuristics
3. **Behaviour-cloning warm start + dual-pool critic + reward-and-deadline-
   weighted PBRS** — adds another +2.5pp
4. **Inter-drone coordination feature** — final +1pp lift to +4.38%

## Reproducing the experiments

The training and evaluation code lives in the parent research repository
(internal), which uses the SimPy + Stable-Baselines3 + sb3-contrib stack on
Northeastern's Explorer cluster. The numbers in `data/saturation_summary_v3_1.csv`
are the canonical aggregate over 4250 evaluation episodes per method.

## Status & roadmap

- Headline experimental grid complete (17 cells × 5 seeds × 50 ep = 4250 ep / method)
- Manuscript draft complete (385-line LaTeX, ESWA format)
- Sensitivity studies queued: fleet-size scaling, customer-count + zero-shot
  transfer to larger N, online customer arrivals, reward-tier proportions

## License

MIT for code; figures and PDF © 2026 Mohammad Dehghani; quote with citation.

## Contact

Mohammad Dehghani · m.dehghani@northeastern.edu
