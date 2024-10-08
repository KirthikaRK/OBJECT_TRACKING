Object tracking is a crucial task in computer vision with applications ranging from video surveillance and autonomous driving to robotics and human-computer interaction. This project focuses on implementing object tracking system that operates in two distinct stages: object detection and object tracking. 

In the first stage, the object detection is carried out using the YOLOv8 model, which is pre-trained on the COCO dataset. YOLO (You Only Look Once) is a real-time object detection algorithm known for its speed and accuracy. YOLOv8, the latest iteration of the YOLO series, builds on the success of its predecessors with improved detection performance and efficiency. It divides the input image into a grid and predicts bounding boxes, class probabilities, and objectness scores for each grid cell. By applying non-max suppression, YOLOv8 eliminates overlapping bounding boxes, ensuring only the most relevant detections are retained.

Once the objects are detected, the output from YOLOv8 is fed into the second stage of the pipeline, which is responsible for object tracking. This is achieved using the DEEPsort technique, a highly effective method for multi-object tracking. DEEPsort enhances the original SORT (Simple Online and Realtime Tracking) algorithm by incorporating deep learning-based appearance descriptors. The DEEPsort algorithm works by associating detected objects across consecutive frames using a combination of motion information (Kalman filter) and appearance features (convolutional neural network). It assigns a unique ID to each object, enabling consistent tracking throughout the video sequence, even when objects temporarily disappear from the scene or occlude each other.

This two-stage process leverages the strengths of both YOLOv8 for accurate object detection and DEEPsort for reliable object tracking, resulting in a robust and efficient system capable of handling complex tracking scenarios in real-time.

The data used is a video stream input. Here we try to identify i.e detect all the human(people) present in the frame and track each person till they are visible in the frame.

BEFORE :
![image](https://github.com/user-attachments/assets/85422a0e-e58d-4739-8879-f3d43f6f00aa)


AFTER : The output is actually an video stream, where each person is identitfied, and an track Id is associated to each of them in order to track them till they exist in the frame. The below is snapshot of one such frame. It can also be noted that the model still need some more tuning and working to improve its accuracy.
![image](https://github.com/user-attachments/assets/363883f1-08f3-40a3-b59e-46d8e3bcca7e)


