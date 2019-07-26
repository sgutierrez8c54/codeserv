### Changing the Name
In order to comply with game manual rule \<RS01\>, the name of the Robot Controller's smartphone should be changed.

[This tutorial](Configuring-Your-Android-Devices#renaming-your-smartphones) demonstrates how to rename a smartphone using the Android Settings activity of the phone.

You can also use the FTC app to change the Robot Controller phone's name.

**Important Note:** Once the name of your Robot Controller is changed, you might need to reconnect your devices (Driver Station and programming laptop/Chromebook) to the newly changed network.

| Changing the Name of a Robot Controller|
| ---- |
| 1. On the Robot Controller phone, touch the three dots in the upper right hand corner to display a pop-up menu.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/touchThreeDots.jpg]]</p>|
| 2. Select the _Settings_ menu item from the pop-up menu.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/selectSettings.jpg]]|
| 3. Click on _Robot Controller Name_ on the _ROBOT CONTROLLER SETTINGS_ page.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/clickRobotControllerName.jpg]]|
| 4.Specify the new Robot Controller Name and press _OK_ to accept the changes. <br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/specifyNewRobotControllerName.jpg]]|

### Changing the WiFi Channel
By default the smartphone Robot Controller automatically picks its own operating WiFi channel.  However, it is sometimes necessary to specify the operating channel for the device.

For example, at a large competition an FTA might ask that you switch to a designated channel to avoid wireless interference that is present in the venue.  Similarly, an FTA might ask you to switch to a specific channel because the FTA is monitoring that designated channel for interference or other wireless disruptions.

You can change the operating channel using the Advanced Settings menu on the Robot Controller or Driver Station.

**Important Note:** Not every Android phone supports channel changing through the FTC software.  Refer to rule \<RE06\> in the game manual for a list of _FIRST_-approved phones that support channel changing through the FTC software.

| Changing the WiFi Channel|
| ---- |
| 1. Verify that the Driver Station is connected to your Robot Controller.|
| 2. Tap the three dots in the upper right hand corner of the Driver Station's main screen to display the pop-up menu and select _Settings_ from the menu.|
| 3. Scroll down to the _ROBOT CONTROLLER SETTINGS_ section of the _Settings_ screen and click on the words _Advanced Settings_ to display the _ADVANCED ROBOT CONTROLLER SETTINGS_ activity.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/clickAdvancedSettings.jpg]]|
| 4. Click on the _Change Wifi Channel_ link to display a list of available channels.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/clickChangeWifiChannel.jpg]]|
| 5. Select the desired operating channel.  The phone should display a toast message if the channel change was successful.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/successChangeWifiChannel.jpg]]|
| 6. Use the Android back arrow to return to the main Driver Station screen.  The new operating channel should be displayed in the "Network:" section under the Robot Controller's name <br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/operatingWifiChannel.jpg]]|

### Downloading the Log File
It's often helpful when troubleshooting problems with the Control System to download the log file from the Robot Controller.  This can be done from the _Manage_ page.  Note that the log file name is _robotControllerLog.txt_ by default.

| Downloading the Log File|
| ---- |
| 1. Verify that your laptop or Chromebook is connected to the Program & Manage wireless network of the smartphone Robot Controller.  If you are connected to the network, you should be able to see the _Robot Controller Connection Info_ page when you navigate to address "192.168.49.1:8080":<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/RCConnectionInfoPage.jpg]]</p>If your laptop or Chromebook is not connected and you are unable to access the _Robot Controller Connection Info_ page, then read the instructions in the following [tutorial](Connecting-a-Laptop-to-the-Program-&-Manage-Network) to learn how to connect to the Program & Manage network.<p align="center"><br/>[Connecting a Laptop to the Program & Manage Network](Connecting-a-Laptop-to-the-Program-&-Manage-Network)|
| 2. Click on the _Manage_ link towards the top of the _Robot Controller Connection Info_ page to navigate to the Manage page.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/manageLink.jpg]]|
| 3. Click the _Download Logs_ button to download the Robot Controller log file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/downloadLogs.jpg]]|
| 2. Verify that the Robot Controller log file was downloaded to the Downloads directory of your computer.|
| 3. Use a text editor such as [Notepad++](https://notepad-plus-plus.org/) or Microsoft's WordPad to open and view the contents of the log file.  Note that the Windows app, Notepad, will not properly display the contents of the log file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/notepadplusplus.jpg]]|

### Updating the Expansion Hub Firmware
The Robot Controller connects to a REV Robotics Expansion Hub using a USB connection.  The purpose of the Expansion Hub is to facilitate communication between the Robot Controller and the motors, servos, and sensors of the robot.  Periodically, REV Robotics will release new versions of the firmware which contains fixes and improvements for the Expansion Hub.  The firmware releases are in the form of a binary (".bin") file.

You can use the _Manage_ interface to upload the firmware file to the Robot Controller.  You can then use a Driver Station that is connected to the Robot Controller to initiate the firmware update.  New firmware images can be obtained from the [REV Robotics website](http://www.revrobotics.com/software/).

| Updating the Expansion Hub Firmware|
| ---- |
| 1. On the _Manage_ page of the Robot Controller user interface, press the _Select Firmware_ button to to select the firmware file that you would like to upload.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectFirmwareFile.jpg]]</p>An _Upload_ button should appear after you successfully selected a file.|
| 2. Press the _Upload_ button to upload the firmware file from your computer to the Robot Controller.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadFirmwareFile.jpg]]</p>The words "Firmware upload complete" should appear once the file has been uploaded successfully.|
| 3. Make sure that your Expansion Hub is turned on and powered by a freshly charged 12V battery and that the Robot Controller phone is connected to the Expansion Hub through a USB connection.  Note that the Robot Controller does **not** need to have the Expansion Hub included in an active configuration file in order for the update to work.<br/><br/><p align="center">[[/images/Configuring-Your-Hardware/ConfiguringHardwareStep4.jpg]]</p>|
| 4. On the Driver Station, touch the three dots in the upper right hand corner to display a pop-up menu.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/touchThreeDots.jpg]]</p>|
| 5. Select _Settings_ from the pop-up menu to display the Settings activity.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/touchSettings.jpg]]</p>|
| 6. On the Driver Station, scroll down and select the _Advanced Settings_ item (under the _ROBOT CONTROLLER SETTINGS_ category).<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectAdvancedSettings.jpg]]</p>|
| 7. Select the _Expansion Hub Firmware Update_ item on the _ADVANCED ROBOT CONTROLLER SETTINGS_ activity.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectExpansionHubFirmwareUpdate.jpg]]</p>|
| 8. If a firmware file that is different from the version currently installed on the Expansion Hub was successfully uploaded, the Driver Station should display some information about the current firmware version and the new firmware version. Press the _Update Expansion Hub Firmware_ button to start the update process.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/pressUpdateExpansionHubFirmwareButton.jpg]]</p>|
| 9. A progress bar will display while the firmware is being updated.  Do not power off the Robot Controller/Expansion Hub during this process.  The Driver Station will display a message when the update process is complete.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/dsUpdateComplete.jpg]]</p>|

