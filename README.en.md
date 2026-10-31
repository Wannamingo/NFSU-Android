![Need for Speed Underground](docs/images/title.png)

**English** · [Русский](README.md)

# NFSU Android

A preview of a native Android ARM64 port of Need for Speed Underground, based on static recompilation of the Xbox version.

**[Complete guide: controls, settings, backups and transferring progress](docs/GUIDE-EN.md)**

**[v0.2.0-preview.9 downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.9)** — ARM64 APK, downloadable guides and checksums. [English release history](docs/RELEASE-NOTES-EN.md).

## Features

- Per-control size 40–160% and opacity 20–100%, with independent save/reset and retained old layouts.
- Car reflections can be turned off in launcher/in-game settings; the previous choice and road reflections are retained.


- A dedicated Vulkan renderer, a separate graphics-preparation thread, geometry arenas and prepared state keys.
- System Vulkan, built-in MaliSX2, Purple Turnip T30 for compatible Adreno GPUs, and custom driver ZIP import.
- Classic and race touch layouts, directional buttons or a neon stick, shared pause, draggable controls and race-button sizing from 40% to 100%.
- Gamepad support, separate touch/gamepad assignments, and A/B and X/Y swapping.
- 4:3, 16:9 and 20:9 with preserved HUD and menu proportions; 1×/2×/3× internal resolution and a 60 or 120 FPS limit.
- Russian and English interfaces.
- Auto / OpenSL ES · 512 audio selection for all CPUs; sensor-driven rotation to either landscape side.
- Fixed RG477M audio output: OpenSL ES with a 512-frame buffer is selected automatically, including on GammaOS.
- Automatic profile backups in `Download/NFSU/Saves`, retention of the latest 10 generations created by the installation, and restoration through the system folder picker.
- Faster exact conversion of swizzled textures and reuse of the Vulkan pipeline cache on the system-driver path. Texture-change checks are retained.

## Release status

Current version: **0.2.0-preview.9**, versionCode **12**. Adds per-control size/opacity and car reflections Off. Retains preview.8 audio, automatic rotation, 20:9, drivers, Russian/English and saves. RG477M passed 54 graphics groups; Off/re-enable and individual control persistence were checked in the installed app. No new moving-race FPS result or full career qualification is claimed.

Install over the existing app without uninstalling or clearing data. Keep an external progress backup.

## Game data

You need your own compatible **NFS Underground image for the original Xbox, USA version**. Import an ISO or ZIP through the launcher. The PC version and Underground 2 are not supported. Game images, user saves and private logs are not distributed in this repository.

## Credits and provenance

This work builds on [nfsu1-sw](https://github.com/antoxa2584x/nfsu1-sw), [nfsu1-android](https://github.com/cherepavel/nfsu1-android), [xboxrecomp](https://github.com/sp00nznet/xboxrecomp), and the graphics and Android libraries used by the port. See [components, recorded revisions and source scope](docs/COMPONENTS-EN.md) and [third-party notices](licenses/README.md).

Need for Speed and Underground are names owned by their respective rights holders. This is an unofficial project.
