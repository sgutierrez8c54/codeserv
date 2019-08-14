### Changing the Name
By default, the Control Hub has a name that begins with the phrase "FTC-" and ends with four characters that are assigned at the factory.  In order to comply with game manual rule \<RS01\>, the name should be changed.

You can change the name of a Control Hub using a laptop or Chromebook that is connected to the Hub's Program & Management page.

**Important Note:** Changing the name of a Control Hub changes the name of the Hub's wireless network.  Once the name is changed, you will have to connect your devices (Driver Station and programming laptop/Chromebook) to the new network.

| Changing the Name of a Control Hub|
| ---- |
| 1. Verify that your laptop or Chromebook is connected to the Program & Manage wireless network of the Control Hub.  If you are connected to the network, you should be able to see the _Robot Controller Connection Info_ page when you navigate to address "192.168.43.1:8080":<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/RCConnectionInfoPage.jpg]]</p>If your laptop or Chromebook is not connected and you are unable to access the _Robot Controller Connection Info_ page, then read the instructions in the following [tutorial](Connecting-a-Laptop-to-the-Program-&-Manage-Network) to learn how to connect to the Program & Manage network.<p align="center"><br/>[Connecting a Laptop to the Program & Manage Network](Connecting-a-Laptop-to-the-Program-&-Manage-Network)|
| 2. Click on the _Manage_ link towards the top of the _Robot Controller Connection Info_ page to navigate to the Manage page.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/manageLink.jpg]]|
| 3. Change the name in the "Robot Controller Name" field and click on the _Change Name_ button to change the Control Hub's name.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/changeName.jpg]]|
| 4. After you press the _Change Name_ button, a dialog box will appear, indicating that the name has been changed and that you will need to connect to the new wireless network and refresh the current page.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/changeNameWarning.jpg]]|

### Changing the Password
By default, the Control Hub has its password set to "password" at the factory.  It is a good idea to change the password from its default value before you begin using your Control Hub.

You can change the password of a Control Hub using a laptop or Chromebook that is connected to the Hub's Program & Management page.

**Important Note:** Commit your new password to memory or store it in a secure location so you will not forget it.  You will need this password to manage and operate your Control Hub.  Also note, once the password has been changed, you will have to reconnect your devices (Driver Station and programming laptop/Chromebook) to the network using the new password.

| Changing the Password of a Control Hub|
| ---- |
| 1. On the _Manage_ page of the Control Hub user interface, find specify your new password and then confirm this new password in the _Access Point Password_ section of the page.  Press the _Change Password_ to change the password.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/changePassword.jpg]]|
| 2. After you press the _Change Password_ button, a dialog box will appear, indicating that the password has been changed and that you will need to reconnect to the wireless network using the new password.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/changePasswordWarning.jpg]]|

### Resetting a Control Hub
If you forget the network name or password for a Control Hub, you can reset the Hub's name and password back to their factory default values.  

**Important Note:** Resetting a Control Hub will restore its default network name and password.  However, existing configuration files and op modes should not be affected by the reset. This includes op modes that were created using the Blocks, OnBot Java and Android Studio tools. 

| Resetting a Control Hub |
| ---- |
| 1. Turn off the power to your Control Hub for 5 seconds. |
| 2. Press and hold the button on the Control Hub (see image below).<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/controlHubButton.jpg]]|
| 3. Power on the Control Hub while continuing to hold the button.  Monitor the LED while the Control Hub is rebooting.  Eventually, the LED will switch from being solid blue, to a multi-color blink pattern.<br/><br/>When the reset has started, the LED should blink purple, yellow, blue, and then red.  This pattern should occur five times in rapid succession.<br/><br/>Once the multi-colored blink pattern is complete, you can release the button.  The Control Hub's network name and password should be restored to their factory values.  Note that the reboot and reset process should take approximately 30 seconds to complete.|

### Changing the WiFi Channel
The Control Hub acts as a wireless access point for the Driver Station and for the programming laptop or Chromebook.  By default the Control Hub automatically picks an operating WiFi channel.  However, it is sometimes necessary to specify the operating channel for the Hub.

For example, at a large competition an FTA might ask that you switch to a designated channel to avoid wireless interference that is present in the venue.  Similarly, an FTA might ask you to switch to a specific channel because the FTA is monitoring that designated channel for interference or other wireless disruptions.

You can select the operating channel for the Control Hub from the _Manage_ page.

| Changing the WiFi Channel|
| ---- |
| 1. On the _Manage_ page of the Control Hub user interface, use the drop down selector to select the desired operating channel.  Note that the Control Hub supports both the 2.4 GHz and 5 GHz bands.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/selectChannel.jpg]]|
| 2. Press the _Change Channel_ button to change to the new channel.  Note that when the channel change occurs, the Driver Station might momentarily disconnect from the Control Hub.  It should eventually, however, reconnect to Control Hub's wireless network.|
| 3. Verify on the Driver Station that the Control Hub is operating on the desired WiFi channel.  The operating channel should be displayed under the network name in the "Network:" section of the main Driver Station screen.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/dsOperatingChannel.jpg]]|

