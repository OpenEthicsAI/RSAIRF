# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-09-06

### Added

- Initial public release of the Really Simple AI Risk Framework (RSAIRF).
- AI Risk Register (`register.csv`) with 30 AI-specific risks (AIR01–AIR30) tagged to lifecycle stages.
- Standards mapping (`standards-map.csv`) cross-referencing each risk to NIST AI RMF, OWASP LLM Top 10 (2025), the EU AI Act, ISO/IEC 42001 (Annex A), and MITRE ATLAS.
- Risk log template (`risk-log.template.csv`) for likelihood × impact scoring, ownership, sign-off, KRIs, and review cadence.
- Methodology and scoring guidance (`README.md`).
- Overview presentation (`docs/index.html`, published via GitHub Pages) and PDF export (`RSAIRF.pdf`), with source in `src/`.

[1.0.0]: https://github.com/OpenEthicsAI/RSAIRF/releases/tag/v1.0.0
