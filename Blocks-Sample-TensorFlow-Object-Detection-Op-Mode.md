### Creating the Op Mode
You can use the sample "ConceptTensorFlowObjectDetection" as a template to create your own Blocks op mode that uses the TensorFlow technology to determine the relative location of the Gold Mineral.  Start by creating a new op mode and select "ConceptTensorFlowObjectDetection" as the sample op mode from the dropdown list on the Create New Op Mode dialog box.  Press "OK" to create the new Op Mode.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksConceptTensorFlow.png" width="400"><br/>Create an Op Mode with ConceptTensorFlowObjectDetection as its template.<p> 

Your new Op Mode should appear in the editing pane of the Blocks Development Tool screen.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksMyExample.png" width="300"><br/>Your newly created Op Mode will have the ConceptTensorFlowObjectDetection Blocks included.<p> 

### Initializing the System
Let's take a look at the initial blocks in the Op Mode.  The first block in the op mode (excluding the comment block) initializes the Vuforia library on the Android Robot Controller.  This is needed because the TensorFlow Lite library will receive image data from the Vuforia library.  In this example, the enableCameraMonitoring option is set to false.  This means that there will not be a Vuforia preview window on the Robot Controller screen.

Note that you can initialize both the Vuforia and the TensorFlow libraries in the same op mode.  This is useful, for example, if you would like to use the TensorFlow library to determine the arrangement of the minerals and then use the Vuforia library to help autonomously navigate on the game field to remove the Gold Mineral from its starting position.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksInit.png" width="500"><br/>Initialize the Vuforia and TensorFlow libraries.<p>

The Op Mode then initializes the TensorFlow library and it enables a camera monitoring window so that the user can see on the Robot Controller activity an image with TensorFlow data (including bounding boxes for detected objects) overlayed.

Note that in this example the ObjectTracker parameter is set to true for this block, so an _object tracker_ will be used, in addition to the TensorFlow interpreter, to keep track of the locations of detected objects.   The object tracker _interpolates_ object recognitions so that results are smoother than they would be if the system were to solely rely on the TensorFlow interpreter.

Also note that the Confidence level is set to 40%.  This means that the TensorFlow library needs to have a confidence level of 40% or higher in order to consider an object as being detected in its field of view.  You can adjust this parameter to a higher value if you would like the system to be more selective in identifying an object.

If a camera monitor window is enabled for the TensorFlow library, then the confidence level for a detected target will be displayed near the bounding box of the identified object (when the object tracker is enabled).  For example, a value of "0.92" indicates a 92% confidence that the object has been identified correctly.

When an object is identified by the TensorFlow library, the Op Mode can read the "Left", "Right", "Top" and "Bottom" values associated with the detected object.  These values correspond to the location of the left, right, top and bottom boundaries of the detection box for that object.  These values are in pixel coordinates of the image from the camera.

The origin of the coordinate system is in the upper left-hand corner of the image.  The horizontal (x) coordinate value increases as you move from the left to the right of the image.  The vertical (y) coordinate value increases as you move from the top to the bottom of the image.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/landscapeCoordinate.png" height="400"><br/>The origin of the image coordinate system is located in upper left hand corner.<p>

In the landscape image above, the approximate coordinate values for the Left, Top, Right, and Bottom boundaries are 955, 411, 1234, and 694 respectively (pixel coordinates).  The width and height for the landscape image above is 1280 and 720 respectively.

### Iterating and Processing List of Recognized Objects
After the Op Mode waits for (and receives) a start command from the Driver Station, if the Op Mode is still active, the Op Mode will activate the TensorFlow object detector.  Note that in this example, the Op Mode does not activate the Vuforia tracking feature, it only activates TensorFlow object detection.  If you want to incorporate Vuforia image detection and tracking you will also need to activate (and later deactivate when you are done) the Vuforia tracking feature.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksTensorFlowActivate.png" width="400"><br/>Activate TensorFlow.<p>

