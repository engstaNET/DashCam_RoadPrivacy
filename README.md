# DashCam RoadPrivacy

[![Release Version](https://img.shields.io/badge/Release-v2.0.0-electriccyan?style=for-the-badge&logo=github)](https://github.com/engstaNET/DashCam_RoadPrivacy/releases)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-blue?style=for-the-badge&logo=windows)](https://github.com/engstaNET/DashCam_RoadPrivacy)
[![License](https://img.shields.io/badge/License-Freeware-green?style=for-the-badge)](LICENSE)

DashCam RoadPrivacy blurs license plates and faces in dashcam footage. Everything runs locally on your Windows PC: no uploads, no account, no telemetry. Plates are only searched inside detected vehicles, which keeps false hits on road markings and house walls down. Whatever the automatic pass misses, you can fix by hand in the built-in editor.

![DashCam RoadPrivacy Interface](DashCam_RoadPrivacy_App_Screenshot.png)

## Features

- **License plates:** YOLOv8 finds the vehicles first, then an RT-DETRv2 model looks for plates only inside them. On 1080p and higher footage an additional tile pass helps with small, distant plates.
- **Faces:** OpenCV YuNet, tuned for small faces in street scenes.
- **No gaps at the start:** A few frames are held back, so an object is already blurred in the frames before the detector was sure about it.
- **Manual editor:** Pause, draw a box or oval over a missed object, and it is tracked through the following frames. Corrections on any frame become keyframes; frames in between are interpolated. Tracking also works backwards.
- **Redaction styles:** Gaussian blur, mosaic or solid black.
- **GPU acceleration:** DirectML via ONNX Runtime on NVIDIA, AMD and Intel GPUs. At startup the app checks whether GPU or CPU is faster on your machine and uses that.
- **Export:** Single pass through FFmpeg with NVENC, Quick Sync, AMF or libx264. Optional downscaling (1080p, 720p, 480p, 75 %, 50 %) and compression presets.
- **Trimming:** Fast cut at keyframes without re-encoding.
- **Metadata and audio:** Optionally remove GPS and other metadata, and mute or keep the audio track.
- **Portable:** FFmpeg and all models are included. No Python, no installer.

> Detection is never perfect. Low light, motion blur or unusual plates can be missed. Please check the result before you publish a video.

## Download

### Latest Release: **v2.0.0**

1. Open the [Releases](https://github.com/engstaNET/DashCam_RoadPrivacy/releases) page.
2. Download either `DashCam_RoadPrivacy_v2.0.0_win64.zip` (portable ZIP) or `RoadPrivacy_v2.0.0.exe` (single EXE).
3. Unpack the ZIP to any folder, if you chose the ZIP.
4. Start `RoadPrivacy_v2.0.0.exe`.

**Windows SmartScreen / antivirus:** The EXE is not code-signed, so SmartScreen may show a warning, and some antivirus tools flag single-file EXEs built with PyInstaller. Click **More info** → **Run anyway**. If you want to be sure the file is the one I uploaded, compare its checksum with the values below.

## Checksums (SHA-256)

| File Name | Target Platform | SHA-256 Hash |
| :--- | :--- | :--- |
| **`DashCam_RoadPrivacy_v2.0.0_win64.zip`** | Windows 10/11 x64 (Portable ZIP) | `674044f17867bfbedfd7493b15ecbf4f7f0209ff0992581355a03fe43483cc69` |
| **`RoadPrivacy_v2.0.0.exe`** | Windows 10/11 x64 (Standalone EXE) | `987e06809f268055f4bac4d68431b2e57eb4ba4a03ea686d65e7eb2f8f3bcafc` |

The same values are in [SHA256SUMS.txt](SHA256SUMS.txt). In PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 .\DashCam_RoadPrivacy_v2.0.0_win64.zip
```

## System Requirements

- Windows 10 or 11, 64-bit
- x86-64 CPU, quad-core recommended
- 4 GB RAM, 8 GB recommended
- Optional: DirectX 12 GPU (NVIDIA GeForce, AMD Radeon, Intel Arc/Iris) for faster processing

## Kurz auf Deutsch

DashCam RoadPrivacy macht Kennzeichen und Gesichter in Dashcam-Videos unkenntlich. Alles läuft lokal unter Windows 10/11, ohne Cloud-Upload und ohne Telemetrie. Kennzeichen werden nur innerhalb erkannter Fahrzeuge gesucht, das reduziert Fehlerkennungen. Was die Automatik übersieht, lässt sich im Editor mit Objektverfolgung nachbearbeiten. GPS-Metadaten und Ton können beim Export entfernt werden. Portable EXE, keine Installation. Das Ergebnis bitte vor der Veröffentlichung prüfen.

## License

Free for personal and commercial use under the [Freeware License](LICENSE). See [DISCLAIMER.md](DISCLAIMER.md), [PRIVACY.md](PRIVACY.md) and [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md) for third-party components and model licenses.

Made by Artur F. ([engstaNET](https://github.com/engstaNET))
