<div align="center">

# WindowDeck

**One main window, up to four side previews, one workspace.**

![ColorOS 17](https://img.shields.io/badge/ColorOS-17-2563eb)
![LSPosed](https://img.shields.io/badge/Framework-LSPosed-8b5cf6)
![Root required](https://img.shields.io/badge/Root-required-d97706)
![Beta](https://img.shields.io/badge/Status-Beta-f59e0b)

[简体中文](README.md) · **English**

[Download APK](https://github.com/Xposed-Modules-Repo/io.github.xitc.windowdeck/releases) · [Changelog (Chinese)](CHANGELOG.md) · [Source](https://github.com/xitc/windowdeck) · [Report an issue](https://github.com/xitc/windowdeck/issues)

</div>

---

WindowDeck is an experimental LSPosed module for **ColorOS 17 / C17**. It uses the ROM's live task embedding APIs to display up to five applications in a main window and side previews. Interact with the main app, tap a side preview to switch, and add, replace or remove apps as needed.

Current release: **0.4.8-beta.28**. Application ID: **`io.github.xitc.windowdeck`**. The module depends on private ColorOS APIs and is not an official port of vivo's workspace feature.

## Features

- One interactive main window and up to four live side previews.
- Tap to switch; long-press for management; select an existing app to return to its existing task.
- Add, replace and remove apps while running; swipe side previews to remove them.
- Left/right and top/bottom layouts; landscape device orientation uses left/right layout.
- “Add to workspace” in the launcher swipe-up split-screen / floating-window panel.
- Restore an existing workspace and pin one app against in-workspace removal or replacement.
- Rotate landscape app content when holding the phone upright; app compatibility still varies.

Side previews are for viewing and switching, not direct app interaction. Optional trapezoid side previews are off by default.

## Compatibility

| Item | Current target |
| --- | --- |
| Device | OnePlus 13, `PJZ110` |
| OS | ColorOS 17 / Android 17 |
| Firmware | `PJZ110_17.0.0.100(SP01CN01)`, C17 / F.04 |
| Launcher | `17.3.9`, versionCode `170030009` |
| Tested root / framework baseline | KernelSU + LSPosed; legacy Xposed API 82 |
| Scope | `com.oplus.pscanvas`, `com.android.launcher` |

The old C.93 / Android 16 baseline is no longer supported. Other devices, OxygenOS, realme UI, other ROMs and firmware updates have not been verified. Minimum APK API 35 is an installation requirement, not an Android 15 compatibility claim. Check the full firmware and launcher versions, not just the OS name.

## Installation

1. Download an APK from [this repository's Releases](https://github.com/Xposed-Modules-Repo/io.github.xitc.windowdeck/releases). Beta and nightly builds are experimental. [Source repository Releases](https://github.com/xitc/windowdeck/releases) also provide builds and checksums.
2. Install it and enable WindowDeck in LSPosed.
3. Select `com.oplus.pscanvas` and `com.android.launcher`. This release does not require the System Framework (`android`) scope.
4. Grant WindowDeck superuser access in your root manager.
5. Restart both the launcher and multi-window host processes after enabling or updating. This interrupts the current foreground and workspace session; finish ongoing work first.
6. Open WindowDeck, choose apps and create a workspace, or restore an existing one.

### Migration from the old package

beta.28 changes `dev.windowdeck.app` to `io.github.xitc.windowdeck`. The new package installs separately and cannot update the old package. Settings and permissions do not migrate.

Exit the old workspace and disable the old module before enabling the new one. Grant root access again, select both scopes and restart both hosts. Enable only one WindowDeck module. Future releases with the same new package and signing certificate can update each other; locally signed APKs may use a different certificate.

## Usage and limitations

Tap a side preview to make it the interactive main window. Use `＋`, the replacement menu or the launcher's “Add to workspace” entry to manage apps. Long-press a side preview or use `•••` for management and layout controls. Back first goes to the main app; backing out from its root page returns to the launcher while keeping the workspace.

Creating a workspace replaces the current multi-window container. Only the primary user is supported; work profiles and multiple users are not supported. Animation handoffs, orientation changes, complex IMEs, multi-touch, lock screen, process recovery and long sessions still need further testing. Pinning only protects in-workspace operations. OTA updates may require new adaptation.

beta.28 is a package migration of public beta.27. Release and layout regression tests, APK compilation, package/version checks and the original release certificate checks passed. **The new-package build has not undergone device installation or behavior acceptance.** Earlier limited device results apply only to their tested firmware and apps. Local dev.128 animation changes are not included.

If the launcher entry is missing, check firmware, launcher version, scopes and host restarts. Hooks are skipped when the ROM contract does not match.

## Disable and report issues

Exit the workspace, disable the module in LSPosed, restart both hosts, then uninstall and revoke root access. No app-data reset is needed.

Report issues at [xitc/windowdeck](https://github.com/xitc/windowdeck/issues), including module version, device, full firmware, launcher version, LSPosed/root details and reproduction steps. Remove personal information from screenshots and logs.

Source code, build scripts and Actions are in [xitc/windowdeck](https://github.com/xitc/windowdeck). This repository hosts module documentation and APK releases.
