# codealpha_task-3
Code Explanation
Model and Class Loading:

The YOLO model's weights (yolov3.weights) and configuration (yolov3.cfg) files are loaded using OpenCV's cv2.dnn.readNet method. These files can be downloaded from the official YOLO GitHub repository.
The coco.names file contains the names of the 80 object classes that the model can detect.
Video Capture:

The cv2.VideoCapture function is used to open the video file (video.mp4). You can also use 0 as an argument to access the webcam.
Frame Processing:

For each frame, we preprocess it using cv2.dnn.blobFromImage, which converts the frame into a blob (a standard format for feeding into the neural network).
The blob is then passed through the YOLO model using net.forward, which returns the output predictions from the model.
Detection Parsing:

We iterate over the outputs and extract the class IDs, confidences, and bounding boxes for the detected objects. Only detections with a confidence above a certain threshold (0.5 in this case) are considered.
Non-Maximum Suppression (NMS):

NMS is applied to remove overlapping boxes, retaining only the most confident detections.
Drawing Boxes and Labels:

For each detection, a bounding box and label are drawn on the frame using cv2.rectangle and cv2.putText.
Display and Exit:

The processed frame is displayed in a window. The loop continues until the video ends or the user presses the 'q' key.
Output
When the code runs, it will display a window showing the video with detected objects highlighted by bounding boxes and labels. Each detected object will have its class name and confidence score displayed above the box.
