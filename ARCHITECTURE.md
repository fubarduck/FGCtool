# FGC Tool Architecture

## Estimated Performance Impact (Typical Gaming PC)
- **CPU (idle, no controllers):** about 0.05-0.3% average.
- **CPU (1-2 controllers connected):** about 0.3-1.0% average due to input polling.
- **Memory:** roughly 60-130 MB (WPF UI + device libraries + resources).
- **GPU:** effectively 0% average; the overlay animation is a tiny compositor effect and is typically well under 1% for a fraction of a second.

These are estimates based on the app's behavior and typical modern gaming PCs. The app runs as a light background tray utility and avoids heavy or continuous work.

---

## Architecture Overview

FGC Tool is a Windows-only background utility built on .NET 8 WPF. It runs as a tray app, watches for fighting game launches, and helps ensure display and audio settings are optimal for competitive play.

This overview explains what the app does and the system APIs it uses so users can understand safety and impact.

### Core Components
- **WPF UI + Tray:** Settings window, alerts, and overlay notifications. Uses a system tray icon for quick access.
- **Process Monitoring:** Detects configured game processes by name and triggers overlays or warnings when a game starts.
- **Display Monitoring:** Reads current display topology and refresh rates and can request rate changes when needed.
- **Audio Monitoring:** Observes the default audio device and restores a preferred device to prevent unexpected device switching.
- **Controller Hotkey (optional):** A long-press hotkey on supported controllers triggers the status overlay.
- **Settings + Updates:** Settings are stored locally; optional update checks on startup.

### Technology and Libraries
- **UI:** WPF (.NET 8, Windows-only).
- **Audio Devices:** NAudio (Windows Core Audio APIs).
- **Controllers:** XInput (SharpDX.XInput) for Xbox controllers; DirectInput (Vortice.DirectInput) for DS4/fightsticks; Raw Windows HID for DualSense and Nintendo controllers.
- **Display:** Windows Display Configuration APIs (native interop).
- **Tray:** Hardcodet.NotifyIcon.Wpf.

### Data & Privacy
- **Local settings only:** Stored under `%LocalAppData%\FGCtool` (settings and game list).
- **No gameplay capture:** The app does not record video, audio, or inputs.
- **Process checks are local:** It matches process names against your configured list.
- **Update checks:** Optional and performed on startup when enabled.
