# Contributing

This is a throwaway repository used by Offsite's git end-to-end tests
(`host/worktree_e2e_test.py` in the offsite repository). The test run creates
branches, opens and merges pull requests and resets `main` afterwards, so do not
store anything of value here.

## Running the tests

There is no test suite in this repository. The only check is the CI workflow in
`.github/workflows/ci.yml`, which passes unless a file named `ci-fail` exists at
the repository root.

To run the same check locally:

```sh
if [ -e ci-fail ]; then echo "ci-fail marker present: failing on purpose"; exit 1; fi; echo ok
```

To reproduce the "checks failing" state, add an empty `ci-fail` file and push
the branch. Remove it again to make CI pass.

The end-to-end tests that exercise this repository live in the offsite
repository and are run from there:

```sh
python -m pytest host/worktree_e2e_test.py
```
