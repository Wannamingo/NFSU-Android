**English** · [Project overview](../README.en.md) · [Current guide](GUIDE-EN.md)

# Release notes

English translations of all six public releases. Each section describes that release at publication; later features must not be assumed to exist in earlier APKs. Russian originals remain on the release pages.


## v0.2.0-preview.6

[Release and downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.6)

### NFSU Android v0.2.0-preview.6 — new touch controls

- One shared **Ⅱ pause button** in classic and race layouts, accessible even when other touch controls are hidden.
- Race steering through **Left / right buttons** or a round **analog Neon stick**. Choose it only while running the game: **Ⅱ → Settings → Race steering → Resume game**. Neither launcher offers the option.
- A simplified classic layout: both virtual sticks and on-screen L1/L2/L3/R1/R2/R3 are removed; physical gamepads retain their functions.
- Separate ≡, MENU and the gear beside FPS are removed. The layout toggle reads **CLASSIC / RACE**.
- Steering selection, control positions and size, assignments, language and profiles are retained.

Retained: **the drag fix, 20:9, RG477M audio fix, Russian and English, backups and driver selection**: System Vulkan, MaliSX2, Purple Turnip T30 and custom ZIP. Native libraries and drivers are byte-identical to the previous release; the Universal/Unified Mali ICD is unchanged.

The user confirmed V2 on Huawei. Passed: 3205 steering checks, 2170 shared-pause checks and previous neon/sizing suites. The public APK has the same DEX/native/drivers/assets as accepted Huawei build `1c698434`; publication changes only Manifest and the HTML version, with debugging disabled. The final APK was not separately launched on a device. No new FPS/GPU/RG477M checks were performed at this stage.

**0.2.0-preview.6**, versionCode **9**, Android ARM64, Android 10+ (T30: Android 11+). Install over the previous version without uninstalling, then fully relaunch the game. Keep an external progress backup before updating. New installations use buttons; an existing selection is retained.

[English guide](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-EN.md) · [Русская инструкция](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-RU.md) · [Components](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/COMPONENTS-EN.md).

APK SHA256: `f075082c8092c93a5d58f9d791f81ba6b6c9cdc2b23a7ce3076081ffe91a205e`.

## v0.2.0-preview.5

[Release and downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.5)

### NFSU Android v0.2.0-preview.5 — drag-racing touch-layout fix

Fixed automatic touch-layout switching in drag racing. Previously, starting to move could replace the driving buttons with the menu layout, releasing the held accelerator; stopping restored the driving layout. The separate drag mode is now recognized as racing, keeping throttle and gear controls available. Car-state and ownership checks remain enabled. Manual layout switching, ordinary races and autopilot are retained.

**Retained:** 20:9 with correct HUD/menu proportions, 4:3 and 16:9, the RG477M OpenSL ES 512 audio fix, Russian/English, control settings, save backups and transfers, System Vulkan, MaliSX2, Purple Turnip T30 for compatible Adreno GPUs and custom ZIP import. Existing T30 limitations still apply.

Checked: 115 host logic tests and the same 115 on Huawei ARM64; the user confirmed the fix in an actual drag race. The final public APK has the same code and resources as checked test build `54835903`, with changed version metadata and debugging disabled. It was not separately launched on a device. No new FPS comparison or full GPU matrix was performed at this stage.

Version **0.2.0-preview.5**, versionCode **8**, Android ARM64, Android 10+ (T30: Android 11+). Install over the previous version without uninstalling; the signature is compatible. Fully relaunch the game after updating. You do not need to reset controls, delete your profile or re-import the game. Keep an external progress backup before updating.

[English guide](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-EN.md) · [Русская инструкция](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-RU.md) · [Components](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/COMPONENTS-EN.md).

APK SHA256: `021618e64422c05561dbb56a82d9de6e8cab8ca640a448a5b19574e71dc733ac`.

## v0.2.0-preview.4

[Original release and downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.4)

