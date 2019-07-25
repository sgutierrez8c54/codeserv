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
| 6.Use the Android back arrow to return to the main Driver Station screen.  The new operating channel should be displayed in the "Network:" section under the Robot Controller's name <br/><br/><p align="center">[[/images/Managing-a-Smartphone-Robot-Controller/operatingWifiChannel.jpg]]|

### Downloading the Log File
It's often helpful when troubleshooting problems with the Control System to download the log file from the Control Hub.  This can be done from the _Manage_ page.

| Downloading the Log File|
| ---- |
| 1. On the _Manage_ page of the Control Hub user interface, press the _Download Logs_ button to download the Robot Controller log file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/downloadLogs.jpg]]|
| 2. Verify that the Robot Controller log file was downloaded to the Downloads directory of your computer.|
| 3. Use a text editor such as [Notepad++](https://notepad-plus-plus.org/) or Microsoft's WordPad to open and view the contents of the log file.  Note that the Windows app, Notepad, will not properly display the contents of the log file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/notepadplusplus.jpg]]|

### Updating the Expansion Hub Firmware
The Control Hub has its own built-in REV Robotics Expansion Hub.  The purpose of the Expansion Hub board is to facilitate communication between the Control Hub's Android controller and the motors, servos, and sensors of the robot.  Periodically, REV Robotics will release new versions of the firmware which contains fixes and improvements for the Expansion Hub.  The firmware releases are in the form of a binary (".bin") file.

You can use the _Manage_ interface to upload the firmware file to the Control Hub.  You can then use a Driver Station that is connected to the Control Hub to initiate the firmware update.  New firmware images can be obtained from the [REV Robotics website](http://www.revrobotics.com/software/).

| Updating the Expansion Hub Firmware|
| ---- |
| 1. On the _Manage_ page of the Control Hub user interface, press the _Select Firmware_ button to to select the firmware file that you would like to upload.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectFirmwareFile.jpg]]</p>An _Upload_ button should appear after you successfully selected a file.|
| 2. Press the _Upload_ button to upload the firmware file from your computer to the Control Hub.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadFirmwareFile.jpg]]</p>The words "Firmware upload complete" should appear once the file has been uploaded successfully.|
| 3. On the Driver Station, touch the three dots in the upper right hand corner to display a pop-up menu.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/touchThreeDots.jpg]]</p>|
| 4. Select _Settings_ from the pop-up menu to display the Settings activity.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/touchSettings.jpg]]</p>|
| 5. On the Driver Station, scroll down and select the _Advanced Settings_ item (under the _ROBOT CONTROLLER SETTINGS_ category).<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectAdvancedSettings.jpg]]</p>|
| 6. Select the _Expansion Hub Firmware Update_ item on the _ADVANCED ROBOT CONTROLLER SETTINGS_ activity.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectExpansionHubFirmwareUpdate.jpg]]</p>|
| 7. If a firmware file that is different from the version currently installed on the Expansion Hub was successfully uploaded, the Driver Station should display some information about the current firmware version and the new firmware version. Press the _Update Expansion Hub Firmware_ button to start the update process.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/pressUpdateExpansionHubFirmwareButton.jpg]]</p>|
| 8. A progress bar will display while the firmware is being updated.  Do not power off the Control Hub/Expansion Hub during this process.  The Driver Station will display a message when the update process is complete.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/dsUpdateComplete.jpg]]</p>|

### Updating the Robot Controller App
It is important to know how to update the Robot Controller app that is installed on a Control Hub.  FIRST periodically releases new versions of this app, which contain improvements and fixes, as well as season-specific data and features.  

Note that you can see the Robot Controller app version number through the Driver Station user interface. Select the _About_ menu option on the Driver Station and note the App Version number under the _ABOUT ROBOT CONTROLLER_ section.

<p align="center">[[/images/Managing-a-Control-Hub/aboutRobotController.jpg]]</p>

The Control Hub lacks a touch screen and Google Play support.  Unfortunately, teams that use the Control Hub cannot update the Control Hub's Robot Controller app directly through the Google Play store.

Instead, Control Hub users can download the Robot Controller app from the appropriate FIRST-Tech-Challenge repository (for the Skystone season, the app can be found [here](https://github.com/FIRST-Tech-Challenge/SkyStone/tree/master/doc/apk)) and use the _Manage_ page to complete the update.

Note that if you are an Android Studio user, then by updating to the newest version of the Android Studio project folder you will update the Robot Controller app when you build the project and install it on your Control Hub

| Updating the Robot Controller App|
| ---- |
| 1. Go to the current season's GitHub repository and look in the "doc/apk" subdirectory to download the appropriate APK file.  For the Skystone season, the APK files can be found [here](https://github.com/FIRST-Tech-Challenge/SkyStone/tree/master/doc/apk).|
| 2. Click on the _FtcRobotController-release.apk_ link in the repository to access the Robot Controller file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/apkFolderOnRepo.jpg]]</p>|
| 3. Click on the _Download_ button to download the Robot Controller app as an APK file to your computer.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/downloadRobotControllerAPK.jpg]]</p>|
| 4. On the _Manage_ page, click on the _Select App_ button to select the Robot Controller app that you would like to upload to the Control Hub.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectRobotControllerAPK.jpg]]</p>An _Update_ button should appear if an APK file was successfully selected.|
| 5. Click on the _Update_ button to begin the update process.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadRobotControllerPleaseWait.jpg]]</p>|
| 6. During the update process, if the Control Hub detects that the digital signature of the APK that is being installed is different from the digital signature of the APK that is already installed, the Hub might prompt you to ask if it is OK to uninstall the current app and replace it with the new one.<br/><br/>This difference in digital signatures can occur, for example, if the previous version of the app was built and installed using Android Studio, but the newer app was downloaded from the GitHub repository.<br/><br/>Press _OK_ to uninstall the old app and continue with the update process.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadRobotControllerWarning.jpg]]</p>|
| 7. If the update process had to uninstall the previous version of the Robot Controller app, the network name and password for the Control Hub will be reset back to their factory values.  If this happens, then you will need to reconnect your computer to the Control Hub using the factory default values.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadRobotControllerUninstalling.jpg]]</p>|
| 9. When the update process is complete and you have successfully reconnected your computer to the Control Hub's network, you should see an "installed successfully" message on the _Manage_ web page.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadRobotControllerInstalledSuccessfully.jpg]]</p>|

