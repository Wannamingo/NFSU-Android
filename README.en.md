![Need for Speed Underground](docs/images/title.png)

**English** · [Русский](README.md)

# NFSU Android

A preview of a native Android ARM64 port of Need for Speed Underground, based on static recompilation of the Xbox version.

**[Complete guide: controls, settings, backups and transferring progress](docs/GUIDE-EN.md)**

**[v0.2.0-preview.5 downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.5)** — ARM64 APK, downloadable guides and checksums. [English release history](docs/RELEASE-NOTES-EN.md).

## Features

- A dedicated Vulkan renderer, a separate graphics-preparation thread, geometry arenas and prepared state keys.
- System Vulkan, built-in MaliSX2, Purple Turnip T30 for compatible Adreno GPUs, and custom driver ZIP import.
- A full touch gamepad layout and dedicated driving buttons, draggable controls and race-button sizing from 40% to 100%.
- Gamepad support, separate touch/gamepad assignments, and A/B and X/Y swapping.
- 4:3, 16:9 and 20:9 with preserved HUD and menu proportions; 1×/2×/3× internal resolution and a 60 or 120 FPS limit.
- Russian and English interfaces.
- Fixed RG477M audio output: OpenSL ES with a 512-frame buffer is selected automatically, including on GammaOS.
- Automatic profile backups in `Download/NFSU/Saves`, retention of the latest 10 generations created by the installation, and restoration through the system folder picker.
- Faster exact conversion of swizzled textures and reuse of the Vulkan pipeline cache on the system-driver path. Texture-change checks are retained.

## Release status

The current public preview is **0.2.0-preview.5**, versionCode 8. It fixes touch-layout switching in drag racing: movement is no longer mistaken for leaving the racing context, so the accelerator and gear buttons stay available.

The cause was exclusion of the separate drag mode from the game-context check. Memory, state and car-ownership checks remain enabled. Ordinary races, autopilot and manual layout switching are retained. The user confirmed the fix in a drag race on Huawei; 115 checks passed on the host and the same 115 on the phone's ARM64 CPU.

The public APK has the same native libraries, DEX, drivers and resources as checked test build `54835903`. Publication changes only AndroidManifest metadata and the launcher version label, with debugging disabled. The final public APK was not separately launched on a device. No new FPS comparison or full GPU matrix was performed for this fix.

20:9 with correct HUD/menu proportions, Russian and English, RG477M OpenSL ES 512, controls and backups are retained. System Vulkan remains the default; MaliSX2, built-in Purple Turnip T30 for compatible Adreno GPUs and custom ZIP import remain available. T30 is still experimental: its previous limited Huawei check does not establish compatibility with every Adreno or an FPS gain. See the [English release history](docs/RELEASE-NOTES-EN.md).

This is a preview release. The private signing key is not distributed. Compatibility with every Mali or Adreno device is not claimed.

## Game data

You need your own compatible **NFS Underground image for the original Xbox, USA version**. Import an ISO or ZIP through the launcher. The PC version and Underground 2 are not supported. Game images, user saves and private logs are not distributed in this repository.

## Credits and provenance

This work builds on [nfsu1-sw](https://github.com/antoxa2584x/nfsu1-sw), [nfsu1-android](https://github.com/cherepavel/nfsu1-android), [xboxrecomp](https://github.com/sp00nznet/xboxrecomp), and the graphics and Android libraries used by the port. See [components, recorded revisions and source scope](docs/COMPONENTS-EN.md) and [third-party notices](licenses/README.md).

Need for Speed and Underground are names owned by their respective rights holders. This is an unofficial project.
