# Changes in this fork

Upstream: https://github.com/python-humanize/humanize

Inspected commit: `785e5dcc0d0308ad0dff3f6cc0faa7085ad0375b`. This directory is upstream code with a focused modification. It is not an original authored library.

## Changes

Return existing NaN, +Inf and -Inf formatting for non-finite sizes, before choosing a suffix. Preserve finite formatting and all suffix modes. Add 19 regression cases.

## Validation

Python 3.14.4, macOS arm64: 875 passed; translations compiled; benchmark timing disabled; Ruff passed for changed files. Baseline symptoms were reproduced before the patch; detailed logs remain in the portfolio research workspace. No public PR has been opened and no upstream acceptance is claimed.

## License and attribution

Original project and contributors retain their copyrights. Original `LICENCE` is unchanged. The MIT copyright and permission notice must accompany redistributed substantial portions. Dependencies and translation files retain their original attribution.

## Remaining validation

Run the upstream supported Python matrix and full release gates before proposing a release. This patch makes no production performance claim.

Published fork: https://github.com/Borep1945/humanize-numeric-edges

## Run the regression suite

Use Python 3.11+ and GNU gettext tools for the complete translation suite.

```sh
python3 -m pip install -e '.[tests]'
bash scripts/generate-translation-binaries.sh
python3 -m pytest -q tests --benchmark-disable
```
