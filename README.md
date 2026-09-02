# llamay releases

Signed binaries, packages and checksums for [llamay](https://llamay.com) —
the AZMX inference engine.

This repository carries **only the artifacts**. The engine's source is in
`AzmxAI/llamay`, which is private; this one is public because a release
nobody can download is not a release. It is the same arrangement as
`kosa8-releases` and `anz33-releases`.

## Install

**macOS and Linux**

```sh
curl -fsSL https://llamay.com/install.sh | sh
```

**Windows**, in PowerShell

```powershell
irm https://llamay.com/install.ps1 | iex
```

Or take a package from [the latest release](../../releases/latest): a `.dmg`
or `.pkg` for macOS, `.deb` and `.rpm` for Linux, a `_setup.exe` for Windows,
and plain `.tar.gz` / `.zip` archives for anyone who would rather place the
binary themselves.

## What is signed, and what that means

macOS binaries carry a Developer ID Application signature. Windows binaries
and installers are Authenticode signed through Azure Trusted Signing.

`SHA256SUMS` covers every file in a release and is what both install scripts
verify before they install anything — they refuse rather than continue if a
machine has no `sha256sum` or `shasum`, because an installer that skips the
check is one that runs whatever it was handed.

## Nothing is built here

Every artifact is produced by `llamay-signed-release.yml` in `AzmxAI/azmx-ai`,
which checks the source out, builds it, signs it and uploads it here. Pull
requests against this repository will not be reviewed; open them against the
engine instead.
