![Need for Speed Underground](docs/images/title.png)

**English** · [Русский](README.md)

# NFSU Android

A preview of a native Android ARM64 port of Need for Speed Underground, based on static recompilation of the Xbox version.

**[Complete guide: controls, settings, backups and transferring progress](docs/GUIDE-EN.md)**

**[v0.2.0-preview.7 downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.7)** — ARM64 APK, downloadable guides and checksums. [English release history](docs/RELEASE-NOTES-EN.md).

## Features

- A dedicated Vulkan renderer, a separate graphics-preparation thread, geometry arenas and prepared state keys.
- System Vulkan, built-in MaliSX2, Purple Turnip T30 for compatible Adreno GPUs, and custom driver ZIP import.
- Classic and race touch layouts, directional buttons or a neon stick, shared pause, draggable controls and race-button sizing from 40% to 100%.
- Gamepad support, separate touch/gamepad assignments, and A/B and X/Y swapping.
- 4:3, 16:9 and 20:9 with preserved HUD and menu proportions; 1×/2×/3× internal resolution and a 60 or 120 FPS limit.
- Russian and English interfaces.
- Fixed RG477M audio output: OpenSL ES with a 512-frame buffer is selected automatically, including on GammaOS.
- Automatic profile backups in `Download/NFSU/Saves`, retention of the latest 10 generations created by the installation, and restoration through the system folder picker.
- Faster exact conversion of swizzled textures and reuse of the Vulkan pipeline cache on the system-driver path. Texture-change checks are retained.

## Release status

The current public version is **0.2.0-preview.7**, versionCode **10**. Cache and prewarm accounting now use real Vulkan texture allocation requirements. Counting RGBA bytes could previously allow a memory-budget exit while loading the next career track.

On October 25, 2026, the user manually completed the entire original problem tournament **«Субботний драйв» — all four stages** — on **RG477M / MaliSX2**, at 2×, 4:3 and a 60 FPS cap. The submitted save was copied exactly; the game process stayed alive across the stages and no autopilot was used. No crashes or memory-budget refusals were recorded during the series. The user confirmed tournament completion and that the new save loads; new progress was kept and the existing profile was not overwritten.

The highest recorded renderer allocation total in periodic samples was **314.20 MiB against a 512 MiB budget**. This is the maximum among logged samples, not a continuously measured peak or the app's total RAM. The cache stayed within 128 MiB, with 1,707 evictions and 69 restorations recorded. These counters confirm that the memory policy ran; they do not measure an FPS gain.

This is one complete manual run of the specified series on RG477M/MaliSX2. No new FPS comparison or complete device/driver matrix is claimed.

Retained: the new touch controls with buttons or a neon stick and shared pause Ⅱ, the drag-racing layout fix, 4:3/16:9/20:9 with preserved HUD/menu proportions, fixed RG477M audio, Russian and English, settings, saved progress, and System Vulkan, MaliSX2, Purple Turnip T30 and custom ZIP driver selection.

Memory budgets and texture quality are retained. This is a preview release; the guide explains the fix and its test scope. Update without uninstalling and keep an external progress backup first.

## Game data

You need your own compatible **NFS Underground image for the original Xbox, USA version**. Import an ISO or ZIP through the launcher. The PC version and Underground 2 are not supported. Game images, user saves and private logs are not distributed in this repository.

## Credits and provenance

This work builds on [nfsu1-sw](https://github.com/antoxa2584x/nfsu1-sw), [nfsu1-android](https://github.com/cherepavel/nfsu1-android), [xboxrecomp](https://github.com/sp00nznet/xboxrecomp), and the graphics and Android libraries used by the port. See [components, recorded revisions and source scope](docs/COMPONENTS-EN.md) and [third-party notices](licenses/README.md).

Need for Speed and Underground are names owned by their respective rights holders. This is an unofficial project.
