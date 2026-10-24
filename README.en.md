![Need for Speed Underground](docs/images/title.png)

**English** · [Русский](README.md)

# NFSU Android

A preview of a native Android ARM64 port of Need for Speed Underground, based on static recompilation of the Xbox version.

**[Complete guide: controls, settings, backups and transferring progress](docs/GUIDE-EN.md)**

**[v0.2.0-preview.6 downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.6)** — ARM64 APK, downloadable guides and checksums. [English release history](docs/RELEASE-NOTES-EN.md).

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

The current public version is **0.2.0-preview.6**, versionCode 9. The shared Mali/Adreno app now has one pause button Ⅱ, race steering through directional buttons or a round neon stick, and a classic layout without either stick or the on-screen L1/L2/L3/R1/R2/R3 buttons.

Choose steering only while the game is running: **Ⅱ → Settings → Race steering → Resume game**. Neither launcher offers this option. Pause remains accessible when other touch controls are hidden. Separate ≡, MENU and gear buttons are removed; the layout toggle reads CLASSIC / RACE.

The user confirmed V2 on Huawei. Passed: 3205 steering checks, 2170 shared-pause checks and the previous neon-rendering and button-size suites. The public APK has the same DEX, native libraries, drivers and resources as accepted Huawei APK `1c698434`; only AndroidManifest and the launcher version label differ. The final public APK was not separately launched on a device; no new GPU matrix, RG477M check or FPS comparison was performed.

The drag fix, 20:9 with preserved HUD/menu proportions, RG477M OpenSL ES 512 audio, languages, settings, profiles and backups are retained. System Vulkan remains the default; MaliSX2, experimental Purple Turnip T30 for compatible Adreno GPUs and custom ZIP import remain available. This work does not change the Unified driver.

This is a preview release. The private signing key is not distributed; compatibility with every Mali or Adreno device is not claimed.

## Game data

You need your own compatible **NFS Underground image for the original Xbox, USA version**. Import an ISO or ZIP through the launcher. The PC version and Underground 2 are not supported. Game images, user saves and private logs are not distributed in this repository.

## Credits and provenance

This work builds on [nfsu1-sw](https://github.com/antoxa2584x/nfsu1-sw), [nfsu1-android](https://github.com/cherepavel/nfsu1-android), [xboxrecomp](https://github.com/sp00nznet/xboxrecomp), and the graphics and Android libraries used by the port. See [components, recorded revisions and source scope](docs/COMPONENTS-EN.md) and [third-party notices](licenses/README.md).

Need for Speed and Underground are names owned by their respective rights holders. This is an unofficial project.
