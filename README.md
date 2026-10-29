# NEXUS FF PANEL

NEXUS FF PANEL is a premium Android gaming utility for players who want quick access to performance information, a floating control panel, display tuning, and safe system/device guidance without claiming unsupported game hacks.

## Features
- Premium AMOLED gaming dashboard with device status, battery, memory, and selected game information.
- Floating overlay panel that can be launched from the app and kept accessible while gaming.
- Gaming tool shortcuts for game launch, Android game settings, brightness, and DND guidance.
- Screen Shift capability page with validation and restore flow.
- Shizuku status detection and permission guidance without forcing privileged behavior.
- Settings persistence with user-configurable floating-panel size and opacity.
- Native Android Java/XML implementation using the Android SDK and Material components.

## Supported functionality without Shizuku
- Dashboard display, battery and memory readouts.
- Installed game detection and game launch by package name.
- Floating overlay service on devices that grant `SYSTEM_ALERT_WINDOW`.
- Settings persistence and UI logic.
- Notification and power-state guidance.

## Features that require Shizuku or special permissions
- Display density/size adjustments are only attempted when Shizuku is installed, running, and permission is granted.
- DND shortcut and some device-specific settings are only available when the OS allows access.
- Overlay permission is required for the floating panel.
- Notification permission may be required on Android 13+.

## Import into CodeAssist
1. Open CodeAssist/Android Studio.
2. Choose Import Project.
3. Select the repository folder.
4. Let Gradle sync.
5. If prompted, install the required Android SDKs.

## Build and install
1. Open a terminal in the repository root.
2. Run `./gradlew assembleDebug`
3. Install with `adb install -r app/build/outputs/apk/debug/app-debug.apk`

## Start and stop floating panel
- Open the app and choose `Floating Panel` from the dashboard or the overlay shortcut.
- Grant overlay permission when prompted.
- Tap the floating icon to expand/collapse the panel.
- Use the `Stop Panel` action to end the overlay service.

## Restore original display settings
- Use the Screen Shift screen.
- Tap `Restore Original Settings` only after verifying the system supports the change and Shizuku permission is active.
- If Shizuku is unavailable, the app will explain the requirement and keep the original settings unchanged.

## Project status
This repository is a Java/XML Android project intended for CodeAssist/Android Studio. Some privileged device features remain capability-based and will show a graceful fallback when unsupported.

## Known limitations
- Display size and density changes are device-specific and may not be available.
- Some manufacturer-specific game settings are OS- and device-dependent.
- The app does not bypass anti-cheat or modify game internals.
