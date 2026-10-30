# GateLab public hosting

Read `../AGENTS.md` and this repository's `README.md` before editing. This repository contains public hosting configuration only. Application changes begin in `../GateLab` and reach the public `david-priest/GateLab` release repository through its approved release process. Build only that public source, never a private development checkout.

Branch from current `origin/main` and propose changes through a PR to `main`. Public pushes require David's authorization in the current session. Keep Actions pinned to full commit SHAs and retain root-path builds, source provenance and licenses.

The public source workflow dispatches this deployment after its own Pages deployment succeeds, using a GitHub App token configured there. This repository stores no App secrets. Keep the required `source_sha` input, full lowercase SHA validation and comparison against hardcoded public `master`; stale notifications must succeed without deploying. Configuration pushes resolve current public `master`. Keep deployments serial without cancelling an active deployment, and do not add schedules.

For each public release, verify both the primary `https://gate-lab.github.io/` site and the transitional `https://david-priest.github.io/GateLab/` site, including the affected app interactions. Retiring the old URL requires David's later approval.
