<div align="center">

<picture>
  <img alt="OrcaSlicer logo" src="resources/images/OrcaSlicer.png" width="15%" height="15%">
</picture>

# OrcaSlicer K1-CFS

[![Build all](https://github.com/JRMSBr/OrcaSlicer-K1-CFS/actions/workflows/build_all.yml/badge.svg?branch=main)](https://github.com/JRMSBr/OrcaSlicer-K1-CFS/actions/workflows/build_all.yml)

**OrcaSlicer v2.4.0 with native Creality CFS integration for the K1 family.**

</div>

---

## What is this fork

This is a fork of [OrcaSlicer v2.4.0](https://github.com/OrcaSlicer/OrcaSlicer) with **Creality CFS** integration ported from [HimAndRobot's OrcaSlicer-CFS fork](https://github.com/HimAndRobot/OrcaSlicer-CFS) (originally developed for v2.3.2).

The goal is to bring the same direct workflow between Orca and CFS, now on top of the latest OrcaSlicer base:

- sync filament colors from CFS into Orca
- sync changes made in Orca back to CFS
- automatically switch filament presets by material type
- keep an automatic mode that is visible, simple, and easy to configure

---

## What this fork adds

- `CFS` button in the filament sidebar
- Visual sync status
- Color sync: CFS → Orca
- Color sync: Orca → CFS
- Automatic filament preset switching by material type
- CFS settings modal
- Continuous sync when automatic mode is enabled

---

## Supported printers

The CFS button and integration are shown only when the active printer profile belongs to the K1 family:

- `K1`
- `K1C`
- `K1 Max`

The printer also needs to be configured normally in Orca using its machine host settings.

---

## How it works

**With CFS disabled:**
- Orca does not run automatic sync
- The button stays in its inactive state
- You can still prepare the configuration before enabling it

**With CFS enabled:**
- Orca enters automatic sync mode
- CFS updates can change filament colors in Orca
- If automatic preset switching is enabled, the filament preset can also be switched

**When you change a color or preset in Orca:**
- This fork can push that change back to CFS
- The machine/CFS state is updated, not only the local UI

---

## Tutorial

### 1. CFS disabled

Use this state when you do not want automatic sync.

![CFS disabled](https://github.com/HimAndRobot/OrcaSlicer-CFS/raw/v2.3.2/public/1.png)

- Automatic sync is off
- Orca will not pull CFS updates on its own
- You can still prepare the configuration before enabling it

### 2. CFS enabled

When you enable `CFS`, the button changes to its active state.

![CFS enabled](https://github.com/HimAndRobot/OrcaSlicer-CFS/raw/v2.3.2/public/2.png)

- Orca enters automatic sync mode
- New CFS updates can change filament colors in Orca
- If automatic preset switching is enabled, the preset can also be switched

### 3. CFS settings

Click `Configure CFS` to open the settings modal.

![CFS settings](https://github.com/HimAndRobot/OrcaSlicer-CFS/raw/v2.3.2/public/3.png)

Here you can:

- Enable or disable automatic filament preset switching
- Choose which Orca preset should be used for each material type coming from CFS

Example:
- `PLA` → your Orca PLA preset
- `PETG` → your Orca PETG preset

---

## Supported sync flows

### CFS → Orca
- Filament color
- Material type
- Automatic application when CFS sync is enabled

### Orca → CFS
- Color changes made in Orca
- Preset/material changes when preset mapping is configured

---

## Expected behavior

**If you change the color in CFS** with sync enabled:
- Orca receives the update
- The matching filament slot color is updated

**If you change the color in Orca** with outbound sync available:
- The fork sends that change to CFS
- The machine state is updated too

**If you change the preset in Orca** with automatic material mapping enabled:
- The fork uses the configured mapping
- And can update the matching material state in CFS

---

## Known limitations

- Only tested with a standard **CFS** and a **single CFS unit**
- Has **not** been validated with **CFS-C** or multiple chained CFS units

---

## Download

Builds for this fork are published in the [Releases](../../releases) tab as:

- Windows installer (`.exe`)
- Windows portable build

---

## Project base

| Component | Repository |
|---|---|
| Slicer base | [OrcaSlicer v2.4.0](https://github.com/OrcaSlicer/OrcaSlicer/releases/tag/v2.4.0) |
| Original CFS feature | [HimAndRobot/OrcaSlicer-CFS @ v2.3.2](https://github.com/HimAndRobot/OrcaSlicer-CFS/tree/v2.3.2) |

---

## License

This repository follows the same license as the upstream OrcaSlicer project: **GNU Affero General Public License, version 3**.
