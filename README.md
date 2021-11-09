# PYGuides

<div align="center">

[![Dependencies Status](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen.svg)](https://github.com/serykhelena/PYGuides/pulls?utf8=%E2%9C%93&q=is%3Apr%20author%3Aapp%2Fdependabot)

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/serykhelena/PYGuides/blob/main/.pre-commit-config.yaml)

Usefull guides to deal with Python3

</div>

## Very first steps

### Preparations

1. Install make
    - Windows:

        Install [chocolatey](https://chocolatey.org/install) and install `make` with command:

    ```powershell
    choco install make
    ```

    - Linux:

    ```bash
    sudo apt-get install build-essential
    ```

1. Install python 3.8
    - Windows

        Install with [official executable](https://www.python.org/downloads/)

    - Linux

    ```bash
    sudo apt install python3.8-dev
    ```

1. Install poetry

    - Windows

        Use [official instructions](https://python-poetry.org/docs/#windows-powershell-install-instructions) or use `powershell` command:

    ```powershell
    (Invoke-WebRequest -Uri https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py -UseBasicParsing).Content | python -
    ```

    - Linux

    ```bash
    make poetry-download
    ```

### Initialize your code

1. Initialize `git` inside your repo:

```bash
cd PYGuides && git init
```

2. Initialize poetry and install `pre-commit` hooks:

```bash
make install
make pre-commit-install
```

3. Run the codestyle:

```bash
make codestyle
```

4. Upload initial code to GitHub:

```bash
git add .
git commit -m ":tada: Initial commit"
git branch -M main
git remote add origin https://github.com/serykhelena/PYGuides.git
git push -u origin main
```

### Some Issues

- If you have issues with python version like:

    ```bash
    The currently activated Python version 3.9.7 is not supported by the project (~3.8.0)
    ...
    NoCompatiblePythonVersionFound
    ...
    ```

    Check version of your `python3` binary and make sure you have python3.8 installed.

### Set up bots

- Set up [Dependabot](https://docs.github.com/en/github/administering-a-repository/enabling-and-disabling-version-updates#enabling-github-dependabot-version-updates) to ensure you have the latest dependencies.
- Set up [Stale bot](https://github.com/apps/stale) for automatic issue closing.

### Poetry

Want to know more about Poetry? Check [its documentation](https://python-poetry.org/docs/).

<details>
<summary>Details about Poetry</summary>
<p>

Poetry's [commands](https://python-poetry.org/docs/cli/#commands) are very intuitive and easy to learn, like:

- `poetry add numpy@latest`
- `poetry run pytest`
- `poetry publish --build`

etc
</p>
</details>

### Building and releasing your package

Building a new version of the application contains steps:

- Bump the version of your package `poetry version <version>`. You can pass the new version explicitly, or a rule such as `major`, `minor`, or `patch`. For more details, refer to the [Semantic Versions](https://semver.org/) standard.
- Make a commit to `GitHub`.
- Create a `GitHub release`.
- And... publish 🙂 `poetry publish --build`

## 🎯 What's next

Well, that's up to you 💪🏻. I can only recommend the packages and articles that helped me.

- [`Typer`](https://github.com/tiangolo/typer) is great for creating CLI applications.
- [`Rich`](https://github.com/willmcgugan/rich) makes it easy to add beautiful formatting in the terminal.
- [`Pydantic`](https://github.com/samuelcolvin/pydantic/) – data validation and settings management using Python type hinting.
- [`Loguru`](https://github.com/Delgan/loguru) makes logging (stupidly) simple.
- [`tqdm`](https://github.com/tqdm/tqdm) – fast, extensible progress bar for Python and CLI.
- [`IceCream`](https://github.com/gruns/icecream) is a little library for sweet and creamy debugging.
- [`orjson`](https://github.com/ijl/orjson) – ultra fast JSON parsing library.
- [`Returns`](https://github.com/dry-python/returns) makes you function's output meaningful, typed, and safe!
- [`Hydra`](https://github.com/facebookresearch/hydra) is a framework for elegantly configuring complex applications.
- [`FastAPI`](https://github.com/tiangolo/fastapi) is a type-driven asynchronous web framework.

Articles:

- [Open Source Guides](https://opensource.guide/).
- [A handy guide to financial support for open source](https://github.com/nayafia/lemonade-stand)
- [GitHub Actions Documentation](https://help.github.com/en/actions).
- Maybe you would like to add [gitmoji](https://gitmoji.carloscuesta.me/) to commit names. This is really funny. 😄

## 🚀 Features

### Development features

- Supports for `Python 3.8` and higher.
- [`Poetry`](https://python-poetry.org/) as the dependencies manager. See configuration in [`pyproject.toml`](pyproject.toml) and [`setup.cfg`](setup.cfg).
- Automatic codestyle with [`black`](https://github.com/psf/black), [`isort`](https://github.com/timothycrosley/isort) and [`pyupgrade`](https://github.com/asottile/pyupgrade).
- Ready-to-use [`pre-commit`](https://pre-commit.com/) hooks with code-formatting.
- Type checks with [`mypy`](https://mypy.readthedocs.io); docstring checks with [`darglint`](https://github.com/terrencepreilly/darglint); security checks with [`safety`](https://github.com/pyupio/safety) and [`bandit`](https://github.com/PyCQA/bandit)
- Testing with [`pytest`](https://docs.pytest.org/en/latest/).
- Ready-to-use [`.editorconfig`](.editorconfig), [`.dockerignore`](.dockerignore), and [`.gitignore`](.gitignore). You don't have to worry about those things.

### Deployment features

- Everything is already set up for security checks, codestyle checks, code formatting, testing, linting, docker builds, etc with [`Makefile`](Makefile#L89). More details in [makefile-usage](#makefile-usage).
- [Dockerfile](docker/Dockerfile) for your package.

## Installation

```bash
pip install -U PYGuides
```

or install with `Poetry`

```bash
poetry add PYGuides
```



### Makefile usage

[`Makefile`](Makefile) contains a lot of functions for faster development.

<details>
<summary>1. Download and remove Poetry</summary>
<p>

To download and install Poetry run:

```bash
make poetry-download
```

To uninstall

```bash
make poetry-remove
```

</p>
</details>

<details>
<summary>2. Install all dependencies and pre-commit hooks</summary>
<p>

Install requirements:

```bash
make install
```

Pre-commit hooks coulb be installed after `git init` via

```bash
make pre-commit-install
```

</p>
</details>

<details>
<summary>3. Codestyle</summary>
<p>

Automatic formatting uses `pyupgrade`, `isort` and `black`.

```bash
make codestyle

# or use synonym
make formatting
```

Codestyle checks only, without rewriting files:

```bash
make check-codestyle
```

> Note: `check-codestyle` uses `isort`, `black` and `darglint` library

<details>
<summary>4. Code security</summary>
<p>

```bash
make check-safety
```

This command launches `Poetry` integrity checks as well as identifies security issues with `Safety` and `Bandit`.

```bash
make check-safety
```

</p>
</details>

</p>
</details>

<details>
<summary>5. Type checks</summary>
<p>

Run `mypy` static type checker

```bash
make mypy
```

</p>
</details>

<details>
<summary>6. Tests</summary>
<p>

Run `pytest`

```bash
make test
```

</p>
</details>

<details>
<summary>7. All linters</summary>
<p>

Of course there is a command to ~~rule~~ run all linters in one:

```bash
make lint
```

the same as:

```bash
make test && make check-codestyle && make mypy && make check-safety
```

</p>
</details>

<details>
<summary>8. Docker</summary>
<p>

```bash
make docker-build
```

which is equivalent to:

```bash
make docker-build VERSION=latest
```

Remove docker image with

```bash
make docker-remove
```

More information [about docker](docker).

</p>
</details>

<details>
<summary>9. Cleanup</summary>
<p>
Delete pycache files

```bash
make pycache-remove
```

Remove package build

```bash
make build-remove
```

Or to remove pycache, build and docker image run:

```bash
make clean-all
```

</p>
</details>
