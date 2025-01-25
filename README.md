# License Plate Detection using YOLOv8

This repository contains a project for detecting vehicle license plates using the YOLOv8 (You Only Look Once version 8) object detection model. The project leverages two datasets—one Iranian and one international—to achieve robust detection performance. The datasets are annotated and processed specifically for YOLOv8 using Roboflow.

---

## Features

- **YOLOv8 Integration**: Utilizes the latest YOLOv8 model for high-speed and accurate object detection.
- **Dual Datasets**: Combines data from Iranian and international datasets to ensure versatility:
  - [IranianCarsNumberPlate in Kaggle](https://www.kaggle.com/datasets/skhalili/iraniancarnumberplate)
  - [Car License Plate Detection in Kaggle](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection)
- **Data Annotation**: Bounding boxes are annotated using Roboflow for seamless integration with YOLOv8.
- **Performance Metrics**: The model achieves:
  - Precision: **0.8625**
  - Recall: **0.9079**
  - F1-score: **0.8846**

---

## Requirements

To run this project, you need the following Python libraries:

- **ultralytics**: For YOLOv8.
- **matplotlib**: For data visualization.
- **cv2**: For image processing.
- **random**: For random operations.
- **os**: For handling file paths and directories.

You can install the dependencies using:
```bash
pip install ultralytics matplotlib opencv-python
```

---

## Datasets

1. **IranianCarsNumberPlate**:
   - A dataset focused on Iranian license plates.
   - Available on [Kaggle](https://www.kaggle.com/datasets/skhalili/iraniancarnumberplate).

2. **Car License Plate Detection**:
   - A diverse dataset of car license plates from various regions.
   - Available on [Kaggle](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection).

---

## Data Annotation with Roboflow

- The datasets were annotated for bounding boxes using Roboflow.
- Roboflow simplifies the conversion of XML annotations to YOLOv8-compatible formats.
- Exported data includes:
  - Train images and labels
  - Validation images and labels

---

## How to Use

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/license-plate-detection-yolov8.git
   cd license-plate-detection-yolov8
   ```

2. **Prepare the Datasets**:
   - Download the datasets from Kaggle.
   - Use Roboflow to annotate and export the data in YOLOv8 format.

3. **Training the Model**:
   - Edit the `dataset.yaml` file to point to your dataset paths:
     ```yaml
     train: path/to/train/images
     val: path/to/val/images
     nc: 1
     names: ['license_plate']
     ```
   - Train the model using the following script:
     ```python
     from ultralytics import YOLO

     model = YOLO("yolov8s.pt")  # Load pre-trained YOLOv8 model
     model.train(data='path/to/dataset.yaml', epochs=50, imgsz=640)
     ```

4. **Inference**:
   - Use the trained model to detect license plates in new images:
     ```python
     results = model("path/to/image.jpg")
     results.show()  # Display detection results
     ```

---

## Performance

- The trained model achieves the following metrics:
  - **Precision**: 0.8625
  - **Recall**: 0.9079
  - **F1-score**: 0.8846

These metrics demonstrate the model’s ability to accurately detect license plates in diverse conditions.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Special thanks to the creators of the [IranianCarsNumberPlate](https://www.kaggle.com/datasets/skhalili/iraniancarnumberplate) and [Car License Plate Detection](https://www.kaggle.com/datasets/andrewmvd/car-plate-detection) datasets.
- Thanks to the Roboflow team for their powerful annotation tools.

Feel free to contribute to this project by submitting issues or pull requests!

