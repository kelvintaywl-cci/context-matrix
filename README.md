# context-matrix
Exploring "how-to" pass contexts in matrix form for CircleCI config

# Important

This is a really contrived showcase of how we can work around injecting context(s) in matrix form in CircleCI.

This is inspired by the work-around shared here:
https://discuss.circleci.com/t/matrix-for-non-parameterized-jobs/42253

# Context

No pun intended, but the set up to the `kelvintaywl-cci` Organization in CircleCI is as follows:

## Contexts

- test-2:
  - `TEST_2` env var  
- test-3:
  - `TEST_3` env var
- test-4:
  - `TEST_4` env var

Hence, if `test-2` context is loaded, we should have `TEST_2` env var injected.
We can see which env vars are injected successfully under the _Preparing environment variables_ step within a job.
For example:
https://app.circleci.com/pipelines/github/kelvintaywl-cci/context-matrix/4/workflows/0a311993-8938-4347-924d-7408536c866a/jobs/12?invite=true#step-99-28

# In Action

You can see how to do this for single context jobs in the **explore-single-context** workflow:
https://app.circleci.com/pipelines/github/kelvintaywl-cci/context-matrix/4/workflows/0a311993-8938-4347-924d-7408536c866a

For multi-contexts, do check out the **explore-multi-context** workflow:
https://app.circleci.com/pipelines/github/kelvintaywl-cci/context-matrix/4/workflows/555c2fdb-c6a1-4a15-a879-6016cf21fc61
