# lab-ci-templates

Reusable workflows for the lab services. One version for the whole repo.

| Workflow | Used by | Does |
|---|---|---|
| `build.yml` | service repos | fake build, then writes the commit SHA to `environments/dev/<service>.yaml` in the platform repo |
| `release-please.yml` | service repos | keeps the service's release PR open; merging it tags the release |
| `release-build.yml` | service repos (on a release tag) | fake build of `vX.Y.Z`, then writes it to `environments/staging/<service>.yaml` on the open `release/*` branch |
| `self-release.yml` | this repo | release-please for this template repo (`vX.Y.Z` tags) |

Call it pinned to a tag, for example `uses: jaswennyhuang/lab-ci-templates/.github/workflows/build.yml@v1.0.0`.
