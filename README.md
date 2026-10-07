# Flat Madness — ReaPack

JSFX effects for REAPER by Dmytro Hapochka (gapalil001).

## Install with ReaPack

1. In REAPER, open **Extensions → ReaPack → Import repositories**.
2. Paste this URL:

   ```text
   https://raw.githubusercontent.com/gapalil001/ReaPack/main/index.xml
   ```

3. Open **Extensions → ReaPack → Browse packages**, find **Flat Madness**, select the effects you want, and choose **Install → Apply**.

The effects install directly into `Effects/Flat Madness/` inside the REAPER resource folder. Their original filenames are preserved. BBQ's five PNG files install into `Effects/Flat Madness/BBQ-assets/` automatically.

If these effects were previously installed manually at the same paths, keep a backup of any personal edits before using ReaPack to manage them.

## Included effects

| Effect | File | ReaPack version |
| --- | --- | --- |
| BurnDrive | `Flat Madness BurnDrive.jsfx` | 1.0 |
| BurnPressor Ultra | `Flat Madness BurnPressor Ultra.jsfx` | 1.0 |
| Clipper | `Flat Madness Clipper.jsfx` | 1.0 |
| MultiTrans | `Flat Madness MultiTrans.jsfx` | 1.0 |
| Panorama | `Flat Madness panorama.jsfx` | 1.0 |
| BBQ Grill saturator | `FM BBQ.jsfx` | 1.0 |
| MultiComp 2 | `FM MultiComp 2.jsfx` | 2.0 |
| MultiGate 2 | `FM MultiGate 2.jsfx` | 2.14 |
| TotalView | `FM TotalView.jsfx` | 1.0 |

The first ReaPack release adds packaging metadata only. The original processing code, slider IDs, filenames, and artwork are preserved. The original `version: 1.0 GR` label in TotalView remains unchanged; its ReaPack release version is 1.0.

## BBQ resources

Keep `BBQ-assets/` beside `FM BBQ.jsfx`, with these exact names:

- `grill-background.png`
- `bbq-knob-35-atlas.png`
- `meter-body.png`
- `meter-needle-35-atlas.png`
- `meter-glass.png`

The two atlases each contain 35 frames. Preserve image dimensions, frame layouts, and transparency when editing artwork.

`JSFX/BBQ-assets/bbq-dsp-test.jsfx` is a developer verification effect that generates its own test signal. It is preserved in the source repository and marked `@noindex`; it is not installed with BBQ.

## Presets and existing projects

The installation path `Effects/Flat Madness/` and original filenames are kept for existing projects and FX chains. No presets are included in this first release. Preset files can be added after their format and effect references have been checked.

## Maintaining this repository

Package sources are under `JSFX/`. ReaPack's repository display name **Flat Madness** is also its installation folder name. Each package maps its installed files one directory above the `JSFX` category using `@provides`, keeping `Effects/Flat Madness/` stable.

For an effect update, change its `// @version` and `// @changelog`. Keep old versions in `index.xml`: their download URLs point to the exact source commit. GitHub Actions checks the packages and updates the index after a push to `main`.

The local index can be checked and generated with Ruby, Pandoc, and `reapack-index` 1.2.3:

```sh
gem install reapack-index --version 1.2.3
reapack-index --check
reapack-index
```

Packaging reference: <https://github.com/cfillion/reapack-index/wiki/Packaging-Documentation>
