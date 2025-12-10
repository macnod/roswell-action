# roswell-action

GitHub action to install Roswell (Common Lisp environment setup utility) and optionally a specific SBCL version.

## Usage

### Basic Usage (Default SBCL)

```yaml
name: CI
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: macnod/roswell-action@v1
      - run: ros run -- --version
```

### With Specific SBCL Version

```yaml
name: CI
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: macnod/roswell-action@v1
        with:
          sbcl-version: 2.5.10
      - run: make test
```

## Inputs

### `sbcl-version`

**Optional** The version of SBCL to install (e.g., `2.5.10`). 

- If specified, installs the requested SBCL version using Roswell
- If not specified, installs the default SBCL binary

## What This Action Does

1. Installs Roswell (Common Lisp environment manager)
2. Adds Roswell to the system PATH
3. Installs SBCL (Steel Bank Common Lisp):
   - If `sbcl-version` is provided: installs that specific version
   - Otherwise: installs the default SBCL binary distribution
4. Verifies the installation

## About Roswell

Roswell is a Common Lisp implementation manager and launcher. It makes it easy to install and manage different Common Lisp implementations, including SBCL, CCL, ECL, and others.

For more information, visit the [Roswell GitHub repository](https://github.com/roswell/roswell).
