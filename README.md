# ch57x-keyboard

Config for my 3x4 macro keypad (12 keys + 1 knob, VID:PID `1189:8890`), programmed with [kriomant/ch57x-keyboard-tool](https://github.com/kriomant/ch57x-keyboard-tool).

## Setup

```sh
# macOS: download prebuilt binary
curl -sL https://github.com/kriomant/ch57x-keyboard-tool/releases/download/v1.7.0/ch57x-keyboard-tool-universal-apple-darwin.tar.gz | tar xz
./ch57x-keyboard-tool validate mapping.yaml
./ch57x-keyboard-tool upload mapping.yaml   # keyboard must be USB-connected
```

## Layers

### Layer 1 — Meetings & Comms (Zoom + Slack + media)

| Keys | Action |
|---|---|
| Row 1 | Zoom: mute `⌘⇧A`, video `⌘⇧V`, share `⌘⇧S`, leave `⌘W` |
| Row 2 | Slack: quick switcher `⌘K`, new message `⌘N`, set status `⌘⇧Y`, edit last message `↑` |
| Row 3 | Media: play, prev, next, mute |
| Knob | ccw volume down / press mute / cw volume up |

### Layer 2 — Deep work / app switching

Chords bound in Raycast → Open App commands:

| Chord | App |
|---|---|
| `⌃⌥C` / `⌃⌥L` / `⌃⌥S` / `⌃⌥O` | Cursor / Claude / Slack / Obsidian |
| `⌃⌥B` / `⌃⌥T` / `⌃⌥P` / `⌃⌥M` | Chrome / Warp / Conductor / MacWhisper |
| Row 3 | Cursor: agent `⌘I`, chat `⌘L`, inline `⌘K`, accept `⌘↩` |
| Knob | ccw prev tab / press close tab / cw next tab |

### Layer 3 — Capture & tracking

| Keys | Action |
|---|---|
| `⌃⌥⇧T` | Todoist quick-add (bind in Todoist prefs) |
| `⌃⌥⇧Y` | Toggl start/stop (bind in Toggl prefs) |
| `⌃⌥⇧D` / `⌃⌥⇧W` | Obsidian daily / weekly note (via Raycast) |
| `⌘O`, `⌃⌥⇧C` | Obsidian quick switcher, clipboard history |
| Rest | Spare `⌃⌥⇧1–6` chords for future Raycast scripts |
| Knob | ccw scroll up / press click / cw scroll down |

## App-side setup required

The tool only writes HID key events — chords are inert until bound:

- **Zoom** → Settings → Keyboard Shortcuts → enable global hotkey for mute
- **Raycast** → bind `⌃⌥*` chords to Open App / script commands
- **Todoist** → Settings → quick-add shortcut
- **Toggl Track** → Preferences → global start/stop shortcut
