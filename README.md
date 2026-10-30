# GateLab hosting

GateLab's primary public URL is [https://gate-lab.github.io/](https://gate-lab.github.io/). The previous URL, [https://david-priest.github.io/GateLab/](https://david-priest.github.io/GateLab/), remains available during the transition.

This repository contains the GitHub Pages deployment configuration. Application source and releases remain in [david-priest/GateLab](https://github.com/david-priest/GateLab).

After a public GateLab release deploys successfully at the previous URL, its workflow dispatches `.github/workflows/deploy-pages.yml` here with that release's full commit SHA. The workflow checks the SHA against current public `master`, builds that exact commit with the asset base `/`, and deploys it to the primary URL. A stale notification succeeds without building or deploying, so it cannot roll the primary site back. Deployments run serially and do not cancel an active deployment.

Merging a hosting configuration change into `main` builds the current public `master` snapshot. For manual recovery, run the deployment workflow on `main` with the required `source_sha` input set to the current `david-priest/GateLab` `master` commit: exactly 40 lowercase hexadecimal characters. The manual path uses the same stale-notification check; it cannot select an older release. There are no scheduled builds.

The dispatch uses a GitHub App installation token with Actions write permission for this repository, configured in the public source repository. This hosting repository needs no stored secrets or private source access. Each deployment includes source provenance in `source.json` and the application and dependency licenses. Check both URLs after a public release; retiring the previous URL requires a separate decision.

Hosting uses GitHub Free, a public repository and a standard Ubuntu runner. No custom domain, paid runner or private repository access is required. Build artifacts are retained for one day.
