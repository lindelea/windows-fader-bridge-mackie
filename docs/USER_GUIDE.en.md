# Windows Fader Bridge for Mackie Control User Guide

[简体中文](USER_GUIDE.zh-CN.md) ・ [日本語](USER_GUIDE.ja.md) ・ [Home](../README.md)

## What it does

The app lets a MIDI controller in Mackie Control / MCU mode operate the Windows audio mixer. Faders, encoders, buttons, LEDs, meters, and playback information are synchronized with Windows in real time.

It is not a device-specific driver. iCON P1-Nano has been physically verified. Other MCU controllers use the same core protocol, but their optional buttons, displays, and lamps may differ.

## Requirements

- Windows 11, 64-bit.
- A MIDI controller with Mackie Control / MCU mode.
- The manufacturer's USB driver, if your controller requires one.

EuControl, Avid software, virtual MIDI cables, and build tools are not required.

## Install

1. Download the file ending in `Setup-x64.exe` from [Releases](https://github.com/lindelea/windows-fader-bridge-mackie/releases/latest).
2. Quit any portable copy you previously started, run the installer, and follow the prompts.
3. Open **Windows Fader Bridge for Mackie Control** from the Start menu.

The project does not currently have a paid Windows code-signing certificate, so Windows may show “Unknown publisher.” Download only from this repository and compare the file with the SHA-256 value on the release page if needed.

## First connection

1. Put the controller in **Mackie Control / MCU** mode, not HUI.
2. Open the app's **Devices** page and add or select a device.
3. Choose its MIDI input and output. Input carries controls to the computer; output carries feedback to the surface.
4. Use the Generic Mackie Control profile for ordinary devices, or the P1-Nano profile for that model.
5. Keep touch protection enabled and save. Auto-connect is on by default; manual mode uses **Connect device**.

Do not let Cubase, another DAW, and this app open the same MIDI port pair at the same time. P1-Nano can place Cubase and Windows control on separate DAW layers; use the dedicated port pair selected for the Windows layer.

## Default controls

- Channel fader: volume of a Windows application or audio device.
- Master fader: Windows default output volume.
- Encoder 1: current-channel volume.
- Encoder 2: current-channel pan/balance; press to return to center.
- Mute / Solo: change and display the real channel state.
- Bank / Channel: page through or select online channels.
- Meters: live audio levels.
- Transport: controls players that support Windows media sessions and may display title, artist, and time.

Closed applications leave the online list and new applications join automatically. The target list is not reordered while a fader is touched.

## Custom buttons and encoders

Use **Button mapping**, **Encoder mapping**, and **Jog & directions** to select a physical control and assign a Windows, media, window, or audio command. While learning controls on the selected device, recognized input is previewed and not executed.

Left, right, and press actions of encoders 3–8 are independent. Ordinary Jog, Move, and Zoom are also assigned separately; Navi / Focus retain their native device meaning.

P1-Nano users can apply the Windows 80-key preset from the Devices page. Back up your own iMAP configuration first. The feature changes only the designated touchscreen positions and does not write other DAW layers. Other devices use control learning for customization.

## Settings and shortcut

The app provides English/Chinese language selection, close to tray, launch at Windows sign-in, and a global summon shortcut. The default is `Ctrl+Alt+Shift+M` and can be re-recorded. Closing the window normally hides it; use the tray menu to restart or fully quit.

Each controller keeps its own port pair, connection policy, and assignments. Up to 16 independent MCU main units can be configured, but a MIDI port cannot be reused by two configurations.

## Troubleshooting

**No MIDI port:** confirm that the device is powered and visible to Windows, close any DAW that may own the port, then select it again.

**Controls work but motors/LEDs do not:** verify the output port and make sure you did not select an iMAP or maintenance port.

**Master or channel arrows do not work:** confirm MCU mode and a matching input/output pair. On P1-Nano, use the same-numbered ports for the selected DAW layer.

**Uninstall:** use Windows Settings → Apps → Installed apps. Device mappings are retained for a future reinstall.

## Report a problem

Open a [GitHub issue](https://github.com/lindelea/windows-fader-bridge-mackie/issues) with the controller model, firmware, selected MIDI ports, reproduction steps, and result. Logs may contain application and device names, so review them before uploading.