The Op Mode will then check with the object detector to see how many objects it recognizes in its field of view. In the screenshot below, the variable "recognitions" is set to a list of objects that were recognized using the TensorFlow technology.  The Op Mode adds a telemetry message to indicate on the Driver Station how many objects were detected in the camera's field of view.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksGetRecognitions.png" width="500"><br/>Get a list of recognized objects from TensorFlow.<p>

If the number of detected objects equals three (i.e., if three Minerals are in the camera's field of view) then the Op Mode will loop through the list of recognized objects and look at the label for each recognized object.  If an object has a label that indicates it's a Gold Mineral, then the "Left" coordinate value of its bounding box will be assigned to the variable "goldMineralX".  Similarly, if the other two objects in the list have labels that indicate that they are Silver Minerals, then their Left coordinate values will be assigned to the variables "silverMineral1X" and "silverMineral2X".

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksFindingLeftValues.png" width="600"><br/>Keep track of the Left coordinate values of the detected objects.<p>

The Op Mode then checks to see if it has three valid X (or Left) coordinate values for the Gold and two Silver Minerals.  If it does have three valid values, then it compares the Gold X coordinate value with the other two values:

* If the Gold X value is the lowest (i.e., leftmost) of the three, then the Gold Mineral is in the "Left" position.
* If the Gold X value is the highest (i.e., rightmost) of the three, then the Gold Mineral is in the "Right" position.
* Otherwise, the Gold Mineral is in the "Center" position.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksCompareLeftValues.png" width="600"><br/>Compare the Left or X coordinate values to determine Gold's relative location.<p>

### Important Note Regarding Image Orientation
The system interprets images based on the phone's orientation (Portrait or Landscape) at the time that the TensorFlow object detector was created and initialized. In our example, if you execute the TensorFlowObjectDetection.initialize block while the phone is in Portrait mode, then the images will be processed in Portrait mode.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodPortrait.png" width="300"> <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodDSPortrait.png" width="300"><br/>If you initialize the detector in Portrait mode, then the images are processed in Portrait mode.<p>

The "Left" and "Right" values of an object's bounding box correspond to horizontal coordinate values, while the "Top" and "Bottom" values of an object's bounding box correspond to vertical coordinate values.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodBoundaries.png" width="300"><br/>The "Left" and "Top" boundaries of a detection box when the image is in Portrait mode.<p>

If you want to use your smartphone in Landscape mode, then make sure that your phone is in Landscape mode when the TensorFlow object detector is initialized.  Landscape mode is preferable for this season's game since it offers a wider field of view so that all three minerals can fit in a single image.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodLandscape.png" height="300"><br/>The system can also be run in Landscape mode.<p>

If the phone is in Landscape mode when the object detector is initialized, then the images will be interpreted in Landscape mode.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodBoundariesLandscape.png" height="300"><br/>The "Left" and "Top" boundaries of a detection box when the image is in Landscape mode.<p>

Note that Android devices can be locked into Portrait Mode so that the screen image will not rotate even if the phone is held in a Landscape orientation.  If your phone is locked in Portrait Mode, then the TensorFlow object detector will interpret all images as Portrait images.  If you would like to use the phone in Landscape mode, then you need to make sure your phone is set to "Auto-rotate" mode.  In Auto-rotate mode, if the phone is held in a Landscape orientation, then the screen will auto rotate to display the contents in Landscape form.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/autorotate.png" width="300"><br/>Auto-rotate must be enabled in order to operate in Landscape mode.<p>

### Deactivating TensorFlow
When the example Op Mode is no longer active (i.e., when the user has pressed the stop button on the Driver Station) the Op Mode will attempt to deactivate the TensorFlow library before it's done.  It's important to deactivate the library to free up system resources.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/blocksTensorFlowDeactivate.png" width="400"><br/>Deactivate TensorFlow.<p>

