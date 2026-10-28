# Contributing packages

Thank you for helping build the WEIRD package ecosystem.

## Before publishing

- Confirm that you have the right to distribute every file in the package.
- Give the package a unique, lowercase name using letters, digits, and hyphens where supported by the installed WPM version.
- Set a valid semantic version in `weird.json`.
- Declare every dependency and use version ranges rather than local paths.
- Include a README explaining the package API, examples, platform requirements, and limitations.
- Include a license.
- Run the package's tests with the WEIRD version it supports.
- Remove tokens, credentials, local session files, personal data, and generated artifacts.
- Inspect the archive contents before publishing.

## Publish

Use the WPM version shipped with the language project. Read its `docs/GITHUB_REGISTRY_QUICKSTART.md` and `docs/PACKAGES.md` first because registry details can change between versions.

For the GitHub Releases registry:

```sh
export WPM_REGISTRY=github://mic3ul/weird-packages
export WPM_GITHUB_TOKEN='<private-token-with-access-to-this-repository>'
wpm publish
unset WPM_GITHUB_TOKEN
```

Create a new version for every published update. Published versions should be treated as immutable; do not attempt to replace an existing version.

## Report a package problem

Open an Issue in this repository and include the package name, version, WPM version, platform, exact command, and sanitized error output. Never include tokens, session files, private media, or other secrets.
