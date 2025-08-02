# Contributing to Routine-Ops

First off, thanks for taking the time to contribute! We welcome improvements, bug fixes, tests, and documentation enhancements.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Code of Conduct](#code-of-conduct)
3. [How to Contribute](#how-to-contribute)

   * [Reporting Issues](#reporting-issues)
   * [Suggesting Enhancements](#suggesting-enhancements)
   * [Submitting Pull Requests](#submitting-pull-requests)
4. [Repository-specific Guidelines](#repository-specific-guidelines)

   * [plan-engine](#plan-engine)
   * [backend](#backend)
   * [ui](#ui)
5. [Development Workflow](#development-workflow)

   * [Branching Model](#branching-model)
   * [Commit Message Guidelines](#commit-message-guidelines)
   * [Writing Tests](#writing-tests)
6. [Style and Quality](#style-and-quality)
7. [License](#license)

---

## Getting Started

1. **Clone the repository** for the project you want to work on:

   ```bash
   git clone https://github.com/routine-ops/<repository-name>.git
   cd <repository-name>
   ```
2. **Install dependencies** as described in that repo’s `README.md`:

   ```bash
   # Example for Python projects
   poetry install
   # Example for JavaScript projects
   npm install
   ```
3. **Create a feature branch**:

   ```bash
   git checkout -b feature/my-new-feature
   ```

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md). Please read and abide by it to foster a welcoming community.

## How to Contribute

### Reporting Issues

* Search existing issues to avoid duplicates.
* When opening a new issue, use the default template and include:

  * A clear description of the problem or feature request.
  * Steps to reproduce (for bugs).
  * Expected vs. actual behavior.

### Suggesting Enhancements

* Describe the enhancement clearly.
* Include use cases or user stories.
* Add any relevant context (links, screenshots).

### Submitting Pull Requests

1. Fork the target repository and branch from `main`.
2. Commit changes in atomic, descriptive commits.
3. Push your branch to your fork.
4. Open a pull request against `main` including:

   * A concise title.
   * A summary of changes.
   * A reference to the related issue (if any).

## Repository-specific Guidelines

### plan-engine

See the [plan-engine CONTRIBUTING.md](https://github.com/routine-ops/routine-ops-plan-engine/blob/main/CONTRIBUTING.md) for coding standards, build steps, and testing protocols.

### backend

Refer to the [backend CONTRIBUTING.md](https://github.com/routine-ops/routine-ops-backend/blob/main/CONTRIBUTING.md) for database migration, API docs, and test guidelines.

### ui

Consult the [ui CONTRIBUTING.md](https://github.com/routine-ops/routine-ops-ui/blob/main/CONTRIBUTING.md) for style rules, component testing, and CI/CD setup.

## Development Workflow

### Branching Model

* **main** is always production-ready.
* Create feature branches:

  * `feature/<short-description>` for new features.
  * `bugfix/<short-description>` for fixes.
  * `docs/<short-description>` for documentation updates.

### Commit Message Guidelines

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <subject>

<body>

<footer>
```

* **type**: `feat`, `fix`, `docs`, `chore`, `style`, `refactor`, `test`.
* **scope**: optional component or file affected.
* **subject**: brief summary (<50 chars).

### Writing Tests

* Add unit/integration tests for new features and bug fixes.
* Use pytest for Python and Jest for JavaScript.
* Keep tests deterministic and idempotent.

## Style and Quality

* Follow PEP 8 and run `black` + `flake8` for Python.
* Use `prettier` + `eslint` for JS/TS.
* Document public APIs with docstrings or JSDoc.
* Update `CHANGELOG.md` for any user-facing changes.

## License

This project is licensed under the MIT License—see the [`LICENSE`](LICENSE) file for details.
