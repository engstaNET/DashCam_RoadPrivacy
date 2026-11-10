# Third-Party Licenses

DashCam RoadPrivacy is built on the following open-source libraries and models. Thanks to everyone who maintains them.

## Libraries

| Component | License | Used for |
| :--- | :--- | :--- |
| OpenCV | Apache 2.0 | Image processing, YuNet face detection, object tracking |
| CustomTkinter | MIT | User interface |
| ONNX Runtime (DirectML) | MIT | Running the vehicle and plate models on GPU or CPU |
| FFmpeg / imageio-ffmpeg | LGPL 2.1+ / GPL 2+ | Video encoding, trimming, audio and metadata handling |
| PyTorch, Ultralytics YOLOv8 | AGPL-3.0 / commercial | Exporting the vehicle detection model to ONNX |

## Models

- **YuNet face detector:** OpenCV team, Apache 2.0.
- **YOLOv8n vehicle detector:** Ultralytics, AGPL-3.0.
- **RT-DETRv2 license plate detector:** [Topurrra/rtdetr-license-plate-detection-onnx](https://huggingface.co/Topurrra/rtdetr-license-plate-detection-onnx), Apache 2.0, fine-tuned on the Open Images "Vehicle registration plate" class. See the model card for details on the base model and training data.
- **Haar cascade plate detector (fallback):** from the OpenCV project, under the Intel open-source license included in the file header.
