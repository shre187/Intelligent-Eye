# INTELLIGENT EYE
OBJECT DETECTION

01.	ABSTRACT
02.	INTRODUCTION
03.	METHODOLOGY
04.	LIMITATIONS
05.	OUTPUT
06.	CONCLUSION

ABSTARCT

Abstract:

•	We present YOLO, a new approach to object detection. Prior work on object detection repurposes classifiers to perform detection. Instead, we frame object detection as a regression problem to spatially separated bounding boxes and associated class probabilities. 
•	A single neural network predicts bounding boxes and class probabilities directly from full images in one evaluation. Since the whole detection pipeline is a single network, it can be optimized end-to-end directly on detection performance. 
•	Our unified architecture is extremely fast. Our base YOLO model processes images in real-time at 45 frames per second. A smaller version of the network, Fast YOLO, processes an astounding 155 frames per second while still achieving double the mAP of other real-time detectors.
•	 Compared to state-of-the-art detection systems, YOLO makes more localization errors but is less likely to predict false positives on background. Finally, YOLO learns very general representations of objects.
•	 It outperforms other detection methods, including DPM and R-CNN, when generalizing from natural images to other domains like artwork.

INTRODUCTION

Object detection is a phenomenon in computer vision that involves the detection of various objects in digital images or videos. Some of the objects detected include people, cars, chairs, stones, buildings, and animals.
This phenomenon seeks to answer two basic questions:
1.	What is the object? This question seeks to identify the object in a specific image.
2.	Where is it? This question seeks to establish the exact location of the object within the image.
Object detection consists of various approaches such as fast R-CNN, Retina-Net, and Single-Shot MultiBox Detector (SSD). Although these approaches have solved the challenges of data limitation and modelling in object detection, they are not able to detect objects in a single algorithm run. YOLO algorithm has gained popularity because of its superior performance over the aforementioned object detection techniques.

METGHODOLOGY

01.	Data collection
02.	Data filtering
03.	Data labelling
04.	Cross validation
05.	Training data
06.	Train sample data
07.	Evaluation
08.	Conclusion

LIMITATIONS

Although YOLO does seem to be the best algorithm to use if you have an object detection problem to solve, it comes with several limitations.
YOLO struggles to detect and segregate small objects in images that appear in groups, as each grid is constrained to detect only a single object. Small objects that naturally come in groups, such as a line of ants, are therefore hard for YOLO to detect and localize.
YOLO is also characterized by lower accuracy when compared to much slower object detection algorithms like Fast RCNN.


HOW IT WORKS?

•	Residual Blocks
•	Bounding Box regression
•	Intersection Over Union (IOU)


•	Residual Blocks
o	 First, the image is divided into various grids. Each grid has a dimension of S x S. The following image shows how an input image is divided into grids.

 



o	In the image above, there are many grid cells of equal dimension. Every grid cell will detect objects that appear within them. For example, if an object center appears within a certain grid cell, then this cell will be responsible for detecting it.

•	Bounding box regression
o	A bounding box is an outline that highlights an object in an image.
o	Every bounding box in the image consists of the following attributes:
	Width (bw)
	Height (bh)
	Class (for example, person, car, traffic light, etc.)- This is represented by the letter c.
	Bounding box center (bx,by)

•	The following image shows an example of a bounding box. The bounding box has been represented by a yellow outline.

 
 

o	YOLO uses a single bounding box regression to predict the height, width, center, and class of objects. In the image above, represents the probability of an object appearing in the bounding box.

Intersection over union (IOU)
•	Intersection over union (IOU) is a phenomenon in object detection that describes how boxes overlap. YOLO uses IOU to provide an output box that surrounds the objects perfectly.
•	Each grid cell is responsible for predicting the bounding boxes and their confidence scores. The IOU is equal to 1 if the predicted bounding box is the same as the real box. This mechanism eliminates bounding boxes that are not equal to the real box.
•	The following image provides a simple example of how IOU works.

 


•	In the image above, there are two bounding boxes, one in green and the other one in blue. The blue box is the predicted box while the green box is the real box. YOLO ensures that the two bounding boxes are equal.


Combination of the three techniques

•	The following image shows how the three techniques are applied to produce the final detection results.
 






	First, the image is divided into grid cells. Each grid cell forecasts B bounding boxes and provides their confidence scores. The cells predict the class probabilities to establish the class of each object.
For example, we can notice at least three classes of objects: a car, a dog, and a bicycle. All the predictions are made simultaneously using a single convolutional neural network.
Intersection over union ensures that the predicted bounding boxes are equal to the real boxes of the objects. This phenomenon eliminates unnecessary bounding boxes that do not meet the characteristics of the objects (like height and width). The final detection will consist of unique bounding boxes that fit the objects perfectly.
For example, the car is surrounded by the pink bounding box while the bicycle is surrounded by the yellow bounding box. The dog has been highlighted using the blue bounding box.
  		
CONCLUSION

This technique provides improved detection results compared to other object detection techniques such as Fast R-CNN and Retina-N
