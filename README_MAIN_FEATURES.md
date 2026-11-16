# RVCI — Main Features

RVCI (Rust Volume Control Interface) controls Windows audio volumes and output devices using custom Arduino hardware.

## Core Features

- **Volume control knobs** mapped to:
  - System / master volume
  - A single process/app
  - All "Other" (unmapped) apps
  - A microphone / capture device
  - A specific output device / endpoint (including virtual channels such as SteelSeries Sonar Game/Chat/Media/Aux)

- **Volume curves**: linear or logarithmic (MacOS-style) for finer control at low end.

- **Output switcher**: a physical 3-way toggle switches audio between configured outputs; up to 16 outputs (first two stay on firmware `WORKS 1` / `WORKS 2`).

- **On-Screen Display (OSD)** showing volume/state changes; expandable for longer process names.

- **Configurable buttons** wired to Arduino pins (`buttonPins[]` in `firmware.ino`), each set to:
  - Mute Knob (toggle mute for a specific knob)
  - Media (Play/Pause, Next, Previous, Stop, Vol+, Vol-, Mute)
  - Keys (recorded key combo, macropad-style)
  - None

- **Function-key buttons (F1–F24)** bindable via the Keys action.

- **Multi-process knobs**: one knob controls several processes at once (comma-delimited `process_name`).

- **Per-process output cycling via buttons**: pressing a button moves selected processes to the next checked output.

- **Debug console / launch-at-startup** options.

- **Config persistence**: GUI edits save to `mapping.json` in `%APPDATA%\Roaming\RVCI`; older Output 1/2-only configs auto-migrate.

## Hardware

- Arduino Nano
- Potentiometers (any count)
- One 3-way toggle switch
- Optional buttons wired to extra pins

## Running

1. Flash `firmware.ino` to the Arduino.
2. Download `RVCI_setup.exe` from the releases page.
3. Launch (minimized to tray).
4. Right-click tray icon → "Open Settings".
5. Configure COM port, baudrate (default 115200), knobs, buttons, outputs.