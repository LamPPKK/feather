# Feather

Ứng dụng quản lý và ký (sign) file `.ipa` trực tiếp trên thiết bị iOS/iPadOS (và Mac Catalyst), sử dụng chứng chỉ thuộc Apple Developer Program (phiên bản dự án `2.9.0`).

> Fork từ [claration/feather](https://github.com/claration/feather) (`khcrysalis/Feather`). Xem chi tiết giấy phép sử dụng trong file [LICENSE](LICENSE).

## Tính năng chính

- Quản lý kho ứng dụng / nguồn AltSource (`AltSourceKit`, `app-repo.json`).
- Nhập, quản lý và ký file `.ipa` trực tiếp trên thiết bị với nhân ký `Zsign` (`Zsign-Package`).
- Hỗ trợ giao tiếp và cài đặt ứng dụng trên thiết bị iOS qua `IDeviceKitten` (`IDeviceKit`).
- Hỗ trợ đa nền tảng mục tiêu: `iphoneos` và `maccatalyst`.

## Công nghệ & Yêu cầu

- **Ngôn ngữ**: Swift / C++ (Zsign)
- **Framework & Module nội bộ**: `AltSourceKit`, `NimbleKit`, submodule `Zsign`, submodule `IDeviceKitten`
- **Yêu cầu**: iOS 16.0+ / Mac Catalyst, Xcode, Git submodules, `jq` (nếu build bằng `Makefile`)

## Cấu trúc thư mục

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

## Hướng dẫn cài đặt & chạy

1. Clone repository kèm đầy đủ submodules:
   ```bash
   git clone --recursive https://github.com/LamPPKK/feather.git
   cd feather
   ```
   *(Nếu đã clone trước đó mà chưa có submodules, chạy: `git submodule update --init --recursive`)*
2. Mở bằng Xcode:
   ```bash
   open Feather.xcworkspace
   ```
   Hoặc build qua `Makefile` (yêu cầu đã cài `xcodebuild` và `jq`):
   ```bash
   make iphoneos
   # hoặc cho Mac Catalyst:
   make maccatalyst
   ```
