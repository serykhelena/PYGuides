# PYGuides

<div align="center">

[![Dependencies Status](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen.svg)](https://github.com/serykhelena/PYGuides/pulls?utf8=%E2%9C%93&q=is%3Apr%20author%3Aapp%2Fdependabot)

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/serykhelena/PYGuides/blob/main/.pre-commit-config.yaml)

Usefull guides to deal with Python3

</div>

## Very first steps

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

2. Install python 3.8
    - Windows

        Install with [official executable](https://www.python.org/downloads/)

    - Linux

    ```bash
    sudo apt install python3.8-dev
    ```

3. Install poetry

    - Windows

        Use [official instructions](https://python-poetry.org/docs/#windows-powershell-install-instructions) or use `powershell` command:

    ```powershell
    (Invoke-WebRequest -Uri https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py -UseBasicParsing).Content | python -
    ```

    - Linux

    ```bash
    make poetry-download
    ```

4. Install tools

```
make tools-install
```

5. While working with notebooks use virtual environment created by poetry
