# GateLab hosting

GateLab is hosted at [https://gate-lab.github.io/](https://gate-lab.github.io/).

This repository contains the GitHub Pages deployment configuration. Application source and releases remain in [david-priest/GateLab](https://github.com/david-priest/GateLab).

The deployment workflow builds an explicitly pinned public GateLab commit with the asset base `/`. To deploy a later public release, update the checkout `ref` in `.github/workflows/deploy-pages.yml` through a pull request. Merging into `main` deploys the selected release; the workflow can also be started manually. There are no scheduled builds.

Hosting uses GitHub Free, a public repository and a standard Ubuntu runner. No custom domain, paid runner or private repository access is required. Build artifacts are retained for one day.