Built-in **Purple Turnip T30 · Adreno** has been added from the [MrPurple666 package](https://github.com/MrPurple666/purple-turnip/releases/tag/vturnip_mrpurple_T30-toasted.adpkg). Select launcher settings → Graphics driver → Purple Turnip T30, then launch the game again. The package is already inside the APK. System Vulkan remains the default; MaliSX2 and custom ZIP import are retained.

Fixed a loader crash caused by incorrectly requiring the MaliSX2 name even after Turnip loaded successfully. Verification against the selected SHA256-checked library and rejection of mismatching drivers are retained.

T30 requires Android 11+, ARM64, a suitable Adreno 6xx/7xx/8xx and 4 KB/16 KB pages. Adreno 710/720 are disabled in this option due to limitations reported by the author; other models are not guaranteed compatible. Huawei testing covered two cold launches, an image of a loaded race and switching back to System Vulkan. Passed: 24 ARM64 identity checks, 37 selection checks and four UI variants. The old full GLES/ANGLE GPU test did not create EGL on this Huawei; no successful run is claimed. FPS, long races and the entire Adreno matrix have not yet been tested.

20:9, localization, controls, backups and RG477M OpenSL ES 512 are retained. Game libraries, audio and previous drivers match preview.3. The public APK differs from the checked test build in version/debug metadata and the launcher version label; it was not separately launched. The test Huawei's settings and saves were restored.

**0.2.0-preview.4**, versionCode **7**, Android ARM64; the app requires Android 10+. Debugging is disabled. Install over the previous version without deleting data. To return to the stock output, select System Vulkan in the launcher and relaunch the game.

APK SHA256: `92e51f9504a1d8454b039bc93f1f02436864d7edb3853d54512f5cc657bd23bf`.

[English guide](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-EN.md) · [Components and testing scope](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/COMPONENTS-EN.md). Assets include the APK, original T30 ZIP, integration sources, guides and checksums.


## v0.2.0-preview.3

[Original release and downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.3)

### NFSU Android v0.2.0-preview.3 — RG477M audio fix and 20:9

This unified build includes the **RG477M audio fix** and the checked **20:9** mode. Russian language support, controls, drivers, saves and other features are retained.

#### Audio fix

RG477M automatically selects **OpenSL ES, 48 kHz stereo, a 512-frame buffer**, including on GammaOS. Bluetooth interference was reproduced with the previous AAudio256 path. In short title/menu tests, the user confirmed clean OpenSL ES audio through Bluetooth headphones, wired headphones and speakers. The unified test base separately passed a cold launch and automatic selection of the new output without diagnostic configuration.

The mixer and game audio files were unchanged. Huawei HWMNA's existing path is retained; other models keep their previous policy. After updating, fully close and relaunch the game.

#### 20:9 mode

Available in both launchers and the in-game settings. It expands the horizontal field of view while preserving the vertical field of view and the proportions of the car, HUD and menus. HUD and menus stay in a central 4:3 area. Choose **Settings → Aspect ratio → 20:9**, or **Aspect ratio → 20:9 → Resume game** during gameplay. Updating retains the previously selected format.

#### Retained features

- Vulkan renderer with a separate graphics-preparation thread, geometry arenas and prepared state keys.
- Faster exact conversion of swizzled textures. Texture-change detection is retained.
- A shared VkPipelineCache for graphics-pipeline creation on the System Vulkan path.
- Selection of System Vulkan, built-in MaliSX2 and a compatible custom driver imported from ZIP.
- Russian and English interfaces and an updated launcher title image.
- Two touch layouts: a full gamepad and dedicated driving buttons. Positions can be edited; race-button size adjusts from 40% to 100%.
- Separate touch/gamepad assignments and A/B and X/Y swapping.
- 1×/2×/3× scale, 4:3/16:9/20:9 formats and a 60/120 FPS limit.
- Automatic profile backups in Download/NFSU/Saves, the latest 10 generations created by the installation, and restoration/transfers through the launcher.
- Reduced repeated graphics-pipeline compilation, bounded retention of recoverable GPU texture copies, and audio-output fixes for the tested Huawei.

#### Installation and guide

Install the APK over the previous version without uninstalling. The signing certificate is retained and versionCode increases to **6**. Keep an external profile backup before updating. The [guide covering the audio fix, 20:9, controls and progress transfers](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-EN.md) is also available in the English guide ZIP.

You need your own **Xbox USA version of NFS Underground** game data. The PC version and Underground 2 are not supported. Game images and user saves are not distributed. Previous public releases remain available; Android may block lower-version APKs, and uninstalling solely to downgrade is not recommended.

#### Checks and limitations

The native code, DEX, drivers, Russian localization and logo match the checked unified base `61672a65` byte for byte. Publication changes only version metadata, disables debugging and updates the launcher version label. Signatures, certificate compatibility and 16 KB alignment were checked.

20:9 was previously checked on Huawei in menus and a loaded Golf/Olympic Square scene: seven format switches without restarting and 147 ARM64 calculation checks. The audio policy passed 12 scope checks; audio functions passed 14 checks. The three listening checks used the diagnostic build; the unified test base separately launched with automatic OpenSL ES 512 and speaker output.

The final public APK was not separately launched on a device. A long race, audio latency, live output switching and a new full GPU matrix were not tested at this stage. No FPS improvement is claimed for the audio fix; the 60/120 FPS limits do not guarantee those frame rates.

Version **0.2.0-preview.3**, versionCode **6**, Android ARM64, Android 10+. Debugging disabled.

File: `NFSU-Android-v0.2.0-preview.3-arm64.apk`.

SHA-256: `21368d9bd36eb1ff3f8eee2e6345441740dde949a21bd6216cdd8fc3b17ea341`.

[Components and source scope](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/COMPONENTS-EN.md).


## v0.2.0-preview.2

[Original release and downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.2)

### NFSU Android v0.2.0-preview.2 — 20:9 mode

**20:9** has been added to both launchers and the in-game settings. It expands the horizontal field of view while preserving the vertical field of view and the proportions of the HUD, car and menus. Menus and HUD stay in a central 4:3 area.

Choose **Settings → Aspect ratio → 20:9** in the launcher, or **Aspect ratio → 20:9 → Resume game** during gameplay. The format persists after restarting. Updating retains your previous choice; select the new mode manually.

#### Retained features

- Vulkan renderer with a separate graphics-preparation thread, geometry arenas and prepared state keys.
- Faster exact conversion of swizzled textures. Texture-change detection is retained.
- A shared VkPipelineCache for graphics-pipeline creation on the System Vulkan path.
- Selection of System Vulkan, built-in MaliSX2 and a compatible custom driver imported from ZIP.
- Russian and English interfaces and an updated launcher title image.
- Two touch layouts: a full gamepad and dedicated driving buttons. Positions can be edited; race-button size adjusts from 40% to 100%.
- Separate touch/gamepad assignments and A/B and X/Y swapping.
- 1×/2×/3× scale, 4:3/16:9/20:9 formats and a 60/120 FPS limit.
- Automatic profile backups in Download/NFSU/Saves, the latest 10 generations created by the installation, and restoration/transfers through the launcher.
- Reduced repeated graphics-pipeline compilation, bounded retention of recoverable GPU texture copies, and audio-output fixes for the tested Huawei.

#### Updating and guide

Install the APK over the previous version without uninstalling. The signing certificate is retained; versionCode increases to 5. Keep an external profile backup before updating. Russian language support, settings, game-data import and backup features are retained. Android may block an APK with a lower version number; do not uninstall solely to downgrade.

The [detailed guide with the new 20:9 section and screenshots](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-EN.md) is available in the English guide ZIP. You need your own **Xbox USA version of NFS Underground** game data. The PC version and Underground 2 are not supported. Game images and user saves are not distributed.

#### What was checked

Huawei testing on base `e0aa7cf9` covered the main menu and loaded Golf/Olympic Square: HUD/menu proportions, wider field of view and seven format switches without restarting the process. ARM64 calculation test: 147 checks. The public APK's native code, DEX, drivers, Russian localization and logo match that checked base byte for byte. Publication changes only version metadata, disables debugging and updates the launcher version label; APK signatures and alignment were checked.

The final public APK was not separately launched. No full comparable race on the new release or RG477M 20:9 check was performed. The earlier 54 GPU groups on c8 are not presented as a repeat run on the new APK. Frame-time spikes and compatibility differences remain possible; a 60/120 FPS limit does not guarantee that frame rate.

Version **0.2.0-preview.2**, versionCode **5**, ARM64, Android 10+. Debugging disabled.

File: `NFSU-Android-v0.2.0-preview.2-arm64.apk`.

SHA-256: `079244d5f8343cc7274b80398ca85d64717bfad0a38f0b964df73515677a0480`.

[Components and source scope](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/COMPONENTS-EN.md). The previous v0.2.0-preview.1 remains available.


## v0.2.0-preview.1

[Original release and downloads](https://github.com/Wannamingo/NFSU-Android/releases/tag/v0.2.0-preview.1)

### NFSU Android — first public preview

A native Android ARM64 port of Need for Speed Underground. Supports your own Xbox USA game data, Vulkan, touch controls and gamepads. The native base was checked on RG477M with Mali and Huawei MNA-LX9 with Adreno 730; the final package was separately launched on RG477M.

#### Included features

- Vulkan renderer with a separate graphics-preparation thread, geometry arenas and prepared state keys.
- Faster exact conversion of swizzled textures. Texture-change detection is retained.
- A shared VkPipelineCache for graphics-pipeline creation on the System Vulkan path.
- Selection of System Vulkan, built-in MaliSX2 and a compatible custom driver imported from ZIP.
- Russian and English interfaces and an updated launcher title image.
- Two touch layouts: a full gamepad and dedicated driving buttons. Positions can be edited; race-button size adjusts from 40% to 100%.
- Separate touch/gamepad assignments and A/B and X/Y swapping.
- 1×/2×/3× scale, 4:3/16:9 formats and a 60/120 FPS limit.
- Automatic profile backups in Download/NFSU/Saves, the latest 10 generations created by the installation, and restoration/transfers through the launcher.
- Reduced repeated graphics-pipeline compilation, bounded retention of recoverable GPU texture copies, and audio-output fixes for the tested Huawei.

#### Installation

Install the APK, open the launcher and import your own **Xbox USA version of NFS Underground** files using **Import ISO / ZIP**. The PC version and Underground 2 are not supported. After import, tap Play and create or load a local profile.

Keep an external profile backup before updating. Install compatible updates over the previous version without uninstalling. The [detailed controls, settings and save-transfer guide](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/GUIDE-EN.md) is also available in the English guide archive.

#### Preview limitations

Base build c8 passed 54 graphics-test groups on RG477M and separate System Vulkan checks on Huawei. Its native code, drivers and Russian localization are byte-identical in `be140f7c`. Ten host checks covered the new initial settings; the final APK was launched on RG477M, where the image, Russian language and initial render configuration were checked. No full comparable race was performed on that final APK. Occasional frame-time spikes, driver compatibility differences and heat during extended gameplay remain possible. A 120 FPS limit does not guarantee that performance. Screenshots show readings from individual scenes.

APK version: `0.2.0-preview.1`, versionCode 3. Debugging is disabled; the signature is compatible with previous test APKs. Public tag: `v0.2.0-preview.1`.

File: `NFSU-Android-v0.2.0-preview.1-arm64.apk`.

SHA-256: `be140f7c0b18cf159b9d80655a7e46a766ea9fc1edda4164c0b2bf220d9ec4e8`.

You need your own game data. ISO/XBE and user saves are not included. See [components and source scope](https://github.com/Wannamingo/NFSU-Android/blob/main/docs/COMPONENTS-EN.md).
