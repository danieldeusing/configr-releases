# configr-releases

Built artifacts for **Configr** — a capability browser for AI coding agents.

Everything here is produced by CI from a private source repository. Nothing is
authored in this repo, and nothing here is source.

## Install

See the install guide at [danieldeusing.de](https://danieldeusing.de).

## What each release contains

| Platform | Files |
| --- | --- |
| macOS | `.dmg`, and `.app.tar.gz` for the in-app updater |
| Linux | `.AppImage`, `.deb`, `.rpm` |
| Windows | `.msi`, `-setup.exe` |

Each updater bundle ships a `.sig` beside it, and every release carries a
`latest.json` the app reads to find newer versions.

## Signing

The builds are **not** code-signed, so macOS and Windows will warn on first
launch. Installing through Homebrew avoids the macOS prompt entirely — the
install guide covers each platform.

Update bundles *are* signed, with a key separate from OS code signing. The app
verifies that signature before applying an update, so an update cannot be
substituted even though the download is unsigned.
