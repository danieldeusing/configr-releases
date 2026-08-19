# Configr

A capability browser for AI coding agents — Claude Code, OpenAI Codex, GitHub
Copilot, Google Antigravity and OpenCode.

Configr reads the configuration those tools already have on your machine and
shows you what each one actually loads: skills, agents, slash commands, hooks,
MCP servers, plugins and instruction files, each with where it came from and
whether it is really in effect.

This repository holds **built artifacts only**. Everything here is produced by
CI; nothing is authored here and nothing here is source.

---

## Install

### macOS

Homebrew is the recommended route — it puts the app in `/Applications`, keeps it
updated, and removes it cleanly.

```
brew install --cask danieldeusing/tap/configr
```

Or download `Configr_<version>_universal.dmg` from
[the latest release](https://github.com/danieldeusing/configr-releases/releases/latest),
open it, and drag Configr to Applications. One `.dmg` covers both Apple Silicon
and Intel.

To remove everything, including settings:

```
brew uninstall --zap --cask configr
```

### Windows

[Scoop](https://scoop.sh) is the recommended route:

```
scoop bucket add danieldeusing https://github.com/danieldeusing/configr-releases
scoop install configr
```

Or download `Configr_<version>_x64-setup.exe` from
[the latest release](https://github.com/danieldeusing/configr-releases/releases/latest)
and run it.

Windows builds are **not** code-signed, so SmartScreen shows *"Windows protected
your PC"* on first run. Choose **More info → Run anyway**. This does not apply to
macOS, which is signed and notarized.

### Linux

Download from [the latest release](https://github.com/danieldeusing/configr-releases/releases/latest):

| File | Use it when |
| --- | --- |
| `.AppImage` | Any distribution. Make it executable and run it — no install needed |
| `.deb` | Debian, Ubuntu, and derivatives |
| `.rpm` | Fedora, RHEL, openSUSE |

```
chmod +x Configr_<version>_amd64.AppImage
./Configr_<version>_amd64.AppImage
```

```
sudo dpkg -i Configr_<version>_amd64.deb
```

---

## Updating

Configr checks for updates from its own menu: **Configr → Check for Updates…**

What happens next depends on how you installed it, because an app that replaces
itself behind a package manager's back leaves that manager holding a version it
no longer has.

| Installed with | Check for Updates… does |
| --- | --- |
| Homebrew | Shows the command: `brew upgrade --cask configr` |
| Scoop | Shows the command: `scoop update configr` |
| `.deb` / `.rpm` | Shows an update command |
| `.dmg`, `.exe`, AppImage | Installs the update and restarts |

Either way the app tells you a new version exists — you never have to go looking.

Updates are signed independently of the download, and Configr verifies that
signature before applying one. An update cannot be substituted even by whoever
serves the file.

---

## What a release contains

| Platform | Files |
| --- | --- |
| macOS | `.dmg` (universal), and `.app.tar.gz` for the in-app updater |
| Linux | `.AppImage`, `.deb`, `.rpm` |
| Windows | `.msi`, `-setup.exe` |

Each updater bundle ships a `.sig` beside it, and every release carries a
`latest.json` the app reads to find newer versions.

## Signing

macOS builds are signed with a Developer ID certificate and notarized by Apple,
so they open without a Gatekeeper prompt however you install them.

Windows builds are **not** signed. Linux needs no signing.

---

Configr is © Daniel Deusing. Source is not public.
