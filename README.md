relativize-imports
================

[![badge](https://img.shields.io/pypi/v/relativize-imports)](https://pypi.org/project/relativize-imports/)

Automatically convert python absolute imports to relative.

Inspired and adapted from [MarcoGorelli/absolufy-imports](https://github.com/MarcoGorelli/absolufy-imports).

## Installation

```console
$ pip install --upgrade relativize-imports
```

## Usage as a pre-commit hook

See [pre-commit](https://github.com/pre-commit/pre-commit) for instructions

Sample `.pre-commit-config.yaml`:

```yaml
-   repo: https://github.com/reallyliri/relativize-imports
    rev: v0.0.4
    hooks:
    -   id: relativize-imports
```

Or with args:

```yaml
-   repo: https://github.com/reallyliri/relativize-imports
    rev: v0.0.4
    hooks:
    -   id: relativize-imports
        args:
          - svc/src
          - automation/tests/source
```

## Usage

```shell
relativize-imports [path/to/dir/or/file.py ...]
```

Provide zero or more paths to relativize.

Files are assumed to be relative to the cwd. Directories are assumed as relativization root and the tool will format all python files under them, in any depth.

If no args are provided, the tool will run in the cwd and address it as the relativization root.

## Command-line example

```console
$ relativize-imports
$ relativize-imports src
$ relativize-imports mypackage/myfile.py
```

```diff
- from mypackage import __version__
+ from . import __version__
```

## Build and Publish

```shell
rm -rf dist
python setup.py bdist_wheel 
twine upload dist/*
```
