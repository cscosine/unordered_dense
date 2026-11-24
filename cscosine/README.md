# unordered_dense: the cscosine fork

unordered_dense, as built and released by [third_party_base_libs](https://github.com/cscosine/third_party_base_libs) for the
cscosine projects: the upstream release plus a few commits of ours on top. This folder is ours; the rest of the
repository is upstream.

| | |
|---|---|
| Upstream | <https://github.com/martinus/unordered_dense> |
| Base | upstream tag `v5.3.3` (also in this repository) |
| Our changes | `git log v5.3.3..main` |
| Our releases | tags `v5.3.3-cs.<n>`, see [CHANGELOG.md](CHANGELOG.md) |
| License | upstream's (MIT) |

## Our changes

| Commit | Files | Why |
|---|---|---|
| csCMake presets: the fork built with the csCMake presets on every platform | `CMakePresets.json`, `csCMakeProjectSetup.json` | Built with the csCMake presets |
| cscosine/: where the fork comes from | `cscosine/README.md`, `CHANGELOG.md` | Where the fork comes from, what we change, why |

Upstream's `.github/` stays as it is: GitHub Actions is disabled on this repository.

## Syncing with a new upstream release

Fetch the new upstream tag (`git fetch https://github.com/martinus/unordered_dense.git refs/tags/<new>:refs/tags/<new>`), rebase our
commits on it (`git rebase --onto <new> v5.3.3 main`), drop those upstream has absorbed, build through
third_party_base_libs, then tag `v<new without v>-cs.1`.
