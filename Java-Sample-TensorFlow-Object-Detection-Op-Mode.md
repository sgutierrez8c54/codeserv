### Creating the Op Mode
You can use the sample "ConceptTensorFlowObjectDetection" as a template to create your own Java Op Mode that uses TensorFlow technology to determine the relative location of the Gold Mineral.  

If you are an OnBot Java user, you can select "ConceptTensorFlowObjectDetection" as the sample op mode from the dropdown list on the New File dialog box.  Select the "Preserve Sample" option and press "OK" to create the new Op Mode.  

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/onbotConceptTensorFlow.png" width="400"><br/>Create an Op Mode with ConceptTensorFlowObjectDetection as its template.<p> 

If you are an Android Studio user, you can copy the sample Op Mode from the external.samples folder to your TeamCode project. This tutorial will focus on using OnBot Java to create your Op Mode.

Your new Op Mode should appear in the editing pane of the OnBot Java screen.  Note that a complete copy of the sample Java Op Mode can be viewed [here.](https://raw.githubusercontent.com/ftctechnh/ftc_app/master/FtcRobotController/src/main/java/org/firstinspires/ftc/robotcontroller/external/samples/ConceptTensorFlowObjectDetection.java)

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/onbotMyExample.png" width="800"><br/>Your newly created Op Mode should be available for editing through OnBot Java.<p> 

### Initializing the System
Let's take a look at the initial statements in the Op Mode.  Before you start, you must first make sure you have a valid Vuforia developer license key to initialize the Vuforia software.  You can obtain a key for free from [https://developer.vuforia.com/license-manager](https://developer.vuforia.com/license-manager).  Once you obtain your key, replace the VUFORIA_KEY static String with the actual license key so the Vuforia software will be able to initialize properly.

```
private static final String VUFORIA_KEY = " -- YOUR NEW VUFORIA KEY GOES HERE  --- ";
```
Also, by default the Op Mode is disabled.  Comment out the "@Disabled" annotation to enable your newly created Op Mode.

```
@TeleOp(name = "Concept: TensorFlow Object Detection", group = "Concept")
//@Disabled
public class ConceptTensorFlowObjectDetection extends LinearOpMode {
```

Since TensorFlow will receive image data from Vuforia, the Op Mode attempts to create and initialize a VuforiaLocalizer object by calling the function called "initVuforia()":

```
        // The TFObjectDetector uses the camera frames from the VuforiaLocalizer, so we create that
        // first.
        initVuforia();
```

Note that you can initialize both the Vuforia and the TensorFlow libraries in the same op mode.  This is useful, for example, if you would like to use the TensorFlow library to determine the arrangement of the minerals and then use the Vuforia library to help autonomously navigate on the game field to remove the Gold Mineral from its starting position.

In this example op mode, however, the initVuforia() function does not load any trackable image targets. 

```
    /**
     * Initialize the Vuforia localization engine.
     */
    private void initVuforia() {
        /*
         * Configure Vuforia by creating a Parameter object, and passing it to the Vuforia engine.
         */
        VuforiaLocalizer.Parameters parameters = new VuforiaLocalizer.Parameters();

        parameters.vuforiaLicenseKey = VUFORIA_KEY;
        parameters.cameraDirection = CameraDirection.BACK;

        //  Instantiate the Vuforia engine
        vuforia = ClassFactory.getInstance().createVuforia(parameters);

        // Loading trackables is not necessary for the Tensor Flow Object Detection engine.
    }
```

After the Vuforia localizer is initialized, if the device is able to run TensorFlow, the Op Mode creates and initializes a TensorFlow Object Detector by calling the function initTfod().

```
        if (ClassFactory.getInstance().canCreateTFObjectDetector()) {
            initTfod();
        } else {
            telemetry.addData("Sorry!", "This device is not compatible with TFOD");
        }
```
Note that when the Op Mode creates a new TensorFlow Object Detector, it specifies an ID for a camera monitor view so that the user can see on the Robot Controller activity an image with TensorFlow data (including bounding boxes for detected objects) overlayed.  

If you do not want a camera monitor view, then you can call the TFObjectDetector.Parameters() constructor without any arguments.

```
        // Leave argument list empty if you want to disable the camera monitor view.
        TFObjectDetector.Parameters tfodParameters = new TFObjectDetector.Parameters();
```

Note that by default, when you create a new TensorFlow object detector, an _object tracker_ is used, in addition to the TensorFlow interpreter, to keep track of the locations of detected objects.   The object tracker _interpolates_ object recognitions so that results are smoother than they would be if the system were to solely rely on the TensorFlow interpreter.

If you want to turn off the object tracker, then you can set the useObjectTracker variable of the tfodParameters object to false before you create the TensorFlow object detector.

```
        // set useObjectTracker to false to disable object tracker.
        tfodParameters.useObjectTracker = false;
```

Also note that the by default, the minimum detection confidence level is set to 40%.  This means that the TensorFlow library needs to have a confidence level of 40% or higher in order to consider an object as being detected in its field of view.  You can adjust this parameter to a higher value if you would like the system to be more selective in identifying an object.

```
        // set the minimumConfidence to a higher percentage to be more selective when identifying objects.
        tfodParameters.minimumConfidence = 0.75;

```

After the TensorFlow Object Detector is created it loads the TensorFlow model data for the Gold and Silver Minerals.

```
    /**
     * Initialize the Tensor Flow Object Detection engine.
     */
    private void initTfod() {
        int tfodMonitorViewId = hardwareMap.appContext.getResources().getIdentifier(
            "tfodMonitorViewId", "id", hardwareMap.appContext.getPackageName());
        TFObjectDetector.Parameters tfodParameters = new TFObjectDetector.Parameters(tfodMonitorViewId);
        tfod = ClassFactory.getInstance().createTFObjectDetector(tfodParameters, vuforia);
        tfod.loadModelFromAsset(TFOD_MODEL_ASSET, LABEL_GOLD_MINERAL, LABEL_SILVER_MINERAL);
    }
```

If a camera monitor view is enabled for the TensorFlow library, then the confidence level for a detected target will be displayed near the bounding box of the identified object (when the object tracker is enabled).  For example, a value of "0.92" indicates a 92% confidence that the object has been identified correctly.

When an object is identified by the TensorFlow library, the Op Mode can read the "Left", "Right", "Top" and "Bottom" values associated with the detected object.  These values correspond to the location of the left, right, top and bottom boundaries of the detection box for that object.  These values are in pixel coordinates of the image from the camera.

The origin of the coordinate system is in the upper left-hand corner of the image.  The horizontal (x) coordinate value increases as you move from the left to the right of the image.  The vertical (y) coordinate value increases as you move from the top to the bottom of the image.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/landscapeCoordinate.png" height="400"><br/>The origin of the image coordinate system is located in upper left hand corner.<p>

In the landscape image above, the approximate coordinate values for the Left, Top, Right, and Bottom boundaries are 955, 411, 1234, and 694 respectively (pixel coordinates).  The width and height for the landscape image above is 1280 and 720 respectively.

### Iterating and Processing List of Recognized Objects
After the Op Mode waits for (and receives) a start command from the Driver Station, if the Op Mode is still active, the Op Mode will activate the TensorFlow library.  Note that in this example, the Op Mode does not activate the Vuforia tracking feature, it only activates the TensorFlow object detection.  If you want to incorporate Vuforia image detection and tracking you will also need to activate (and later deactivate when you are done) the Vuforia tracking feature.

```
            /** Activate Tensor Flow Object Detection. */
            if (tfod != null) {
                tfod.activate();
            }
```

The Op Mode will then check with TensorFlow to see how many objects it recognizes in its field of view. The Op Mode adds a telemetry message to indicate on the Driver Station how many objects were detected in the camera's field of view.

```
                    // getUpdatedRecognitions() will return null if no new information is available since
                    // the last time that call was made.
                    List<Recognition> updatedRecognitions = tfod.getUpdatedRecognitions();
                    if (updatedRecognitions != null) {
                      telemetry.addData("# Object Detected", updatedRecognitions.size());

```

If the number of detected objects equals three (i.e., if three Minerals are in the camera's field of view) then the Op Mode will loop through the list of recognized objects and look at the label for each recognized object.  If an object has a label that indicates it's a Gold Mineral, then the "Left" coordinate value of its bounding box  will be assigned to the variable "goldMineralX".  Similarly, if the other two objects in the list have labels that indicate that they are Silver Minerals, then their Left coordinate values will be assigned to the variables "silverMineral1X" and "silverMineral2X".

```
                      if (updatedRecognitions.size() == 3) {
                        int goldMineralX = -1;
                        int silverMineral1X = -1;
                        int silverMineral2X = -1;
                        for (Recognition recognition : updatedRecognitions) {
                          if (recognition.getLabel().equals(LABEL_GOLD_MINERAL)) {
                            goldMineralX = (int) recognition.getLeft();
                          } else if (silverMineral1X == -1) {
                            silverMineral1X = (int) recognition.getLeft();
                          } else {
                            silverMineral2X = (int) recognition.getLeft();
                          }
                        }
```

The Op Mode then checks to see if it has three valid X (or Left) coordinate values for the Gold and two Silver Minerals.  If it does have three valid values, then it compares the Gold X coordinate value with the other two values:

* If the Gold X value is the lowest (i.e., leftmost) of the three, then the Gold Mineral is in the "Left" position.
* If the Gold X value is the highest (i.e., rightmost) of the three, then the Gold Mineral is in the "Right" position.
* Otherwise, the Gold Mineral is in the "Center" position.

```
                        if (goldMineralX != -1 && silverMineral1X != -1 && silverMineral2X != -1) {
                          if (goldMineralX < silverMineral1X && goldMineralX < silverMineral2X) {
                            telemetry.addData("Gold Mineral Position", "Left");
                          } else if (goldMineralX > silverMineral1X && goldMineralX > silverMineral2X) {
                            telemetry.addData("Gold Mineral Position", "Right");
                          } else {
                            telemetry.addData("Gold Mineral Position", "Center");
                          }
                        }

```

### Important Note Regarding Image Orientation
The system interprets images based on the phone's orientation (Portrait or Landscape) at the time that the TensorFlow object detector was created and initialized. In our example, if you create the TensorFlow object detector while the phone is in Portrait mode, then the images will be processed in Portrait mode.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodPortrait.png" width="300"> <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodDSPortrait.png" width="300"><br/>If you create the detector in Portrait mode, then the images are processed in Portrait mode.<p>

The "Left" and "Right" values of an object's bounding box correspond to horizontal coordinate values, while the "Top" and "Bottom" values of an object's bounding box correspond to vertical coordinate values.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodBoundaries.png" width="300"><br/>The "Left" and "Top" boundaries of a detection box when the image is in Portrait mode.<p>

If you wanted to use your smartphone in Landscape mode, then make sure that your phone is in Landscape mode when the TensorFlow object detector is created.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodLandscape.png" height="300"><br/>The system can also be run in Landscape mode.<p>

If the phone is in Landscape mode when the object detector is initialized, then the images will be interpreted in Landscape mode.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/tfodBoundariesLandscape.png" height="300"><br/>The "Left" and "Top" boundaries of a detection box when the image is in Landscape mode.<p>

Note that Android devices can be locked into Portrait Mode so that the screen image will not rotate even if the phone is held in a Landscape orientation.  If your phone is locked in Portrait Mode, then the TensorFlow object detector will interpret all images as Portrait images.  If you would like to use the phone in Landscape mode, then you need to make sure your phone is set to "Auto-rotate" mode.  In Auto-rotate mode, if the phone is held in a Landscape orientation, then the screen will auto rotate to display the contents in Landscape form.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/tensorflow/images/autorotate.png" width="300"><br/>Auto-rotate must be enabled in order to operate in Landscape mode.<p>

### Deactivating TensorFlow
When the example Op Mode is no longer active (i.e., when the user has pressed the stop button on the Driver Station) the Op Mode will attempt to deactivate the TensorFlow library before it's done.  It's important to deactivate the library to free up system resources.

```
        if (tfod != null) {
            tfod.shutdown();
        }
```