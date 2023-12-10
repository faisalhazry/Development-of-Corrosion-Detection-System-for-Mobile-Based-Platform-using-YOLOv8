# Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8
Keywords— AI-based corrosion detection; custom YOLOv8 dataset; early detection; mobile-based platform;


## I. INTRODUCTION
Corrosion poses immense risks to structures. Current visual inspection methods are time-consuming and subjective. Introducing AI-based corrosion detection using YOLOv8 promises precise, real-time identification on mobile platforms, ensuring safer infrastructure with reduced manual inspections and improved maintenance across industries reliant on metal structures.


## II. METHODOLOGY
### A. Archtecture of the system
This AI-driven corrosion detection system, utilizing a custom YOLOv8 dataset, operates via a mobile interface. Its architecture boasts a web front-end enabling video upload or real-time webcam detection. Powered by Flask, it manages HTTP interactions, file handling, and delivers seamless result viewing for enhanced user experience.

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/d4b2d18a-042a-43c3-9fac-02295c05ad1e)

### B. Instance Segmentation detection
For this project, the use of instance segmentation for corrosion detection was proposed. Unlike object detection, instance segmentation not only detects the presence of objects in an image, but also identifies the boundaries of each object instance. This approach can be particularly useful for detecting and analyzing individual instances of corrosion within an image.

1. Object Detection: Firstly, it runs object detection to find all bounding boxes for every object in an image
2. Semantic Segmentation: After finding all the rectangles (bounding boxes), it uses a semantic segmentation model inside every rectangle
3. Instance Segmentation: Masking identifying the boundaries of objects

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/e98b5c36-d2a2-467f-8176-553b5e6574a2)

### C. Dataset Generation
Collected 705 corroded surface images, annotated via Roboflow for instance segmentation. Augmentation doubled dataset to 1398 images through flips and resizing. Split into training (1200), validation (141), and testing (57) sets. Crucial steps: collection, annotation, augmentation, and division for robust ML model development in corrosion detection.

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/207ec61b-e124-412f-bf10-d61a0f460164)
![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/97e41d36-bba9-4a07-828e-f47a4f6957ec)

### D. Model Architecture Selection Training

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/50a78bc4-cbdc-4fe8-9bc3-360bdee3476a)

### E. Model Training Environment

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/40eb2a13-868f-4eae-b5d5-30e3badf4d5d)

### F. Evaluation
#### i. IOU Intersection over Union
In simple terms, IoU measures the degree of overlap between the predicted bounding box and the ground truth bounding box, expressed as a percentage. A diagrammatic representation of IoU is shown in the accompanying figure[6],
![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/520a973e-50e8-49d4-bead-142e48e7ee0f)

#### ii. Precision & Recall
![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/3f01c374-89ce-47ee-b799-4a36c7545f6f)

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/28e47a6d-afa7-4976-be82-c28e2524e92e)

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/b51d6f0a-86df-42e2-8ac5-fd182da7b7c5)


## III. RESULT AND DISCUSSION
### A. Precision & Recall curve
#### i. Precision & Recall curve
![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/547b3f3f-4f9f-4522-a6cf-1b29b9cb1b39)

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/97efe037-d334-4f54-9a5d-dedbe85894d2)

### B. Model Deployment
#### i. Flask Framework
Flask is a Python web framework that enables developers to create web applications by integrating various web technologies, such as HTML, CSS, and Python files[9].

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/73613200-0f1a-4778-9471-87ca26313c9b)

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/e9da77a4-ccf7-4596-ac4f-4ae1bb9bf076)

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/e8d1c60f-c2f0-4c8e-b02f-abd96b83759f)

### C. Performance benchmark
The provided table showcases the performance metrics of different models (YoloV8x, YoloV8n, YoloV5x, and YoloV5n) in terms of precision and recall at a confidence level of 0.5. Additionally, it presents the video rendering duration for each model, measured using both the Command Line Interface (CLI) and Python. YoloV8x achieves a precision of 0.71 and a recall of 0.62, with a video rendering duration of 100 seconds (14.5 average FPS) using CLI and 1205 seconds (1.12 average FPS) using Python. YoloV8n demonstrates a precision of 0.72 and a recall of 0.59, with a video rendering duration of 64 seconds (21.0 average FPS) using CLI and 144 seconds (9.35 average FPS) using Python. YoloV5x exhibits a precision of 0.69 and a recall of 0.64, with a video rendering duration of 1082 seconds (1.24 average FPS). Finally, YoloV5n showcases a precision of 0.69 and a recall of 0.66, with a video rendering duration of 160 seconds (8.43 average FPS).

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/b22ed2df-ba16-44ec-b7b3-5e733494dca8)


## IV. CONCLUSION
In conclusion, a mobile-based AI-driven corrosion detection system was successfully developed using YOLOv8. This system provides users with the capability to upload videos, access webcams, and store video detections on a local server. Comparative analysis between YOLOv8 and YOLOv5 revealed that YOLOv8 outperformed YOLOv5 in terms of precision, exhibiting improvements of 2.90% for the extra-large size and 4.35% for the nano size. Moreover, YOLOv8 demonstrated significant speed enhancements, achieving an impressive 89.16% improvement for the extra-large size and 94.09% improvement for the nano size. This AI-based corrosion detection system makes valuable contributions to the field by offering an effective solution for early detection on mobile platforms and IoT devices.

![WhatsApp Image 2023-12-10 at 15 08 50_f1218cb1](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/b55ef25b-38c0-43f3-9061-586ad6fcd46e)

![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/d34623df-0378-4d65-930f-47a52a09dfdc)
![image](https://github.com/faisalhazry/Development-of-Corrosion-Detection-System-for-Mobile-Based-Platform-using-YOLOv8/assets/121289405/a4c6ae3b-8062-4878-97a6-5c692341f927)

























