# Changelog

All notable changes to this dataset will be documented in this file.

## [1.0.0] - 07-2026

### Added
- Initial release of QSQ measurement dataset for the $^{40}\mathrm{Ca}^+$ ion trap at Mainz University.
- Measurement runs from July 2025, containing circuits of increasingly long $R_x(\pi/2)$ gate sequences, 1000 shots per circuit.
- `README.md` describing the measurement scheme, calibration workflow, and data format.

### Known Issues
- Autocalibration status (qubit frequency $\omega_0$ and laser power drift compensation) is unconfirmed for the 23.07 runs, which may explain anomalous oscillation behavior in the QSQ analysis.
- Data was collected as a proof-of-principle for QSQ certification rather than under best-achievable trap conditions.

## [1.1.0] - 11-2026

### Changed
- Modified keys in all json lines to include `"shots"`, `measurement_basis` and `ideal_probs`. The latter of which depends on whether or not the `amount_of_gates` value is divisible by 4.
- Modified `README.md` to introduce global sequence parameters and the aforementioned new keys.
- Added missing `angles` keys on datasets (RT_0.7ms_4.5pm, RT_1.3ms_7pm, RT_1.5ms_12am)

These changes come up in order to make the dataset compatible with version 0.2.0 of QSQlab