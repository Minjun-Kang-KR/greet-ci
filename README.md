# greet-ci

A small Python greeting project used to practice continuous integration with
GitHub Actions.

## Requirements

- Python 3.11 or newer
- [uv](https://docs.astral.sh/uv/)

## Run

```powershell
uv run --locked python greet.py Hee
uv run --locked python greet.py
```

The first command prints `Hello, Hee!`; the second prints `Hello, world!`.

## Verify

```powershell
uv lock
uv run --locked pytest -q greet.py
uv run --locked black --check greet.py
uv run --locked flake8 greet.py
uv run --locked mypy greet.py
uv build
```

The GitHub Actions workflow runs the tests on Ubuntu and Windows with Python
3.11 and 3.12, checks formatting, lint, and types, then builds and uploads the
package distributions.
