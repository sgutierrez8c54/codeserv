### Color-Distance Sensor
A sensor is a device that lets the Robot Controller get information about its environment.  In this example, you will use a REV Robotics Color-Distance sensor to display range (distance from an object) info to the driver station.

The Color-Range sensor uses reflected light to determine the distance from the sensor to the target object.  It can be used to measure close distances (up 5” or more) with reasonable accuracy.  Note that at the time this document was most recently edited, the REV Color-Range sensor saturates around 2” (5cm).  This means that for distances less than or equal to 2”, the sensor returns a measured distance equal to 2” or so.

Note that it will take an estimated 15 minutes to complete this task.

| Modifying the Op Mode to Display Distance |
| ---- |
| 1. Verify that your laptop is still connected to the Robot Controller’s Program & Manage Wi-Fi network. |
| 2. Verify that “MyFIRSTOpMode” is opened for editing. If it is not, you can click on the FIRST logo in the upper left hand corner of the browser window on the laptop.  This should take you to the main FTC Blocks Development Tool project screen.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep2ControlHub.jpg]]</p>Click on the “MyFIRSTOpMode” project to open it for editing if it is not already opened. |
| 3. Click on the “Utilities” category on the left-hand side of your browser.  Find and click on the “Telemetry” subcategory.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep3ControlHub.jpg]]</p> |
| 4. Select the “call telemetry.addData” block (the numeric version) and drag it to the spot in your “while” loop block immediately before the “telemetry.update” block.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep4ControlHub.jpg]]</p> |
| 5. Click and highlight the “key” text and change the text so it reads “Distance (cm)”.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep5ControlHub.jpg]]</p> |
| 6. Click and expand the “Sensors” category.  Click on the “REV Color/Range Sensor” subcategory. Click on and select the “call sensorColorRange.getDistance” programming block.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep6ControlHub.jpg]]</p>Note that earlier versions of the FTC Blocks Programming tool refer to the REV Robotics Color-Distance Sensor as the "LynxI2cColorRangeSensor".  Newer versions of the software refer to the device as the "REV Color/Range Sensor". |
| 7. Drag the “call sensorColorRange.getDistance” programming block to the “number” field of the “call telemetry.addData” programming block.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep7ControlHub.jpg]]</p>This will send the measured distance to the target in centimeters back to the Driver Station. |
| 8. Save your op mode and verify that it was saved successfully to the Robot Controller.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep8ControlHub.jpg]]</p> |
| 9. Follow the procedure outlined in the section titled [Running Your Op Mode](https://github.com/ftctechnh/ftc_app/wiki/Running-Your-Op-Mode) to run your updated op mode.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/DistanceSensorStep9ControlHub.jpg]]</p>As you run the op mode, if you move your hand above the color light sensor, you should see the measured distance change on the Driver Station screen.  If the expression “NaN” (not a number) is displayed on the Driver Station, the target is most likely out of range (and the sensor does not detect any reflected light). |

### Touch Sensor

For this example, we assume that the REV Robotics Touch Sensor has been configured as a digital touch sensor in the Robot Controller's active configuration file.  We will use the "isPressed" programming block to determine if the button on the sensor is currently pressed or not.

<p align="center">[[/images/Using-Sensors-(Blocks)/REVTouchSensor.jpg]]<p>

The Expansion Hub digital ports contain two digital pins per port.  When you use a 4-wire JST cable to connect a REV Robotics Touch sensor to an Expansion Hub digital port, the Touch Sensor is wired to the second of the two digital pins within the port.  The first digital pin of the 4-wire cable remains disconnected.

For example, if you connect a Touch Sensor to the “0,1” digital port of the Expansion Hub, the Touch Sensor will be connected to the second pin (labeled “1”) of the port.  The first pin (labeled “0”) will stay disconnected.

Note that it will take an estimated 15 minutes to complete this task.

| Modifying the Op Mode to Display Button (Touch Sensor) State|
| ---- |
| 1. Verify that your laptop is still connected to the Robot Controller’s Programming Mode Wi-Fi network. |
| 2. Verify that “MyFIRSTOpMode” is opened for editing. If it is not, you can click on the FIRST logo in the upper left hand corner of the browser window on the laptop.  This should take you to the main FTC Blocks Development Tool project screen.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep2ControlHub.jpg]]</p>Click on the “MyFIRSTOpMode” project to open it for editing if it is not already opened. |
| 3. Click on the “Logic” category.  Find and click on the “if do else” block.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep3ControlHub.jpg]]</p> |
| 4. Drag the “if do else” block to the position before the “telemetry.update” block.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep4ControlHub.jpg]]</p> |
| 5. Click on the "Sensors" category to expand it (if it isn't already expanded).  Click on the "Touch Sensor" subcategory, then find and select the ".isPressed" block.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep5ControlHub.jpg]]</p> |
| 6. Drag the “isPressed” block to the test condition of the “if do else” programming block.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep6ControlHub.jpg]]</p> |
| 7. Click on the “Utilities” category on the left-hand side of your browser.  Find and click on the “Telemetry” subcategory.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep7ControlHub.jpg]]</p>Select the “call telemetry.addData” block (the text version) and drag it to the “do” clause of the “if do else” block. |
| 8. Change the “key” value to “testTouch” and the “text” value to “is pressed”.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep8ControlHub.jpg]]</p> |
| 9. Insert another "telemetry.addData" block (the text version) to the "else" clause of the "if do else" block.  Change the “key” value to “testTouch” and the “text” value to “is NOT pressed”.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep9ControlHub.jpg]]</p> |
| 10. Save your op mode and verify that it was saved successfully to the Robot Controller.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep10ControlHub.jpg]]</p> |
| 11. Follow the procedure outlined in the section titled [Running Your Op Mode](https://github.com/ftctechnh/ftc_app/wiki/Running-Your-Op-Mode) to run your updated op mode.<br/><br/><p align="center">[[/images/Using-Sensors-(Blocks)/TouchSensorOpModeStep11ControlHub.jpg]]</p>As you run the op mode and push or release the button, the telemetry message on the Driver Station should update to reflect the current state of the digital Touch Sensor. |

