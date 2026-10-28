# WEIRD Package Registry

This repository is the public package registry for the WEIRD programming language. It stores published packages as GitHub Releases so users can install packages without a dedicated server.

## Configure WPM

```sh
export WPM_REGISTRY=github://mic3ul/weird-packages
wpm search <keyword>
```

## Publish a package

1. Create a package with WPM and verify its `weird.json` manifest.
2. Create a fine-grained GitHub token scoped only to this repository, with the permissions required by WPM to publish releases.
3. Keep the token private and set it only in your current shell:

```sh
export WPM_REGISTRY=github://mic3ul/weird-packages
export WPM_GITHUB_TOKEN='<your-private-token>'
wpm publish
unset WPM_GITHUB_TOKEN
```

WPM's exact manifest fields, release naming, archive format, and publish command must match the version of `tools/wpm.py` shipped with the WEIRD language. Consult that version's `docs/GITHUB_REGISTRY_QUICKSTART.md` and `docs/PACKAGES.md` before publishing.

## Install a package

```sh
export WPM_REGISTRY=github://mic3ul/weird-packages
wpm search <keyword>
wpm info <package-name>
wpm add <package-name> --version '^0.1.0'
wpm install --frozen
```

The final two commands are intended for a project directory with a valid `weird.json` manifest. Use the version constraint appropriate for the package you choose.

## Registry policy

- Publish only packages you have the right to distribute.
- Never commit access tokens, session files, credentials, or personal data.
- Include a README, version, license, and clear dependency declarations in each package.
- Test packages before publishing and document platform requirements.
- Treat packages as executable code: install only packages from publishers you trust.
- Report broken or malicious packages through repository Issues.

## Important limitations

This repository is a release-backed package catalogue, not a package hosting server with an independent database. Public package installation should not require a token. Publishing requires authenticated GitHub access. A package checksum detects changes to downloaded bytes but does not prove that the package is safe or cryptographically identify its publisher.
