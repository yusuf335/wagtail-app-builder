# Contributing to wagtail-app-builder

Thank you for your interest in contributing! This project is in an early design phase, so contributions of all kinds are welcome — ideas, design feedback, bug reports, documentation, and code.

## Ground rules

- Be respectful. All participation is governed by our [Code of Conduct](CODE_OF_CONDUCT.md).
- Open an issue before starting significant work, so we can discuss the approach and avoid duplicated or wasted effort.
- Keep pull requests focused: one feature or fix per PR.

## How to contribute

### Reporting bugs

Open an issue with:

- What you did, what you expected, and what actually happened
- Your Python, Django, Wagtail, and package versions
- A minimal reproduction (a small snippet or repo) if possible

### Suggesting features

Open an issue describing the use case first, not just the solution. Because this package is young, feature discussions directly shape the roadmap.

### Submitting code

1. Fork the repository and create a branch from `main` (e.g. `feature/widget-registry` or `fix/render-tag-escaping`)
2. Make your changes, following the style guidelines below
3. Add or update tests for any behavior change
4. Update documentation (README or docstrings) where relevant
5. Open a pull request against `main` and fill in the PR template

A maintainer will review your PR. Reviews may request changes — this is a normal part of the process.

## Development setup

```bash
git clone https://github.com/<your-fork>/wagtail-app-builder.git
cd wagtail-app-builder
python -m venv .venv && source .venv/bin/activate
pip install -e ".[dev]"
```

(The dev extra and test suite are being set up as part of the phase 1 roadmap — until then, discussion and design contributions are the most valuable.)

## Style guidelines

- **Python:** follow PEP 8; format with `black` and lint with `ruff`
- **JavaScript/React (editor):** format with `prettier`; functional components and hooks
- **Commits:** short imperative subject line ("Add widget registry"), details in the body if needed

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
