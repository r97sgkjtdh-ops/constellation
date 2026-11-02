<p align="center"><a href="SECURITY.md">Français</a> · English</p>

# Security policy

## Supported versions

Only the latest version published on the [Releases](https://github.com/r97sgkjtdh-ops/constellation/releases/latest) page receives fixes. The app offers each new version itself: keep it up to date.

## Reporting a vulnerability

**Do not post a vulnerability in a public issue.**

Use GitHub's private reporting: **Security** tab, then **Report a vulnerability**. The report is visible only to the maintainer.

If possible, include:

- the Constellation version (Settings › About) and the macOS version;
- what the flaw allows, and under what conditions;
- the steps to reproduce it.

You will get a first reply within 7 days. Once the flaw is fixed and the new version published, the report may be made public, with your agreement, crediting you if you wish.

## What already protects the app

- Updates are installed only if their **Ed25519 signature** matches the key built into the app, and only from GitHub's servers.
- The app keeps no credentials: accounts stay managed by Claude Code and the other tools.
- No data is sent to a Constellation server: there is none.
