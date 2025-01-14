* Automated-Car-Damage-Detection

Vehicle damage detection uses machine learning algorithms to automatically detect a vehicle's exterior body and assess its injuries and the extent of the damage. Damages to the car are identified not only for insurance purposes but also for repair cost estimation, using computer vision and imaging processing tools.



* Mask R-CNN Model

State-of-the-art object detection networks depend on region proposal algorithms to hypothesize object locations. Introduce a Region Proposal Network (RPN) that shares full-image convolutional features with the detection network, thus enabling nearly cost-free region proposals. An RPN is a fully convolutional network that simultaneously predicts object bounds and objectness scores at each position.

Mask R-CNN, extends Faster R-CNN by adding a branch for predicting an object mask in parallel with the existing branch for bounding box recognition. Mask R-CNN is an instance segmentation model that allows identifying pixel wise location for predefined class. Mask R-CNN is different from classical object detection models like Faster R-CNN where, in addition to identifying the class and its bounding box location, it can also color pixels in the bounding box that correspond to that class.



* How Mask R-CNN works

Extracting Regions of Interest(ROI):

Image is passed to a ConvNet which returns the region of interests based on methods like selective search(RCNN) or RPN(Region Proposal N/W for Faster RCNN).

Then RoI pooling layer on the extracted ROI to make sure all the regions are of the same size.
Classification:

Regions are passed on to a fully connected network which classifies them into different image classes. For instance, scratch(‘damage’) or background(car body without damage).


* Regression:

Bounding box(BB) regression is used to predict the bounding boxes for each identified region for tightening the bounding boxes(getting exact BB defining relative coordinates).
To regress from either region proposals or fixed anchor boxes to nearby bounding boxes of a pre-defined target object classes.
Need to identify the exact pixels location in the bounding box that correspond to the class(damage) to identify the location and quantify the damage accurately.

* Masked Region based CNN(Mask R-CNN):

Identifying pixel-wise delineation for object class of our interest, BB based Object detection (uses ROI align to allow the pixel to pixel preserve of ROIs and prevent information loss), Semantic segmentation - segmenting individual objects at pixel within a scene, irrespective of the shapes (pixel-wise classification) (pixel-wise shading of the class of interest)


Loss at each phase




 
