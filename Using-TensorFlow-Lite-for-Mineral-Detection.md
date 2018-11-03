### What is a TensorFlow Lite?
[TensorFlow Lite](https://www.tensorflow.org/lite/) is a lightweight version of Google's [TensorFlow](https://www.tensorflow.org/) machine learning technology that is designed to run on mobile devices such as an Android smartphone.  A _trained TensorFlow model_ was developed to recognize the Gold and Silver Mineral game pieces from the 2018-2019 FIRST Tech Challenge game.  This TensorFlow model has been integrated into the FIRST Tech Challenge Control System software and can be used to identify and track these game pieces during a match.

### Important Note on Phone Compatibility
Unfortunately, the TensorFlow Lite technology will not run on the older ZTE Speed phones that are approved for use in the FIRST Tech Challenge competition.  Teams who would like to use the TensorFlow Lite technology for objection detection, will have to use a different type of approved phone (such as the Motorola Moto G4 Play).  The TensorFlow Lite technology requires Android 6.0 (Marshmallow) or higher.

Note that if you are a Blocks programmer and you are using an older Android device that is not running Marshmallow or higher, then the TensorFlow Object Detection category of Blocks will automatically not be available in the Blocks design palette.

### Sample Op Modes
The FIRST Tech Challenge software contains sample Blocks and Java op modes that demonstrate how to use the TensorFlow technology to detect the relative location of the Gold Mineral (i.e., the yellow cube) with respect to the two Silver Minerals (i.e., the white wiffle-style balls).

Click on the following links to learn more about these sample Op Modes.

* [Blocks Tensor Flow Object Detection Example](https://github.com/ftctechnh/ftc_app/wiki/Blocks-Sample-TensorFlow-Object-Detection-Op-Mode)
* [Java Tensor Flow Object Detection Example](https://github.com/ftctechnh/ftc_app/wiki/Java-Sample-TensorFlow-Object-Detection-Op-Mode)

 