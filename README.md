# YOLO for Autonomous Vehicle Detection

## Introduction
This repository hosts the evaluation results of the YOLOv7 and YOLOv8 models for real-time object detection in autonomous vehicles, utilizing the Berkeley Deep Drive BDD100K dataset.

## Results Summary
Our study focuses on the performance of YOLO models on embedded devices, aiming to balance detection accuracy and computational efficiency crucial for real-time applications in autonomous vehicles.

### Key Findings:
- **YOLOv8s** offers the best performance in terms of precision and mAP values across various resolutions but at a higher computational cost.
- **YOLOv7-tiny** shows commendable efficiency, making it suitable for embedded devices with limited computational resources.
- **YOLOv8n** provides a balanced performance, particularly excelling in higher FPS on embedded devices when optimized with TensorRT.

### Performance Metrics:
- **Setting 1** (Single Class: Vehicle):
  - YOLOv8s achieves the highest mAP50 of 81.9% at 640x384 resolution.
  - YOLOv8n and YOLOv7-tiny perform well in lower resolutions, suitable for real-time processing needs.
- **Setting 2** (Multiple Classes: Vehicle, Traffic Control Signals, Bike, Person):
  - YOLOv8s consistently outperforms in precision and mAP values but requires more computational power.
  - The performance across models decreases as the resolution decreases, reflecting the trade-offs between accuracy and computational demand.

### Visualization of Results:
- Daytime and nighttime detection scenarios show that YOLOv8s can reliably detect small and distant objects under various traffic conditions.
- Comparative analysis under different lighting conditions emphasizes the models' robustness in practical autonomous driving applications.

## Conclusion
The YOLO models, particularly YOLOv8 variants, demonstrate significant potential for use in autonomous vehicle technologies, providing a strong balance between speed and accuracy. Further optimization on computational efficiency and model robustness is suggested to enhance real-time applicability.

## Citation
Please cite our work if you find it useful in your research or application.

```yaml
@article{YOLOAutonomous2023,
  title={YOLO for Autonomous Vehicle Detection},
  author={Authors},
  journal={Conference on Computer Vision and Pattern Recognition},
  year={2023}
}
