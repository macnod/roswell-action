# roswell-action

GitHub Action to install **Roswell** (Common Lisp environment manager) + **SBCL** with specific versions.

## Quick Start

```yaml
- uses: macnod/roswell-action@v2
```

**Default versions:**
- Roswell: `23.10.14.114`
- SBCL: `2.5.10`

## Specify Versions

```yaml
- uses: macnod/roswell-action@v2
  with:
    sbcl-version: 2.5.10           # Optional
    roswell-version: 23.10.14.114  # Optional
```

## Full Example

```yaml
name: CI
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: macnod/roswell-action@v2
      - run: |
          ros version
          ros run -- --version
```

## Inputs

| Input            | Default            | Description |
|------------------|--------------------|-------------|
| `sbcl-version`   | `2.5.10`          | SBCL version |
| `roswell-version`| `23.10.14.114`    | Roswell version |

## What it does

✅ Installs Roswell
✅ Adds to PATH
✅ Installs SBCL
✅ Ready to use

[Roswell](https://github.com/roswell/roswell) • [SBCL](http://www.sbcl.org/)
