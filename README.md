# Clickswave Scoop bucket

Scoop manifests for [Crossfyre](https://crossfyre.io), for Windows on x86_64.

## Install

```powershell
scoop bucket add clickswave https://github.com/clickswave/scoop-bucket
scoop install clickswave/crossfyre
```

## What it installs

Only the `crossfyre` CLI, from the versioned release on bins.crossfyre.io, for
running crossfyre as your own user. `crossfyre login`, `crossfyre node list` and
the other commands that need no administrator work from it.

The CLI fetches the node agent, cfx-script and the engines into
`C:\Program Files\Crossfyre\bin`, which only an administrator can write to, so a
Scoop install run as your own user has none of them.

## Running a node

Not from Scoop. A node is a Windows service that runs as LocalSystem, and it should
not run a file that your own user can replace, as everything under `~\scoop` can be.
To run this machine as a node, `scoop uninstall crossfyre` and install crossfyre
with the installer, as https://crossfyre.io/docs/install describes.

## Updating and removing

`scoop update crossfyre` updates the CLI. `scoop uninstall crossfyre` removes it.
Your sign-in and settings stay in `%APPDATA%\crossfyre` until you delete it.

## Licence

The CLI is a first-party build. Its open source parts are under the Apache License
2.0 and live at https://github.com/clickswave/crossfyre-toolchain. The binary as a
whole is under `BINARY-LICENCE.txt`, which Scoop installs next to `LICENSE` and
`THIRD-PARTY-NOTICES` in `~\scoop\apps\crossfyre\current`.

The manifests in this repository are under the 0BSD licence in `LICENSE`.
