# Package catalogue

This repository uses GitHub Releases as the package catalogue and archive store for WPM. Package releases are discovered by the WPM client; merely adding a directory or source file to this repository does not publish an installable package.

## Current status

No package is declared as officially available by this catalogue document. A package should be considered published only after its release and archive have been created successfully and a clean consumer project can discover and install it using WPM.

## Required verification for each package

Before announcing a package, verify all of the following with the current WEIRD/WPM version:

1. The package manifest is valid.
2. The release tag and release title match WPM's implemented naming convention.
3. The expected archive asset is attached.
4. Package metadata and dependency declarations can be read by WPM.
5. A clean project can search for and inspect the package.
6. The package installs with a lockfile and frozen installation.
7. Archive integrity checks pass.
8. The package's documented examples run successfully.
9. Platform requirements and known limitations are documented.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the publishing checklist and [README.md](README.md) for registry configuration.

## Security

Packages execute with the permissions of the process running WEIRD. Review package source before installation. Checksums verify downloaded bytes against recorded metadata but do not prove that a package is trustworthy.