### Updating the Robot Controller App
It is important to know how to update the Robot Controller app that is installed on your smartphone.  FIRST periodically releases new versions of this app, which contain improvements and fixes, as well as season-specific data and features.  

Note that you can see the Robot Controller app version number through the Robot Controller or Driver Station user interface. Select the _About_ menu option on the Robot Controller or Driver Station and note the App Version number under the _ABOUT ROBOT CONTROLLER_ section.

<p align="center">[[/images/Managing-a-Control-Hub/aboutRobotController.jpg]]</p>

If you use the FTC Blocks Development Tool or the FTC OnBot Java Tool to write your op modes, then the easiest way to update the Robot Controller App is using the Google Play store.  To be able to use the Google Play Store to update your software, you will first need the following items:
1.	A Google e-mail account (available for free from Google).
2.	Access to a wireless network that can connect to the Internet.
3.	Your Android smartphone.

**Important Note:** If you update your Robot Controller, then you should also update your Driver Station software to the same version number.

| Updating the Robot Controller App (Using Google Play)|
| ---- |
| 1. Connect your Android phone to the wireless network that has access to the Internet.|
| 2. Launch the Google Play Store app on the Android device.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/launchGooglePlayStore.jpg]]</p>|
| 3. In the Google Play Store, if you haven’t signed into your Google account yet, follow the onscreen instructions to log into your Google account.|
| 4. In the search window of the Google Play Store type in the words “FTC Robot Controller” to find the appropriate FTC app for your Android device.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/findFTCRobotController.jpg]]</p>|
| 5. Select the  app (“FTC Robot Controller”) that you want to update on your Android phone.|
| 6. If you do not have the most current version of the app, the Google Play Store listing should have a button that reads “UPDATE”.  Press the “UPDATE” button and follow the onscreen instructions to update your app.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/updateFTCRobotController.jpg]]</p>|
| 7. The update process might prompt you to accept request for permissions that are needed in order to run the app on your Android phone.  When prompted, hit the “ACCEPT” button to accept the request and to continue with the update process.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/acceptUpdateFTCRobotController.jpg]]</p>|
| 8. Once the update process is complete, the “UPDATE” button on the screen should change to an “OPEN” button.  You can press the “OPEN” button to launch the new app.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/openFTCRobotController.jpg]]</p>|
| 9. After you have updated the software, you must forget the wireless network that you used to connect to the internet to access the Google Play store.  You do not want to have your Android devices configured to connect to anything other than each other during a competition.<br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/forgetWifiNetwork.jpg]]</p>|

Note that if you are an Android Studio user, then by updating to the newest version of the Android Studio project folder you will update the Robot Controller app when you build the project and install it on your smartphone.  For the Skystone season, you can download the newest version of the project folder [here](https://github.com/FIRST-Tech-Challenge/SkyStone).

### Uploading a Custom Webcam Calibration File
The Robot Controller app has built-in calibration information for a variety of commonly available webcams.  Users can also create their own custom calibration files and then upload these files to a Control Hub. 

A commented example of what the contents of a calibration file should look like can be found in a file called _teamwebcamcalibrations.xml_, which is included with the FTC Android Studio project folder.  For the Skystone season, this example calibration file can be found [here](https://github.com/FIRST-Tech-Challenge/SkyStone/blob/master/TeamCode/src/main/res/xml/teamwebcamcalibrations.xml). 

| Uploading a Custom Webcam Calibration File|
| ---- |
| 1. On the _Manage_ page, click on the _Select Webcam Calibration File..._ button to select the calibration file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectWebcamCalibrationFile.jpg]]</p>An _Upload_ button should appear if a file was successfully selected.|
| 2. Click on the _Upload_ button to upload the selected file.  If the upload was successful, then the _Manage_ page will display a message indicating that the upload has completed.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadWebcamCalibrationFileComplete.jpg]]</p>|
