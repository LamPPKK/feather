# Feather

An on-device iOS/iPadOS (and Mac Catalyst) application manager and `.ipa` signer (`v2.9.0`) using certificates from the Apple Developer Program.

> Forked from [claration/feather](https://github.com/claration/feather) (`khcrysalis/Feather`). See [LICENSE](LICENSE) for full license details.

## Features

- Manage AltSource repositories and app sources (`AltSourceKit`, `app-repo.json`).
- Import, inspect, and sign `.ipa` packages directly on-device powered by `Zsign` (`Zsign-Package`).
- Install and communicate with iOS devices via `IDeviceKitten` (`IDeviceKit`).
- Targets both `iphoneos` and `maccatalyst`.

## Tech Stack & Requirements

- **Languages**: Swift / C++ (`Zsign`)
- **Modules & Submodules**: `AltSourceKit`, `NimbleKit`, `Zsign`, `IDeviceKitten`
- **Requirements**: iOS 16.0+ / Mac Catalyst, Xcode, Git submodules, `jq` (when building via `Makefile`)

## Project Structure

```text
Feather/
├── Feather.xcodeproj
├── Feather.xcworkspace
├── Feather.xcconfig
├── Makefile
├── LICENSE
├── app-repo.json
├── Feather/
│   ├── FeatherApp.swift
│   ├── Backend/
│   ├── Views/
│   ├── Utilities/
│   ├── Extensions/
│   ├── Resources/
│   └── Supporting Files/
├── AltSourceKit/
├── NimbleKit/
├── Zsign/               (Git submodule)
└── IDeviceKitten/       (Git submodule)
```

## Getting Started

1. Clone the repository recursively with all submodules:
   ```bash
   git clone --recursive https://github.com/LamPPKK/feather.git
   cd feather
   ```
   *(If already cloned without submodules, run `git submodule update --init --recursive`.)*
2. Open the workspace in Xcode:
   ```bash
   open Feather.xcworkspace
   ```
   Or build using the `Makefile` (requires `xcodebuild` and `jq`):
   ```bash
   make iphoneos
   # or for Mac Catalyst:
   make maccatalyst
   ```
