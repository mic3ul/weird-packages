# Security policy

## Reporting a vulnerability

Do not publish exploit details, access tokens, session credentials, or private user data in a public Issue.

For registry, package, or WPM-related security problems, contact the repository maintainer privately through an available GitHub contact method. If private contact is unavailable, open a minimal public Issue that requests a private reporting channel without including exploit details.

## Package publisher responsibilities

- Never include secrets, account session files, or private data in a package.
- Validate archive paths and avoid path traversal.
- Treat downloaded files as untrusted input.
- Declare dependencies accurately and avoid unexpected network or process behavior.
- Document permissions, platform requirements, and any native dependencies.
- Publish immutable versioned releases.

## Consumer guidance

Installing a package executes code with the permissions of the calling user. Inspect unfamiliar packages before use. A checksum is an integrity check, not a proof of safety or publisher identity.
