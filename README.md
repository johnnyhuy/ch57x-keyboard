# ch57x-keyboard

Config for my **Tessl 2×3** macro keypad (6 keys + 1 knob, VID:PID `1189:8890`), programmed with [kriomant/ch57x-keyboard-tool](https://github.com/kriomant/ch57x-keyboard-tool).

No side layer button — single layer only.

## Setup

```sh
# macOS: download prebuilt binary
curl -sL https://github.com/kriomant/ch57x-keyboard-tool/releases/download/v1.7.0/ch57x-keyboard-tool-universal-apple-darwin.tar.gz \
  | tar xz -C ~/.local/bin ch57x-keyboard-tool

# keyboard must be USB-connected
ch57x-keyboard-tool validate mapping.yaml
ch57x-keyboard-tool upload mapping.yaml
```

Local copy used on this machine: `~/ch57x-mapping.yaml` (keep in sync with `mapping.yaml` here).

## Layout

Knob on the right. Top → bottom, left → right:

```
[ Esc ] [ ⌘A then ⌫  clear ] [ ⌘↵  accept ]
[ ⌘⇧4 ] [ ⌘V  paste        ] [ ⌃⇧D dictation ]
                              ⟳ undo · play/pause · redo
```

| Control | Bind | Notes |
|---------|------|--------|
| Top-left | `Esc` | Cancel |
| Top-middle | `⌘A`, `⌫` | Select all + clear |
| Top-right | `⌘↵` | Accept / submit (agents) |
| Bottom-left | `⌘⇧4` | Screenshot |
| Bottom-middle | `⌘V` | Paste |
| Bottom-right | `⌃⇧D` | macOS Dictation |
| Knob CCW | `⌘Z` | Undo |
| Knob press | `play` | Play/pause |
| Knob CW | `⌘⇧Z` | Redo |

## macOS Dictation

System Settings → Keyboard → Dictation:

- **Dictation** on
- **Shortcut** → customise to **⌃⇧D** (not the 🎤 key — pad can’t send that)

## Related

- Foot pedals (separate hardware): program with [rgerganov/footswitch](https://github.com/rgerganov/footswitch), same `⌃⇧D` chord for Dictation.
