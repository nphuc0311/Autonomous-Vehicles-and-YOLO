# YOLO for Autonomous Vehicle Detection on BDD100K dataset

## Introduction
This repository hosts the evaluation results of the YOLOv7 and YOLOv8 models for real-time object detection in autonomous vehicles, utilizing the Berkeley Deep Drive BDD100K dataset.

### Key Findings:
- **YOLOv8s** offers the best performance in terms of precision and mAP values across various resolutions but at a higher computational cost.
- **YOLOv7-tiny** shows commendable efficiency, making it suitable for embedded devices with limited computational resources.
- **YOLOv8n** provides a balanced performance, particularly excelling in higher FPS on embedded devices when optimized with TensorRT.

## Training Pipeline
- **Setting 1:** We group the objects car, truck, bus, train into a single class vehicle.
- **Setting 2:** we group the objects (car, truck, bus, train) into vehicle, (traffic light, traffic sign) into traffic control signals, (motorcycle, bicycle) into bike, and (pedestrian, rider, other person) into person.

## Performance Metrics
All experiments used the PyTorch framework on an NVIDIA GeForce RTX A5000 GPU with 32GB of RAM and an Intel(R) Core(TM) i9-10900X processor.

### Computational Cost
| Model        | FLOPs   | #Params | CPU | GPU <br><sup>(w/o TRT) |
|--------------|---------|---------|-----|-----------------------|
| YOLOv8s      | 17.06G  | 11.12M  | 31  | 229                   |
| YOLOv8n      | 4.85G   | 3M      | 59  | 234                   |
| YOLOv7-tiny  | 7.81G   | 6M      | 41  | 249                   |

### Comparative Analysis of YOLO Models on Setting 1
| Size   | Model       | Precision | Recall | mAP<sup>val<br>50 | mAP<sup>val<br>50:95 | FLOPs  |
|--------|-------------|-----------|--------|-------------------|----------------------|--------|
| 640x384| YOLOv8s     | 86.3%     | 72.7%  | 81.9%             | 54%                  | 17.06G |
| 640x384| YOLOv8n     | 84.9%     | 69.1%  | 78.5%             | 50.7%                | 4.85G  |
| 640x384| YOLOv7-tiny | 84.3%     | 69.5%  | 79.4%             | 48.4%                | 7.81G  |

### Comparative Analysis of YOLO Models on Setting 2
| Size   | Model       | Precision | Recall | mAP<sup>val<br>50 | mAP<sup>val<br>50:95 | FLOPs  |
|--------|-------------|-----------|--------|-------------------|----------------------|--------|
| 640x384| YOLOv8s     | 75%       | 58.7%  | 65.8%             | 35.9%                | 17.07G |
| 640x384| YOLOv8n     | 69.9%     | 52.3%  | 58%               | 30.5%                | 4.85G  |
| 640x384| YOLOv7-tiny | 71.2%     | 53%    | 59.4%             | 29.2%                | 7.83G  |

## Performance Evaluation on Embedded Devices
Below is a table showcasing the frames per second (FPS) achieved by various YOLO models at the resolution tested (640x384), with batch size set to 1. This metric is crucial for understanding the real-time object detection capabilities of each model on NVIDIA Xavier and TX2 platforms.

### FPS Performance on Embedded Devices
| Model       | FPS (Xavier) | FPS (TX2) |
|-------------|--------------|-----------|
| YOLOv8n     | 184          | 83        |
| YOLOv8s     | 101          | 38        |
| YOLOv7-tiny | 172          | 76        |

## Conclusion
The YOLO models, particularly YOLOv8 variants, demonstrate significant potential for use in autonomous vehicle technologies, providing a strong balance between speed and accuracy. Further optimization on computational efficiency and model robustness is suggested to enhance real-time applicability.

For more detailed information and analysis on the performance of these models, you can read more in our full paper [here](https://drive.google.com/file/d/16zPZg5q4vZSM3FgP32VoWCn3tY6w3gcN/view?usp=sharing).
