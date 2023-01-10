relativize-imports
================

Automatically convert python absolute imports to relative.

Inspired and adapted from [MarcoGorelli/absolufy-imports](https://github.com/MarcoGorelli/absolufy-imports).

## Installation

```console
$ pip install relativize-imports
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

## Command-line example

```console
$ relativize-imports
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
