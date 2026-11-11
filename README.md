# phantomdep-dogfood

Purpose-built dogfood repo for **PhantomDep PR Gate**.

It runs the published Action — `RakTikoo/phantomdep-pr-gate@v0.2` — as a real
cross-repo consumer on pull requests, to prove the Action works on GitHub
(not just in local simulation):

- **Clean PR** adds known, imported deps (`lodash`, `requests`) — expect one
  PhantomDep comment, all OK, green check.
- **Bump commit** on the clean PR changes only a version — expect the same
  single comment updated in place, no added deps, still green.
- **Bad PR** adds the typosquat `reqeusts` — expect NOT-FOUND + SUSPECT-TYPO
  in the comment and a red (blocking) check.
