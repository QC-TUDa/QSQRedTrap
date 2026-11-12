# QSQ Measurements in Mainz University $^{40}\mathrm{Ca}^+$ Ion Trap

Experimental runs for QSQ certification. These measurements track changes in the fluorescence detection window used for state-dependent discrimination in the $^{40}\mathrm{Ca}^+$ ionic ground state. The aim of this investigation is to certify single-qubit gate quality while separating out the effects of SPAM errors in the circuit results.

## Measurement Scheme

QSQ measurement run data is contained in JSON Lines files (`.jsonl`). Each file contains circuits made up of increasingly longer sequences of $R_x(\pi/2)$ gates.

Each JSON line represents one circuit with 1000 measurement shots:

| Field | Description |
|---|---|
| `counts` | Shot results, with `"0"` and `"1"` giving the number of shots measured in $\lvert 0\rangle$ and $\lvert 1\rangle$ respectively |
| `amount_of_gates` | Number of $R_x(\pi/2)$ gates in the sequence |
| `shots` | Number of measurement shots per circuit |
| `gate` | Gate type applied (e.g. `"rx"`) |
| `angles` | Angles $\theta, \phi, \lambda$ used for rotation. $\sqrt{X}\equiv R(\theta=\pi/2, \phi=0)$ |
| `measurement_basis` | Bloch sphere basis in which state-dependent measurements were performed|
| `backend` | Identifier of the trap/backend used |
| `timestamp` | Human-readable timestamp |
| `unix_time` | Machine timestamp (Unix time) |

Example:

```json
{"counts": {"0": 941, "1": 59}, "amount_of_gates": 0, "ideal_probs": {"0": 1.0, "1": 0.0}, "shots": 1000, "gate": "rx", "angles": {"theta": 1.5707963267948966, "phi": null, "lam": null}, "measurement_basis": "Z", "backend": "RedTrapBackend", "timestamp": "23.07 18-01-07", "unix_time": 1753286467.6760588}
{"counts": {"0": 954, "1": 46}, "amount_of_gates": 0, "ideal_probs": {"0": 1.0, "1": 0.0}, "shots": 1000, "gate": "rx", "angles": {"theta": 1.5707963267948966, "phi": null, "lam": null}, "measurement_basis": "Z", "backend": "RedTrapBackend", "timestamp": "23.07 18-01-33", "unix_time": 1753286493.3604624}
```

The measurements present **global parameters** of:
- 1000 `shots` per circuit
- `"Z"` as the `measurement_basis`
- `rx` as the `gate` and `"theta": 1.5707963267948966` as the only `angles`. (Representing an $R_x(\pi/2)$ rotation)

## Experiment Calibration

The ion trap was calibrated at the beginning of each measurement day with a workflow consisting of:

- Ionic fluorescence
- Spin-selective readout
- Single-qubit Raman gate
- Sideband cooling

In addition to these manual steps, an autocalibration scheme for the qubit frequency $\omega_0$ and laser powers ran in the background during measurements to compensate for setup drift. However, it is not confirmed whether this scheme was active for the measurements taken in July 2025 ("23.07"), which may explain the anomalous behavior observed in the oscillations studied by the QSQ analysis.

It is also worth noting that these measurements were not taken with a "best achievable trap state" approach, but rather as a proof-of-principle for the QSQ certification method. As a result, the data quality may be subject to unaccounted-for factors.

Calibration steps such as splitting and the two-qubit Raman gate are not relevant to these measurements and were therefore often skipped.

## Data Generation & Analysis

All measurements were generated and can be analyzed with the [QSQlab](https://github.com/QC-TUDa/QSQlab.git) Python package. See the repository for further details and documentation.

## How to Cite

If you use this dataset, please cite it as:

> José Martínez et al. (2025). *QSQ Measurements in Mainz University <sup>40</sup>Ca<sup>+</sup> Ion Trap* [Data set]. Zenodo. https://doi.org/10.5281/zenodo.21918587

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21918587.svg)](https://doi.org/10.5281/zenodo.21918587)

- Academic work: *(to be added)*
- DOI: [10.5281/zenodo.21918587](https://doi.org/10.5281/zenodo.21918587)

## License

This data is licensed under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/). It may be used for personal and commercial purposes, provided attribution is given.

## Contact

- Ion trap: [QUANTUM Uni Mainz](https://www.quantenbit.physik.uni-mainz.de)
- QSQ certification: [QC TU Darmstadt](https://www.informatik.tu-darmstadt.de/qc/quantum_computing_group/index.en.jsp)
- Measurement responsible: José Martínez — [tmartnez@students.uni-mainz.de](mailto:tmartnez@students.uni-mainz.de)