### Downloading the Log File
It's often helpful when troubleshooting problems with the Control System to download the log file from the Control Hub.  This can be done from the _Manage_ page.  Note that the log file name is _robotControllerLog.txt_ by default.

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

Note that if you are an Android Studio user, then by updating to the newest version of the Android Studio project folder you will update the Robot Controller app when you build the project and install it on your Control Hub.

**Important Note:** If you update your Robot Controller, then you should also update your Driver Station software to the same version number.

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

### Disabling/Enabling the Internal Android Controller

Each Control Hub has its own built-in Android Controller.  It is possible to enable or disable the Control Hub’s built-in Android controller:

* When the built-in Android controller is disabled, the Control Hub acts like an Expansion Hub.  When the internal controller is disabled, a user can connect an external Android phone to the USB mini (not Type C) port of the Control Hub and use the device just like an Expansion Hub.
* When the internal Android controller is enabled, the user cannot use the device as an Expansion Hub.  Instead, when the built-in Android controller is enabled, the user must use the device as a Control Hub, and the Driver Station must pair to the Control Hub's built-in Android controller.

**IMPORTANT NOTE:** Disabling/Enabling the internal Android controller requires advanced Android programming skills.  The user must be familiar with using the Android Debug Bridge (ADB) utility.  FIRST does not recommend that users disable their Control Hub's internal Android controller - doing so could cause unforeseen negative effects.  FIRST provides this information for educational purposes only.

**IMPORTANT NOTE:** Unfortunately, the Control Hub is only approved for use during the SKYSTONE season in limited regions. If a team disables a Control Hub's internal Android controller, the team still will most likely not be allowed to use the Control Hub as an Expansion Hub outside of these limited test regions.

#### Disabling the Built-In Android Controller
Follow these steps to disable the built-in Android controller of a Control Hub:
1.	Connect a USB micro cable from your development laptop to the port labeled "USB C" on the Control Hub.  
2.	From a terminal on your laptop, use adb to shell into the Android controller.
3.	Type the command “getprop persist.ftcandroid.db.disable” to view the current value of the system property called “persist.ftcandroid.db.disable”.  By default this value should be false.
4.	Use the command “setprop persist.ftcandroid.db.disable true” to change this system property.
5.	Type the command “getprop persist.ftcandroid.db.disable” to verify that the property was changed to true.
6.	Type the command “reboot” to reboot your Android controller.  Upon reboot, the Android controller should detect that the “persist.ftcandroid.db.disable” propery is now set to true.  It will disable the connection between the Android device and the built in Expansion Hub of the Control Hub.  

You should now be able to use your Control Hub as an Expansion Hub.  Note that if you do this you might need to change the serial address of the Control Hub's internal Expansion Hub.  By default, the serial number for a Control Hub is set to 1.  If you re-enable the internal Android Controller, you should set the serial number back to 1.

**IMPORTANT NOTE:** A _disabled_ internal Android controller is not really disabled. Instead, the Robot Controller app is not active and a user can connect to the Expansion Hub portion of the Control Hub using the USB **Mini** port on the back of the Control Hub.  When you disable your internal Android controller, you still might see the Wi-Fi network established by the internal Android controller (which is still powered on whenever the Control Hub is turned on).

The following screen shot shows the commands that can be issued to disable the internal Android controller of a Control Hub.

<p align="center">[[/images/Managing-a-Control-Hub/disablingInternalAndroidController.jpg]]<p>

#### Enabling the Built-In Android Controller
Follow these steps to enable the built-in Android controller of a Control Hub:
1.	Connect a USB micro cable from your development laptop to the port labeled "USB C" on the Control Hub.  
2.	From a terminal on your laptop, use adb to shell into the Android controller.
3.	Type the command “getprop persist.ftcandroid.db.disable” to view the current value of the system property called “persist.ftcandroid.db.disable”.  If the value is true, then you must change the value back to false to re-enable the internal Android Controller.
4.	Use the command “setprop persist.ftcandroid.db.disable false” to change this system property.
5.	Type the command “getprop persist.ftcandroid.db.disable” to verify that the property was changed to false.
6.	Type the command “reboot” to reboot your Android controller.  Upon reboot, the Android controller should detect that the “persist.ftcandroid.db.disable” propery is now set to false.  It will enable the connection between the Android device and the built in Expansion Hub of the Control Hub.  It will also launch the Robot Controller app on the built-in Android controller and operate as a Control Hub.

Note that if you had previously changed the serial address of the internal Expansion Hub to a value other than 1, then you should change the address back to 1 once the internal Android controller has been re-enabled.  After the address change, you will need to reboot your machine and recreate your configuration file for your Control Hub.

The following screen shot shows the commands that can be issued to re-enable the internal Android controller of a Control Hub.

<p align="center">[[/images/Managing-a-Control-Hub/enablingInternalAndroidController.jpg]]<p>


 

