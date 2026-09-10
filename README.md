# offsite-test-repo

Throwaway repository for Offsite's worktree **finish** end-to-end tests
(`host/worktree_e2e_test.py` in the offsite repository).

The test run creates branches, opens and closes pull requests, merges into `main`
and resets `main` afterwards. Do not keep anything of value here.

## CI contract

The workflow in `.github/workflows/ci.yml` passes unless a file named `ci-fail`
exists at the repository root. A branch that adds `ci-fail` therefore produces a
failing check, which the tests use for the "checks failing" state.
MCP tool test 16:34:27
