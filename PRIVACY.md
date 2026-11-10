# Privacy

DashCam RoadPrivacy processes your videos on your own computer.

- Decoding, detection, blurring, encoding and metadata removal all happen locally. Nothing is uploaded.
- The app has no telemetry, analytics or update check.
- No internet connection is needed to process videos. The release package already contains all models. Only if a model file is missing does the app try to download it from its original source (GitHub or Hugging Face). No video data is sent in that case either.
- Your footage, location data and timestamps stay on your machine.

## Checking your download

SHA-256 checksums for every release are listed on the [Releases](https://github.com/engstaNET/DashCam_RoadPrivacy/releases) page and in [SHA256SUMS.txt](SHA256SUMS.txt), so you can check that the file has not been changed.
