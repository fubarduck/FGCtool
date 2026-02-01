# Changelog

## [1.1] - 2026-02-01

### New Features
- **Expanded controller support**: Added support for DualShock 4, PS5 DualSense, Nintendo Switch Pro, and Nintendo Switch 2 Pro Controllers
- **Configurable per-game startup delay**: Set custom delays in `games.txt` for games with long loading screens
- **Hot-reload for games.txt**: Changes are applied automatically without restarting the app

### Improvements
- Controller hotkey now requires a long press to prevent accidental triggers during gameplay
- Status overlay now waits for game window to be ready before appearing
- Improved overlay positioning for games with exclusive loading screens
- Custom display names now work even when matching the process name

### Bug Fixes
- Fixed startup overlay not appearing over games with exclusive loading screens
- Fixed audio restore not triggering reliably in some scenarios

## [1.0.2] - 2025-01-24

### Bug Fixes
- Fixed tray context menu appearing in wrong position on high-DPI displays
- Fixed main window being cut off on scaled displays (e.g., 4K at 300% scaling)

## [1.0.1] - 2025-01-23

### Improvements
- Main window now displays on manual launch (still starts minimized via auto-start)
- Settings file now updated immediately when audio device is changed (consistent with other settings)

### Bug Fixes
- Fixed audio not restoring when monitor powers back on after being turned off

## [1.0] - 2025-01-18

Initial stable release.
