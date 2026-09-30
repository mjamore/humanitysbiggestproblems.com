# Launch Flagship Candidate Research

Status checked: 2026-09-15

## Decision summary

The founder approved this 13-candidate slate for detailed seed drafting on 2026-09-15. Approval is not final publication: each candidate must still pass the source and acceptance-criteria audit described below.

Recommended launch slate:

- **Mathematics (4):** Riemann Hypothesis; Hodge Conjecture; Birch and Swinnerton-Dyer Conjecture; Yang-Mills Existence and Mass Gap.
- **Natural science (5):** neutrino mass ordering; leptonic CP violation; absolute neutrino mass scale; resolve the Hubble-tension discrepancy; demonstrate ambient-pressure room-temperature superconductivity.
- **Computer science (4):** P versus NP; Unique Games Conjecture; existence of classical one-way functions; polynomial-time Graph Isomorphism.

These candidates have authoritative formulations, current evidence that they remain open, objectively reviewable outcomes, and established research programs that can become Research Directions. Before publication, the initial Site Moderator must produce a procedural Seed Audit Report showing that every numerical confidence, systematic-error, benchmark, and independence requirement comes from authoritative Sources rather than founder judgment. This is not expert endorsement; the eventual Committee must adopt or replace the seed before scientific promotion can occur.

## Assessment method

`Strong` means the candidate passes all five launch criteria:

1. currently unresolved;
2. authoritatively documented;
3. precise enough for a seed definition;
4. objectively verifiable; and
5. meaningfully decomposable.

`Conditional` means the underlying question is important and open, but a Steward/Committee must narrow the claim or validation boundary before it can become a Problem. `Exclude` means it should not launch as an unquestionably open Problem.

For proof problems, verification means a proof or counterexample addressing the exact formal statement. For empirical science, it means independently reproducible evidence under a predeclared statistical and systematic-error standard; conclusions remain provisional.

## Mathematics

