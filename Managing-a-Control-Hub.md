### Changing the Name
By default, the Control Hub has a name that begins with the phrase "FTC-" and ends with four characters that are assigned at the factory.  In order to comply with game manual rule \<RS01\>, the name should be changed.

You can change the name of a Control Hub using a laptop or Chromebook that is connected to the Hub's Program & Management page.

**Important Note:** Changing the name of a Control Hub changes the name of the Hub's wireless network.  Once the name is changed, you will have to connect your devices (Driver Station and programming laptop/Chromebook) to the new network.

| Changing the Name of a Control Hub|
| ---- |
| 1. Verify that your laptop or Chromebook is connected to the Program & Manage wireless network of the Control Hub.  If you are connected to the network, you should be able to see the _Robot Controller Connection Info_ page when you navigate to address "192.168.43.1:8080":<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/RCConnectionInfoPage.jpg]]</p>If your laptop or Chromebook is not connected and you are unable to access the _Robot Controller Connection Info_ page, then read the instructions in the following [tutorial](Connecting-a-Laptop-to-the-Program-and-Manage-Network) to learn how to connect to the Program & Manage network.<p align="center"><br/>[Connecting a Laptop to the Program & Manage Network](Connecting-a-Laptop-to-the-Program-&-Manage-Network)|
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
It's often helpful when troubleshooting problems with the Control System to download the log file from the Control Hub.  This can be done from the _Manage_ page.

| Downloading the Log File|
| ---- |
| 1. On the _Manage_ page of the Control Hub user interface, press the _Download Logs_ button to download the Robot Controller lot file.<br/><br/><p align="center">[[/images/Managing-a-Control-Hub/downloadLogs.jpg]]|
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





