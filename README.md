# YOLO for Autonomous Vehicle Detection on BDD100K dataset

## Introduction
This repository hosts the evaluation results of the YOLOv7 and YOLOv8 models for real-time object detection in autonomous vehicles, utilizing the Berkeley Deep Drive BDD100K dataset.

## Results Summary
Our study focuses on the performance of YOLO models on embedded devices, aiming to balance detection accuracy and computational efficiency crucial for real-time applications in autonomous vehicles.

### Key Findings:
- **YOLOv8s** offers the best performance in terms of precision and mAP values across various resolutions but at a higher computational cost.
- **YOLOv7-tiny** shows commendable efficiency, making it suitable for embedded devices with limited computational resources.
- **YOLOv8n** provides a balanced performance, particularly excelling in higher FPS on embedded devices when optimized with TensorRT.

## Performance Metrics
All experiments used the PyTorch framework on an NVIDIA GeForce RTX A5000 GPU with 32GB of RAM and an Intel(R) Core(TM) i9-10900X processor.

### Table I: Computational Cost (
| Model        | FLOPs   | #Params | FPS (CPU w/o TRT) | FPS (GPU w/ TRT) |
|--------------|---------|---------|-------------------|------------------|
| YOLOv8s      | 17.06G  | 11.12M  | 31                | 554              |
| YOLOv8n      | 4.85G   | 3M      | 59                | 947              |
| YOLOv7-tiny  | 7.81G   | 6M      | 41                | 919              |

### Table II: Comparative Analysis of YOLO Models at Various Resolutions on Our Setting 1
| Size   | Model       | Precision | Recall | mAPval50 | mAPval50:95 | FLOPs  |
|--------|-------------|-----------|--------|----------|-------------|--------|
| 640x384| YOLOv8s     | 86.3%     | 72.7%  | 81.9%    | 54%         | 17.06G |
| 640x384| YOLOv8n     | 84.9%     | 69.1%  | 78.5%    | 50.7%       | 4.85G  |
| 640x384| YOLOv7-tiny | 84.3%     | 69.5%  | 79.4%    | 48.4%       | 7.81G  |

### Table III: Comparative Analysis of YOLO Models at Various Resolutions on Our Setting 2
| Size   | Model       | Precision | Recall | mAPval50 | mAPval50:95 | FLOPs  |
|--------|-------------|-----------|--------|----------|-------------|--------|
| 640x384| YOLOv8s     | 75%       | 58.7%  | 65.8%    | 35.9%       | 17.07G |
| 640x384| YOLOv8n     | 69.9%     | 52.3%  | 58%      | 30.5%       | 4.85G  |
| 640x384| YOLOv7-tiny | 71.2%     | 53%    | 59.4%    | 29.2%       | 7.83G  |

### Performance Evaluation on Embedded Devices
Below is a table showcasing the frames per second (FPS) achieved by various YOLO models at the resolution tested (640x384), with batch size set to 1. This metric is crucial for understanding the real-time object detection capabilities of each model on NVIDIA Xavier and TX2 platforms.

### Table: FPS Performance on Embedded Devices at 640x384 Resolution (Batch Size = 1)
| Model       | FPS (Xavier) | FPS (TX2) |
|-------------|--------------|-----------|
| YOLOv8n     | 184 ±40      | 83 ±0     |
| YOLOv8s     | 101 ±10      | 38 ±0     |
| YOLOv7-tiny | 172 ±30      | 76 ±0     |

## Conclusion
The YOLO models, particularly YOLOv8 variants, demonstrate significant potential for use in autonomous vehicle technologies, providing a strong balance between speed and accuracy. Further optimization on computational efficiency and model robustness is suggested to enhance real-time applicability.
