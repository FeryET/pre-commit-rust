# Notice

This is a fork of the original [repo](https://github.com/doublify/pre-commit-rust), which as of now, has been unmaintained for a few years. I'm trying to customize the hooks that I use the most, ping at me via the issues board if you needed any change or noticed anything.

---

# Rust hooks for pre-commit

[Rust](https://www.rust-lang.org) tools package for [pre-commit](https://pre-commit.com).

## Using rust tools with pre-commit

```yaml
- repo: https://github.com/FeryET/pre-commit-rust
  rev: v1.2.0
  hooks:
    - id: fmt
    - id: cargo-check
```

## Passing arguments to rustfmt

```yaml
- repo: https://github.com/FeryET/pre-commit-rust
  rev: v1.2.0
  hooks:
    - id: fmt
      args: ["--verbose", "--edition", "2018", "--"]
```

## Pre-push hooks

You can use `test` and `build` pre-commit hooks to make sure you are not pushing a faulty code to the remote.

```yaml
- repo: https://github.com/FeryET/pre-commit-rust
  rev: v1.2.0
  hooks:
    - id: build
    - id: test
```

You can then install these hooks via:

```sh
pre-commit install --hook-type pre-push
```