### Uploading a Custom Webcam Calibration File
The Robot Controller app has built-in calibration information for a variety of commonly available webcams.  Users can also create their own custom calibration files and then upload these files to a Control Hub. 

A commented example of what the contents of a calibration file should look like can be found in a file called _teamwebcamcalibrations.xml_, which is included with the FTC Android Studio project folder.  For the Skystone season, this example calibration file can be found [here](https://github.com/FIRST-Tech-Challenge/SkyStone/blob/master/TeamCode/src/main/res/xml/teamwebcamcalibrations.xml). 

| Uploading a Custom Webcam Calibration File|
| ---- |
| 1. On the _Manage_ page, click on the _Select Webcam Calibration File..._ button to select the calibration file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectWebcamCalibrationFile.jpg]]</p>An _Upload_ button should appear if a file was successfully selected.|
| 2. Click on the _Upload_ button to upload the selected file.  If the upload was successful, then the _Manage_ page will display a message indicating that the upload has completed.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/uploadWebcamCalibrationFileComplete.jpg]]</p>|

### Updating the Control Hub OS
REV Robotics periodically releases new versions of the Control Hub operating system (OS). These new versions incorporate fixes, improvements, and new features.   

Note that you can see the Control Hub OS version number through the Driver Station user interface. Select the _About_ menu option on the Driver Station and note the Operating System Version number under the _ABOUT ROBOT CONTROLLER_ section.

<p align="center">[[/images/Managing-a-Control-Hub/aboutRobotControllerOSVersion.jpg]]</p>

Control Hub users can download a new Control Hub OS file from the REV Robotics website and use the _Manage_ page to complete the update of the OS.

| Updating the Control Hub OS|
| ---- |
| 1. Download the new Control Hub OS update file from the [REV Robotics website](http://www.revrobotics.com/software/).|
| 2. On the _Manage_ page, click on the _Select Update File..._ button to select the OS update file that you would like to upload.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectOSUpdateFile.jpg]]</p>An _Update & Reboot_ button should appear if an update file was successfully selected.|
| 3. Click on the _Update & Reboot_ button to start the update process.  Please wait while the OS file gets uploaded to the Control Hub.  Note that since the file is relatively large, it might take several minutes before the upload is complete. Do not turn off the Control Hub while the process is underway.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/osUpdatePleaseWait.jpg]]</p>|
| 4. If the upload was successful, the _Manage_ page will display a message indicating that the device is being rebooted and the update is being installed.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/osUpdateVerificationSucceeded.jpg]]</p>|
| 5. When the OS update has completed, the Control Hub LED should switch from blue, back to its normal blink pattern (green, then it will blink blue once to indicate the Hub's serial address number, then the pattern repeats itself).  Reconnect your computer to the Control Hub network and verify that the update was a success. <br/><br/><p align="center">[[/images/Managing-a-Control-Hub/osUpdateSuccess.jpg]]</p>Note that you can also check in the About page (through the Driver Station app) to verify the updated version number of the Control Hub OS.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/aboutRobotControllerNewOSVersion.jpg]]</p>|

### Connecting to the Control Hub Using Wireless ADB 
Advanced users who use Android Studio to build and install the Robot Controller app onto their Control Hub should be familiar with the Android Debug Bridge (adb) utility.  adb is included with the Android development platform tools.  It can be used to communicate with an Android device such as the Control Hub.

Traditionally, programmers use a hard-wired USB connection to communicate using adb to their Android device.  adb also supports a mode where commands are sent back and forth through a wireless connection.

The Control Hub is configured so that it automatically will support an adb wireless connection request on port 5555.

| Connecting to the Control Hub Using Wireless ADB|
| ---- |
| 1. Verify that your laptop is connected to the Program & Manage wireless network of the Control Hub.  If you are connected to the network, you should be able to see the _Robot Controller Connection Info_ page when you navigate to address "192.168.43.1:8080":<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/RCConnectionInfoPage.jpg]]</p>If your laptop is not connected and you are unable to access the _Robot Controller Connection Info_ page, then read the instructions in the following [tutorial](Connecting-a-Laptop-to-the-Program-&-Manage-Network) to learn how to connect to the Program & Manage network.<p align="center"><br/>[Connecting a Laptop to the Program & Manage Network](Connecting-a-Laptop-to-the-Program-&-Manage-Network)|
| 2. Verify that the PATH environment variable for your Windows computer includes the path to the adb.exe executable file.  The [Android Developer website](https://developer.android.com/studio/command-line/adb) tells you where in your Android SDK installation you can find the adb.exe file.  This [post](https://helpdeskgeek.com/windows-10/add-windows-path-environment-variable/) from [HelpDeskGeek.com](https://helpdeskgeek.com/windows-10/add-windows-path-environment-variable/) shows how to add a directory to your Windows PATH environment variable.|
| 3. Open a Windows Command Prompt and type in "adb.exe connect 192.168.43.1:5555".  This should connect your adb server to the Control Hub over the wireless connection.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/adbConnected.jpg]]</p>|


