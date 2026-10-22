![Need for Speed Underground](docs/images/title.png)

**English** · [Русский](README.md)

# NFSU Android

A preview of a native Android ARM64 port of Need for Speed Underground, based on static recompilation of the Xbox version.

**[Complete guide: controls, settings, backups and transferring progress](docs/GUIDE-EN.md)**

**[v0.2.0-preview.4 downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.4)** — ARM64 APK, downloadable guides and checksums. [English release history](docs/RELEASE-NOTES-EN.md).

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

The current public preview is **0.2.0-preview.4**, versionCode 7. It adds a separate built-in **Purple Turnip T30 · Adreno** option using the MrPurple666 package. System Vulkan remains the default; MaliSX2 and custom ZIP import remain available. Built-in T30 does not replace your imported driver package.

A custom-driver crash during GPU enumeration is fixed: the loader no longer requires the name `malisx2`. Instead, it matches GPU identity and driver version/UUID against the selected SHA256-verified library. It still rejects a mismatching system-driver substitution.

Testing on Huawei covered two T30 cold launches, an image of a loaded race and switching back to System Vulkan. Also passed: 24 ARM64 driver-identity checks, 37 selection-policy checks, four RU/EN interface variants and real ZIP import checks for 4 KB/16 KB pages. This is limited compatibility testing: FPS comparisons, a long race and the full T30 GPU matrix have not been completed. The old full `gpuSelfTest` forces a separate GLES/ANGLE path and failed to create EGL on this Huawei with both System and T30 selected; no successful run is attributed to it.

The public APK uses the checked code and libraries from test build `fbbe5d71`; only AndroidManifest metadata and the launcher version label differ, with debugging disabled. The final public APK was not separately launched on a phone. Huawei's original APK, controls, settings and saves were restored after testing; the game was closed.

20:9, Russian localization, controls, backups and the RG477M OpenSL ES 512 fix are retained. The game library, audio and previous built-in drivers match preview.3 byte for byte. The Unified driver is outside this change.

This is a preview release. The public APK is not debuggable; the private signing key is not distributed. Compatibility with every Mali or Adreno device is not claimed.

## Game data

You need your own compatible **NFS Underground image for the original Xbox, USA version**. Import an ISO or ZIP through the launcher. The PC version and Underground 2 are not supported. Game images, user saves and private logs are not distributed in this repository.

## Credits and provenance

This work builds on [nfsu1-sw](https://github.com/antoxa2584x/nfsu1-sw), [nfsu1-android](https://github.com/cherepavel/nfsu1-android), [xboxrecomp](https://github.com/sp00nznet/xboxrecomp), and the graphics and Android libraries used by the port. See [components, recorded revisions and source scope](docs/COMPONENTS-EN.md) and [third-party notices](licenses/README.md).

Need for Speed and Underground are names owned by their respective rights holders. This is an unofficial project.
