**English** · [Русский](COMPONENTS.md) · [Guide](GUIDE-EN.md) · [Project overview](../README.en.md)

# Preview release components

This repository contains application releases and user documentation. It is not yet a complete source tree for a reproducible APK build. GitHub's standard “Source code” archives contain this repository's tree, not the sources of every bundled library or any game data.

## APK identity

| Field | Value |
| --- | --- |
| Version | 0.2.0-preview.8, versionCode 11, debuggable disabled |
| Architecture | Android ARM64; app requires Android 10+, T30 requires Android 11+ |
| APK SHA-256 | `78a12804bdab37583d9a43a64e3d3be2ea150fcca20352413ffc94bb9f8ee831` |
| Checked test APK | `a4f2e91ddd882aeb154a9fc84a280f979d7af2a2bc2e9ce1cfeafcbe75aae595` |
| Fixed custom-driver loader | `27e55484ad419a5e20985bcc7da00793fa0dc1eff3d2cfa3ef45746920aacc48` |
| Original T30 ZIP SHA-256 | `f65b2d3353fd4aa7190bb5426b94468e99ffea7a58a830bc0c4651db89353227` |
| vulkan.purple.so SHA-256 | `1d80dfa019659b008e4669311db5b1e4a02af59ff1d5458a98e2f5fe18ed013b` |

For preview.8, libmain.so is byte-identical to preview.7. Java/DEX and launcher settings add audio selection and sensor orientation; the matched ANGLE pair and its notices are updated. The tested debug candidate has identical DEX and native libraries to this release. The final wrapper differs only in Manifest metadata, the HTML version label and corrected provenance notices; it was not separately cold-started. The test hash above is the audio/rotation candidate, not a fresh tournament run.

On October 25, 2026, the user manually completed the entire original problem tournament **«Субботний драйв» — all four stages** — on **RG477M / MaliSX2**, at 2×, 4:3 and a 60 FPS cap. The submitted save was copied exactly; the game process stayed alive across the stages and no autopilot was used. No crashes or memory-budget refusals were recorded during the series. The user confirmed tournament completion and that the new save loads; new progress was kept and the existing profile was not overwritten.

The highest recorded renderer allocation total in periodic samples was **314.20 MiB against a 512 MiB budget**. This is the maximum among logged samples, not a continuously measured peak or the app's total RAM. The cache stayed within 128 MiB, with 1,707 evictions and 69 restorations recorded. These counters confirm that the memory policy ran; they do not measure an FPS gain.

This is one complete manual run of the specified series on RG477M/MaliSX2. No new FPS comparison or complete device/driver matrix is claimed.

Passed: 8,803 host checks and four headless GPU test groups on Huawei. No new FPS comparison or complete driver matrix is claimed. The original refusal was logged on Mali-G610 MC6/System Vulkan; Huawei/Adreno is a separate device. The 128/64/512 MiB budgets, resource protection, fence-owned deletion and change checks are retained.

Historical checks retain their original scope: preview.5's drag fix passed 115 host and 115 Huawei ARM64 checks and was confirmed in drag racing. Preview.4 T30 checks covered two cold launches, a race image and return to System Vulkan on Huawei HWMNA. The old full GLES/ANGLE GPU test did not create EGL with either driver on this Huawei; no successful run is claimed.

The release includes a new UI source archive and retains the small drag-fix source patch. These packages contain the corresponding integration sources, not a complete tree for building the game's libmain.so. Fixed custom-loader sources and its AdrenoTools dependency are also provided separately. GitHub's standard Source code archives contain this repository's documentation.

Also included: `NFSU-career-memory-fix-source.zip`, containing the accounting diff against preview.6 and associated tests. It is the source of this specific fix, not a complete reproducible APK project. User saves, private device logs and the signing key are excluded.

## Main dependencies

- [Purple Turnip T30, MrPurple666](https://github.com/MrPurple666/purple-turnip/releases/tag/vturnip_mrpurple_T30-toasted.adpkg): the author's unchanged `turnip_mrpurple_T30-toasted.adpkg.zip`, metadata version `26.3.0-T30-1.4.359`, minApi 30. A built-in experimental option for suitable Adreno GPUs. [Package notice](../licenses/Purple-Turnip-T30-NOTICE.txt).
- [MaliSX2](https://github.com/bmdhacks/malisx2/tree/090e0c43a174a95284782f6129ee7de250256e3d), with local changes. Bundled driver SHA-256: `577a7ea21a54e8f107e296abb00eee7b8e6b0e6db1b9d39aa6fb89427228a455`.
- [Mesa branch used](https://github.com/bmdhacks/armsx2-turnip/tree/730a6284cb7a88f6c19a07f1caea35c7a2ae64f2). Individual components retain their own license terms.
- [AdrenoTools / linkernsbypass in ARMSX2](https://github.com/ARMSX2/ARMSX2/tree/a8031268e53ed9576c6093913671d4628210fd97), BSD-2-Clause. Custom driver import applies only inside this app.
- [xboxrecomp](https://github.com/sp00nznet/xboxrecomp/tree/74649ef5b0f023e7b878043bc6de2534c55e717e), with local system-layer changes. Its MIT license does not replace the separate terms of files listed in the upstream NOTICE.
- [SDL](https://github.com/libsdl-org/SDL/tree/fa2c02bb6e21974a89ea9824bc53c9932abe5f9c): the Android AAR description records version 3.4.16 and this commit.
- glslang and SPIRV-Cross: statically linked shader-conversion libraries. License texts are included; exact upstream commits for the prebuilt archives have not yet been established.
- LLVM C++ runtime and xxHash: notices are included in the licenses directory.
- ANGLE: matched prebuilt pair from [kubuszok/sge-angle-natives Chromium 7151](https://github.com/kubuszok/sge-angle-natives/releases/tag/chromium-7151), upstream ANGLE commit `df9c59dcacff7d186d00e3263a1aa68f8059137c`. No local source rebuild or instruction patching. See [provenance](../licenses/ANGLE-compat-provenance.json), [notice](../licenses/ANGLE-SGE7151-NOTICE.txt) and [third-party terms](../licenses/ANGLE-SGE7151-THIRD-PARTY.txt). The older firmware license is retained as historical material.

Original terms and notices are in [licenses](../licenses/README.md). An upstream link does not imply that its current version matches a locally modified library byte for byte.

## Game content

Users must import their own compatible Xbox USA game data. ISO, XBE and user saves are not part of the repository materials. The APK includes Russian localization and font additions; these are not declared part of the MIT-licensed code. Guide screenshots and the title logo illustrate this unofficial port. Rights to the game, its imagery and trademarks belong to their respective rights holders.


Historical career checks above belong to preview.7. Preview.8 adds `NFSU-Android-preview.8-UI-source.zip` with current Java/UI, Manifest and tests. It is integration material, not a complete reproducible APK project.