All four recommendations come with official Clay problem descriptions and are still labeled **Unsolved**. Clay describes the Millennium Problems as classic, exceptionally difficult questions selected after consultation with leading experts. Each has a formal statement, many known special cases or equivalent formulations, and an obvious proof/counterexample validation boundary. [Clay overview](https://www.claymath.org/millennium-problems/)

| Candidate | Verdict | Seed statement and verification | Decomposition basis |
| --- | --- | --- | --- |
| Riemann Hypothesis | **Strong** | Prove or disprove that every nontrivial zero of the Riemann zeta function has real part `1/2`. Clay currently labels it Unsolved and supplies the official problem description. [Clay](https://www.claymath.org/millennium/Riemann-Hypothesis/) | Zero-free regions, equivalent criteria, zeta-function estimates, random-matrix heuristics, and computational checks are distinct directions. Finite zero checks are Progress, not a Solution. |
| Hodge Conjecture | **Strong** | Prove or disprove that Hodge cycles on projective algebraic varieties are rational linear combinations of algebraic cycles, within the exact scope of Deligne's official statement. Clay says it is known in special cases but unknown in dimension four. [Clay](https://www.claymath.org/millennium/hodge-conjecture/) | Special classes and dimensions, cycle constructions, cohomological methods, and candidate counterexamples provide natural subproblems. |
| Birch and Swinnerton-Dyer Conjecture | **Strong** | Prove or disprove the equality between the rank of an elliptic curve over the rationals and the order of vanishing of its `L`-function at `s = 1`, using Wiles's official formulation. Clay currently labels it Unsolved. [Clay](https://www.claymath.org/millennium/birch-and-swinnerton-dyer-conjecture/) | Rank cases, curve families, analytic continuation, Tate-Shafarevich finiteness, arithmetic statistics, and computation form separable directions. |
| Yang-Mills Existence and Mass Gap | **Strong** | Prove that for every compact simple gauge group `G`, a nontrivial quantum Yang-Mills theory exists on `R⁴` and has a mass gap `Δ > 0`, including the required axiomatic properties. Clay currently labels it Unsolved and publishes the formal statement. [Clay overview](https://www.claymath.org/millennium/yang-mills-the-maths-gap/) · [official formulation](https://www.claymath.org/wp-content/uploads/2022/02/MPPc.pdf) | Constructive field theory, lower-dimensional and lattice results, axiomatization, continuum limits, and mass-gap estimates provide meaningful directions. |

### Mathematics exclusion

| Candidate | Verdict | Reason |
| --- | --- | --- |
| Navier-Stokes existence and smoothness | **Exclude for launch; status ambiguous** | On 2026-09-10 Clay announced that the problem had “apparently been settled” and said the claimed work must be analyzed under its deliberately unhurried evaluation process. Clay's problem page now calls it **Active**, not Unsolved. It is therefore not an “unquestionably open” launch choice on the 2026-09-15 cutoff. Reassess after Clay's review. [Clay announcement](https://www.claymath.org/news/navier-stokes-announcement/) · [problem page](https://www.claymath.org/millennium/navier-stokes-equation/) |

## Natural science

Three clean launch-ready empirical Problems are in neutrino physics. They are exact physical parameters or symmetry questions, not umbrella mysteries. Fermilab's 2026 materials still describe mass ordering and leptonic CP violation as questions DUNE is expected to determine, while the 2025 Particle Data Group review and 2026 DOE-laboratory results show that the absolute mass remains bounded rather than measured. [Fermilab, July 2026](https://indico.fnal.gov/event/72820/timetable/?view=standard_numbered) · [Particle Data Group 2025 review](https://pdgweb.lbl.gov/2025/reviews/rpp2025-rev-neutrino-mixing.pdf) · [DOE 2026 KATRIN result](https://science.osti.gov/np/Highlights/2026/4a)

| Candidate | Verdict | Seed statement and verification | Decomposition basis |
| --- | --- | --- | --- |
| Determine the neutrino mass ordering | **Strong** | Determine whether the three known mass eigenstates have normal or inverted ordering. A seed version must fix the model assumptions, datasets, significance threshold, systematic-error treatment, and independent-reproduction rule. Fermilab reported in June 2026 that NOvA plus future JUNO measurements could reach `3σ` evidence within five years, confirming that the ordering was not yet determined. [NOvA publications](https://novaexperiment.fnal.gov/publications/) | Oscillation channels, reactor and accelerator datasets, matter effects, interaction models, detector calibration, global fits, and alternative-model checks are separable directions. |
| Determine whether neutrino oscillations violate CP symmetry | **Strong** | Determine whether the Dirac phase `δCP` differs from the CP-conserving values `0` and `π` in the three-flavor model. A seed version must predeclare discovery/exclusion significance across parameter space and independent datasets. DUNE's official technical design identifies this as an open question addressable by oscillation experiments. [DUNE technical design report](https://lss.fnal.gov/archive/2020/pub/fermilab-pub-20-025-nd.pdf) | Beam modes, appearance channels, cross-section and flux systematics, matter-effect degeneracies, detector reconstruction, combined fits, and theory interpretation are independent directions. |
| Determine the absolute neutrino mass scale | **Strong, with scoped precision** | Directly determine the lightest neutrino mass (and therefore the absolute scale), rather than only mass-squared differences. The seed must state a target uncertainty or interval and model assumptions; “measure it exactly” is not a valid criterion. DOE reported in 2026 that KATRIN had narrowed the range but that the exact mass remains unknown. [DOE Office of Science](https://science.osti.gov/np/Highlights/2026/4a) | Tritium beta decay, cosmological inference, neutrinoless double-beta constraints, calibration and molecular-state systematics, and joint inference are distinct directions. |

### Cross-field natural-science additions

These two candidates pass the same five criteria without relying on neutrino or particle physics.

| Candidate | Field | Verdict | Seed statement and verification | Decomposition basis |
| --- | --- | --- | --- | --- |
| Resolve the Hubble-tension discrepancy | Observational cosmology | **Strong, with a fixed benchmark suite** | Explain why independently inferred present-day expansion rates disagree. A Solution must either identify and reproduce a specific measurement/systematic correction, or supply a quantitative physical model that makes predeclared early- and late-universe benchmark datasets statistically concordant without degrading their individual fits; it must then succeed on held-out or subsequently collected data. NASA's current Hubble science page says the values still disagree and that the tension “is still a mystery.” [NASA Hubble Constant and Tension](https://science.nasa.gov/mission/hubble/science/science-behind-the-discoveries/hubble-constant-and-tension/) | Distance-ladder calibration, standard sirens, strong-lens time delays, CMB inference, baryon acoustic oscillations, stellar-population systematics, model comparison, and blinded cross-dataset tests are separable directions. |
| Demonstrate ambient-pressure room-temperature superconductivity | Condensed-matter and materials science | **Strong** | Produce a reproducible material that superconducts at or above a predeclared room-temperature threshold (recommended `293.15 K`) at approximately one atmosphere. Require independent synthesis plus bulk zero DC resistance, magnetic flux expulsion/Meissner evidence, critical-field/current behavior, and structural/compositional characterization; one electrical anomaly is insufficient. DOE still presents room-temperature superconductivity as a grand challenge, and its July 2025 update describes an ambient-pressure nickelate near `80 K` only as a step toward that goal. [DOE grand challenges](https://science.osti.gov/bes/efrc/History/Grand-Challenges) · [DOE 2025 nickelate result](https://www.energy.gov/science/bes/articles/unveiling-link-between-high-pressure-and-superconductivity) | Candidate-material families, synthesis and stabilization, pairing predictions, structure/property mapping, transport, magnetic confirmation, isotope effects, artifact controls, and independent replication form distinct directions. The platform stops at discovery and scientific validation; wire fabrication, manufacturing, and deployment are downstream technology. |

### Natural-science reserves

| Candidate | Verdict | Reason |
| --- | --- | --- |
| Are neutrinos Majorana or Dirac particles? | **Conditional** | Authoritative and still open: Berkeley Lab calls it one of neutrino physics's most important open questions, and 2026 LEGEND results only set a stronger lower half-life limit. But ordinary neutrinoless double-beta decay is a one-sided test: observation would establish Majorana character, while non-observation at finite sensitivity would not by itself prove Dirac character. Publish only after experts define what would settle each branch. [Berkeley Lab SNO+](https://nuclearscience.lbl.gov/research/research-programs/neutrinos/neutrinos-research/neutrino-detection-for-science-and-nonproliferation/neutrino-detection-for-science-and-nonproliferation-research/sno/) · [LEGEND-200 2026](https://nuclearscience.lbl.gov/2026/03/30/legend-200-publishes-its-first-results/) |
| Determine the nature of dark matter | **Conditional** | NASA and DOE still describe its composition and non-gravitational properties as unknown, and the 2023 P5 report makes determining its nature a major science driver. However, this is an umbrella research program, not yet one falsifiable claim: detection, abundance, astrophysical alternatives, and candidate completeness need an expert-defined validation boundary. [NASA](https://science.nasa.gov/dark-matter/) · [DOE Cosmic Frontier](https://science.osti.gov/hep/Research/Cosmic-Frontier) · [2023 P5 report](https://www.usparticlephysics.org/2023-p5-report/introduction.html) |
| Determine the physical cause of cosmic acceleration | **Conditional** | NASA and P5 identify the cosmological constant, dynamical fields, and modified gravity as live explanations. The question is important and decomposable, but “understand dark energy” has no finite acceptance criterion until experts specify observables, model space, precision, and what evidence discriminates the alternatives. [NASA](https://science.nasa.gov/astrophysics/programs/physics-of-the-cosmos/expand-our-knowledge-of-dark-energy/) · [2023 P5 report](https://www.usparticlephysics.org/2023-p5-report/illuminate-the-invisible-universe.html) |
| Explain the microscopic mechanism of unconventional high-temperature superconductivity | **Conditional** | DOE identifies the mechanism as a grand challenge, but “complete explanation” has no universally finite validation boundary across cuprates, iron-based compounds, nickelates, and other material families. Keep this separate from the objectively testable material-discovery Problem above; publish it only after experts define the material scope and required discriminating predictions. [DOE superconductivity report](https://science.osti.gov/-/media/bes/pdf/reports/files/Basic_Research_Needs_for_Superconductivity_rpt.pdf) |

## Computer science

| Candidate | Verdict | Seed statement and verification | Decomposition basis |
| --- | --- | --- | --- |
| P versus NP | **Strong** | Prove `P = NP` by giving and proving a polynomial-time algorithm for an NP-complete problem, or prove `P ≠ NP`. Clay currently labels it Unsolved and publishes Cook's official description. [Clay](https://www.claymath.org/millennium/p-vs-np/) | Circuit lower bounds, proof complexity, algebraic and geometric complexity, algorithms for restricted cases, and barrier results are established directions. |
| Unique Games Conjecture | **Strong** | Prove or disprove Khot's formal inapproximability conjecture for Unique Games. Khot's first-party survey states the formulation; a current Simons Institute program still lists solving it as a motivating open question. [Khot survey](https://cs.nyu.edu/~khot/papers/UGCSurvey.pdf) · [Simons Institute](https://simons.berkeley.edu/index.php/programs/analysis-tcs-new-frontiers) | Restricted graph classes, sum-of-squares hierarchies, expansion, integrality gaps, approximation algorithms, and equivalent formulations are separable directions. |
| Existence of classical one-way functions | **Strong** | Prove that a function family exists that is polynomial-time computable but infeasible for every probabilistic polynomial-time adversary to invert on average, or prove none exists, under one fixed standard definition. A 2024 primary paper calls this the most important open problem in cryptography and supplies a formal statement. [Hirahara, Lu, and Oliveira, IACR ePrint](https://eprint.iacr.org/2024/1388) | Worst-case-to-average-case reductions, candidate constructions, meta-complexity, circuit lower bounds, black-box barriers, and restricted models provide independent directions. |
| Is Graph Isomorphism in P? | **Strong** | Give and prove a deterministic polynomial-time algorithm deciding whether two finite graphs are isomorphic, or prove no such algorithm exists. A 2025 STOC paper from its authors' institution states that no polynomial-time algorithm is known; the problem is finite and algorithmically testable even though correctness and runtime require proof. [ISTA/STOC 2025](https://research-explorer.ista.ac.at/record/20007) | Canonization, group-theoretic methods, Weisfeiler-Leman refinement, restricted graph families, smoothed analysis, and lower-bound/barrier work are distinct directions. |

## Launch recommendation

1. Seed the **13 Strong candidates**, not 15 merely to fill a quota.
2. Use the exact institutional or scholarly formal statements as Sources; write plain-language summaries separately.
3. Label every seed **Unstewarded** and preserve this research note as selection evidence.
4. Before publishing the five empirical Problems, publish a procedural Seed Audit Report tracing their confidence thresholds, allowed assumptions, systematic-error requirements, benchmark datasets, and independent-reproduction rules to authoritative Sources. Their eventual Committees must adopt or replace those seeds before scientific promotion can occur.
5. Recheck every status immediately before launch. In particular, do not seed Navier-Stokes unless Clay's review leaves it open.

## Source-quality note

Only first-party institutional pages, government laboratories/agencies, official problem institutions, and primary scholarly sources were used. Search-result summaries and popular secondary accounts were not treated as evidence.
