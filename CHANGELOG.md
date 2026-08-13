# Changelog

All notable changes to this dataset will be documented in this file.

## [1.0.0] - 07-2025

### Added
- Initial release of QSQ measurement dataset for the $^{40}\mathrm{Ca}^+$ ion trap at Mainz University.
- Measurement runs from July 2025, containing circuits of increasingly long $R_x(\pi/2)$ gate sequences, 1000 shots per circuit.
- `README.md` describing the measurement scheme, calibration workflow, and data format.

### Known Issues
- Autocalibration status (qubit frequency $\omega_0$ and laser power drift compensation) is unconfirmed for the 23.07 runs, which may explain anomalous oscillation behavior in the QSQ analysis.
- Data was collected as a proof-of-principle for QSQ certification rather than under best-achievable trap conditions.