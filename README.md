# DashCam RoadPrivacy

[![Release Version](https://img.shields.io/badge/Release-v2.0.0-electriccyan?style=for-the-badge&logo=github)](https://github.com/engstaNET/DashCam_RoadPrivacy/releases)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-blue?style=for-the-badge&logo=windows)](https://github.com/engstaNET/DashCam_RoadPrivacy)
[![License](https://img.shields.io/badge/License-Freeware-green?style=for-the-badge)](LICENSE)
[![Privacy](https://img.shields.io/badge/Privacy-100%25%20Local%20%2F%20Offline-success?style=for-the-badge)](PRIVACY.md)

**DashCam RoadPrivacy** is a high-performance, standalone Windows application engineered for automated AI-powered video anonymization. Designed specifically for DashCam footage, action camera recordings, and public video captures, it automatically detects and redacts faces and vehicle license plates while offering GPU DirectML hardware acceleration, interactive manual post-processing redaction, and customizable compression.

![DashCam RoadPrivacy Interface](DashCam_RoadPrivacy_App_Screenshot.png)

---

## 🌟 Key Features

- **🎯 Vehicle-Restricted License Plate Detection:**
  - **YOLOv8 & RT-DETRv2 Pipeline:** YOLOv8 identifies vehicles first; RT-DETRv2 ONNX scans vehicle regions exclusively to eliminate background false positives on pavement, walls, and road markings.
  - **1080p Detail Tiles:** Alternating high-resolution detail passes double detection recall for distant and parked vehicle plates on 1080p+ footage.
  - **Look-Behind Redaction:** Frames are buffered to ensure plates and faces are redacted even before detection confirmation thresholds are met.
- **⚡ Face Detection:**
  - Ultra-fast OpenCV YuNet DNN Face Detector tuned for distant and small faces in public street scenes.
- **🚀 GPU Hardware Acceleration & Auto-Benchmarking:**
  - Microsoft DirectML & ONNX Runtime support for NVIDIA, AMD, and Intel GPUs.
  - Startup benchmark automatically evaluates DirectML vs. CPU cores and selects the fastest provider.
- **✏️ Interactive Manual-Processing Mode:**
  - Keyframe-based timeline editor with automated CSRT tracking, backward tracking, jump/end/delete, and manual test detection.
- **🔒 100% Local & Private:** Runs entirely offline on your PC. No internet connection required, zero cloud uploads, and zero telemetry.
- **✂️ Lossless Stream-Copy Video Trimming:** Keyframe-aligned sub-second fast trim without video re-encoding when cutting clips.
- **🎬 Single-Pass Video Compression:**
  - Direct FFmpeg streaming into NVIDIA NVENC, Intel QSV, AMD AMF, or multi-threaded CPU libx264.
  - Redaction modes: Gaussian Blur, Mosaic Pixelation, and Solid Blackout.
- **🛡️ Metadata Stripping & Audio Control:** Strip EXIF/GPS telemetry metadata and optionally mute or preserve audio tracks.
- **📦 Portable Standalone Executable:** Self-contained package bundling FFmpeg and all AI models. No Python installation or external dependencies required. Simply download, extract, and run.

---

## 📥 Download & Installation

### Latest Release: **v2.0.0**

1. Go to the [Releases](https://github.com/engstaNET/DashCam_RoadPrivacy/releases) page.
2. Download `DashCam_RoadPrivacy_v2.0.0_win64.zip` (Portable ZIP) or `RoadPrivacy_v2.0.0.exe` (Single Standalone Executable).
3. If using the ZIP archive, extract it to any directory on your PC.
4. Launch `RoadPrivacy_v2.0.0.exe`.

> **Note for Windows Defender / SmartScreen:**  
> Since the executable is freshly built and self-signed, Windows Defender SmartScreen may show an informational warning. Click **More info** -> **Run anyway**.

---

## 🔐 Security & SHA-256 Verification

To ensure that your download has not been tampered with, you can verify the SHA-256 hash against the official values below:

| File Name | Target Platform | SHA-256 Hash |
| :--- | :--- | :--- |
| **`DashCam_RoadPrivacy_v2.0.0_win64.zip`** | Windows 10/11 x64 (Portable ZIP) | `674044f17867bfbedfd7493b15ecbf4f7f0209ff0992581355a03fe43483cc69` |
| **`RoadPrivacy_v2.0.0.exe`** | Windows 10/11 x64 (Standalone EXE) | `987e06809f268055f4bac4d68431b2e57eb4ba4a03ea686d65e7eb2f8f3bcafc` |

### Verifying Hashes in Windows PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 .\DashCam_RoadPrivacy_v2.0.0_win64.zip
```

---

## 🖥️ System Requirements

- **Operating System:** Windows 10 or Windows 11 (64-bit)
- **Processor:** Dual-Core x86-64 CPU (Quad-Core or higher recommended)
- **Memory:** 4 GB RAM (8 GB recommended)
- **Graphics (Optional):** DirectX 12 compatible GPU for DirectML hardware acceleration (NVIDIA GeForce, AMD Radeon, Intel Arc/Iris)

---

## 📄 License & Attribution

This software is distributed under the [Freeware License Agreement](LICENSE). Free to use for personal and commercial purposes.  
For third-party components and AI model licenses, see [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md).

Developed by **Artur F.** ([engstaNET](https://github.com/engstaNET)).
