# VasqStrike Desktop Releases

Public download artifacts for [VasqStrike](https://vasqstrike.tech).
This repository contains release metadata and installers; application source
and build management are maintained separately in the private source repository.

## Windows

[Download Windows 0.1.2](https://github.com/FelipeVqs/VasqStrike-releases/releases/download/windows-v0.1.2/VasqStrike-windows-x64.exe)

This is a native Windows x64 build that loads `https://vasqstrike.tech`.
It is unsigned and uses manual updates. Windows may display an unknown-publisher
warning. Close the old client and launch the newly installed VasqStrike shortcut.
Confirm that sign-in opens `vasqstrike.tech`.

The versioned release contains the tested installer, `build-info.json`, and
`SHA256SUMS`. The provenance records the built source commit, backend origin,
hash, and signing status. Verify the installer with PowerShell:

```powershell
Get-FileHash .\VasqStrike-windows-x64.exe -Algorithm SHA256
```

Compare the result with `SHA256SUMS` from the same versioned release.
Release notes distinguish a successful native build from installed-client
sign-in and connection checks.

## Legacy platform downloads

The historical `desktop-v0.0.61` release retains macOS/Linux files and signed
updater metadata for compatibility. Those mirrored clients were not rebuilt
from current VasqStrike source and may still use original upstream endpoints.
Their presence does not establish compatibility with your VasqStrike backend.

The repository-wide `latest` pointer stays on that historical release to keep
existing platform download URLs working. The fixed-name Windows alias there
is retained as a compatibility link to the promoted Windows build. Prefer the
explicit versioned Windows release above for provenance and repeatable downloads.

## Release policy

- `windows-vX.Y.Z`: standalone Windows build with explicit signing/update status.
- `desktop-vX.Y.Z`: cross-platform desktop distribution channel.
- Published version tags and versioned assets are not moved or replaced.
- Windows-only releases do not become repository-wide `latest`.
- New versions include source provenance, checksums, and verification notes.

Do not post credentials, account information, private targets, or sensitive
logs in this public repository. Report security findings privately to the
VasqStrike maintainer through your established support channel.
