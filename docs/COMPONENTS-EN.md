**English** · [Русский](COMPONENTS.md) · [Guide](GUIDE-EN.md) · [Project overview](../README.en.md)

# Preview release components

This repository contains application releases and user documentation. It is not yet a complete source tree for a reproducible APK build. GitHub's standard “Source code” archives contain this repository's tree, not the sources of every bundled library or any game data.

## APK identity

| Field | Value |
| --- | --- |
| Version | 0.2.0-preview.6, versionCode 9, debuggable disabled |
| Architecture | Android ARM64; app requires Android 10+, T30 requires Android 11+ |
| APK SHA-256 | `f075082c8092c93a5d58f9d791f81ba6b6c9cdc2b23a7ce3076081ffe91a205e` |
| Checked test APK | `1c698434dbff09ba0e6611ad749f42033a42c331145d110bd6c59868dce679c8` |
| Fixed custom-driver loader | `27e55484ad419a5e20985bcc7da00793fa0dc1eff3d2cfa3ef45746920aacc48` |
| Original T30 ZIP SHA-256 | `f65b2d3353fd4aa7190bb5426b94468e99ffea7a58a830bc0c4651db89353227` |
| vulkan.purple.so SHA-256 | `1d80dfa019659b008e4669311db5b1e4a02af59ff1d5458a98e2f5fe18ed013b` |

This release changes Java/DEX touch controls and launcher hints. All native libraries, drivers, audio, Russian localization and game additions are byte-identical to preview.5. The drag fix and 20:9 therefore remain in the same native code. The public APK preserves the DEX/native/drivers/assets of user-accepted Huawei APK `1c698434`; only AndroidManifest and the HTML version label differ. The public APK itself was not separately launched on a phone.

Acceptance: the user confirmed V2 on Huawei; 3205 steering checks, 2170 shared-pause checks and the previous neon-rendering and sizing suites passed. They validate input/layout logic, not a new GPU matrix, FPS comparison or every Mali/Adreno device. The new UI was not checked on RG477M at this stage. Steering choice is separate from positions and physical assignments; the accepted Huawei update retained UID, settings and render configuration without clearing data.

Historical checks retain their original scope: preview.5's drag fix passed 115 host and 115 Huawei ARM64 checks and was confirmed in drag racing. Preview.4 T30 checks covered two cold launches, a race image and return to System Vulkan on Huawei HWMNA. The old full GLES/ANGLE GPU test did not create EGL with either driver on this Huawei; no successful run is claimed.

The release includes a new UI source archive and retains the small drag-fix source patch. These packages contain the corresponding integration sources, not a complete tree for building the game's libmain.so. Fixed custom-loader sources and its AdrenoTools dependency are also provided separately. GitHub's standard Source code archives contain this repository's documentation.

## Main dependencies

- [Purple Turnip T30, MrPurple666](https://github.com/MrPurple666/purple-turnip/releases/tag/vturnip_mrpurple_T30-toasted.adpkg): the author's unchanged `turnip_mrpurple_T30-toasted.adpkg.zip`, metadata version `26.3.0-T30-1.4.359`, minApi 30. A built-in experimental option for suitable Adreno GPUs. [Package notice](../licenses/Purple-Turnip-T30-NOTICE.txt).
- [MaliSX2](https://github.com/bmdhacks/malisx2/tree/090e0c43a174a95284782f6129ee7de250256e3d), with local changes. Bundled driver SHA-256: `577a7ea21a54e8f107e296abb00eee7b8e6b0e6db1b9d39aa6fb89427228a455`.
- [Mesa branch used](https://github.com/bmdhacks/armsx2-turnip/tree/730a6284cb7a88f6c19a07f1caea35c7a2ae64f2). Individual components retain their own license terms.
- [AdrenoTools / linkernsbypass in ARMSX2](https://github.com/ARMSX2/ARMSX2/tree/a8031268e53ed9576c6093913671d4628210fd97), BSD-2-Clause. Custom driver import applies only inside this app.
- [xboxrecomp](https://github.com/sp00nznet/xboxrecomp/tree/74649ef5b0f023e7b878043bc6de2534c55e717e), with local system-layer changes. Its MIT license does not replace the separate terms of files listed in the upstream NOTICE.
- [SDL](https://github.com/libsdl-org/SDL/tree/fa2c02bb6e21974a89ea9824bc53c9932abe5f9c): the Android AAR description records version 3.4.16 and this commit.
- glslang and SPIRV-Cross: statically linked shader-conversion libraries. License texts are included; exact upstream commits for the prebuilt archives have not yet been established.
- LLVM C++ runtime and xxHash: notices are included in the licenses directory.
- ANGLE: compatible libraries were obtained from RG477M firmware; the GLES library contains local string modifications. No build from an established exact upstream revision is claimed. The included upstream LICENSE is provided as a reference.

Original terms and notices are in [licenses](../licenses/README.md). An upstream link does not imply that its current version matches a locally modified library byte for byte.

## Game content

Users must import their own compatible Xbox USA game data. ISO, XBE and user saves are not part of the repository materials. The APK includes Russian localization and font additions; these are not declared part of the MIT-licensed code. Guide screenshots and the title logo illustrate this unofficial port. Rights to the game, its imagery and trademarks belong to their respective rights holders.
