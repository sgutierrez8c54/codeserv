### What Needs to Be Configured for My Control System?
#### Control Hub Users 

Teams who are using a Control Hub with the integrated Robot Controller will only need to configure a single smartphone for use as a Driver Station.  The process is as follows:
* Rename the smartphone to "\<TEAM NUMBER\>-DS" (where \<TEAM NUMBER\> is replaced by your team number).
* Install the Driver Station app onto the Driver Station phone.
* Put your phone into Airplane Mode (with the WiFi radio still on).
* Pair (i.e., wirelessly connect) the Driver Station to the Control Hub.

<p align="center">[[/images/Configuring-Your-Android-Devices/ControlHubAndPhone.jpg]]<p>

**IMPORTANT NOTE:** Eventually the Control Hub will need be renamed so that its name complies with Game Manual rule 
\<RS01\>, but for now we will use the Control Hub with its default name.  You can learn how to manage a Control Hub (and modify its name, password, etc.) in [this tutorial](Managing-a-Control-Hub).  

#### Users with Two Android Smartphones
Teams who have two smartphones and are not using a Control Hub will need to configure one smartphone for use as a Robot Controller and a second smartphone for use as a Driver Station.  The process is as follows,
* Rename one smartphone to "\<TEAM NUMBER\>-RC" (replace \<TEAM NUMBER\> with your team number).
* Install the Robot Controller app onto the Robot Controller phone.
* Rename a second smartphone to "\<TEAM NUMBER\>-DS" (where \<TEAM NUMBER\> is replaced by your team number).
* Install the Driver Station app onto the Driver Station phone.
* Put your phones into Airplane Mode (with the WiFi radios still on).
* Pair (i.e., wirelessly connect) the Driver Station to the Robot Controller.

<p align="center">[[/images/Configuring-Your-Android-Devices/twoAndroidPhones.jpg]]</p>

### Renaming Your Smartphones
The official rules of the FIRST Tech Challenge (see \<RS01\>) require that you change the Wi-Fi name of your smartphones to include your team number and “-RC” if the phone is a Robot Controller or “-DS” if it is a Driver Station.  A team can insert an additional dash and a letter (“A”, “B”, “C”, etc.) if the team has more than one set of Android phones.

If, for example, a team has a team number of 9999 and the team has multiple sets of phones, the team might decide to name one phone “9999-C-RC” for the Robot Controller and the other phone “9999-C-DS” for the Driver Station.  The “-C” indicates that these devices belong to the third set of phones for this team.

NOTE: it will take an estimated 5 minutes per phone to complete this task.

| Step| Image |
| ----------- | :---: |
| 1. Browse the list of available apps on the smartphone and locate <br/>the **Settings** icon. Click on **Settings** icon to display the Settings screen. | [[/images/Configuring-Your-Android-Devices/RenameStep1.jpg]] |
| 2. Click on **Wi-Fi** to launch the Wi-Fi screen. | [[/images/Configuring-Your-Android-Devices/RenameStep2.jpg]] |
| 3. Touch the three vertical dots to display a pop-up menu. | [[/images/Configuring-Your-Android-Devices/RenameStep3.jpg]] |
| 4. Select **Advanced** from the pop-up menu. | [[/images/Configuring-Your-Android-Devices/RenameStep4.jpg]] |
| 5. Select **Wi-Fi Direct** from the **Advanced Wi-Fi** screen. | [[/images/Configuring-Your-Android-Devices/RenameStep5.jpg]] |
| 6. Touch the three vertical dots to display a pop-up menu. | [[/images/Configuring-Your-Android-Devices/RenameStep6.jpg]] |
| 7. Select **Configure Device** from the pop-up menu. | [[/images/Configuring-Your-Android-Devices/RenameStep7.jpg]] |
| 8. Use touch pad to enter new name of device. <br/>If the device will be a Robot Controller, specify<br/>your team number and "-RC".  If the device will be<br/>a Driver Station, specify your team number and "-DS".<br/><br/>You can also set the Wi-Fi Direct inactivity<br/>timeout to "Never disconnect" and then hit the<br/>**SAVE** button to save your changes.<br/><br/>Note that in the screenshot shown to the right,<br/>the team number is “9999”.  The “-C” indicates<br/>that this is from the third pair of smartphones for<br/>this team.  The “-RC” indicates that this phone<br/>will be a Robot Controller. | [[/images/Configuring-Your-Android-Devices/RenameStep8.jpg]] |
| 9. After renaming phone, power cycle the device. | 

### Installing the FTC Apps
The FTC apps are available to download for free from the Google Play store.  You will need to have your Android phones connected to a Wi-Fi network that has Internet access before you can access the Google Play store.  You will also need a Google account to be able to download the apps from the Google Play store.

It is also possible to "side-load" the FTC Android Apps onto the Robot Controller and Driver Station phones.  The GitHub repository contains the release versions of the Android apps:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://github.com/ftctechnh/ftc_app/tree/master/doc/apk

However, this section of the wiki does **not** include instructions on how to side-load the apps.  It only explains how to use Google Play to install the FTC apps.

NOTE: it will take an estimated 7.5 minutes per phone to complete this task.

| Step| Image |
| ----------- | :---: |
| 1. From the Android Wi-Fi screen look for the name of <br/>your wireless network (“CE_NET” in this example) and <br/>touch the wireless network name to log into the network.  | [[/images/Configuring-Your-Android-Devices/InstallStep1.jpg]] |
| 2. Specify the password using the touch keypad and hit <br/>**CONNECT** to connect to this wireless network. | [[/images/Configuring-Your-Android-Devices/InstallStep2.jpg]] |
| 3. Find the Google Play Store icon on your phone and <br/>click it to launch the Google Play Store app. | [[/images/Configuring-Your-Android-Devices/InstallStep3.jpg]] |
| 4. If you haven’t signed into your Google account yet, <br/>follow the onscreen instructions to log into your <br/>Google account. <br/><br/>If you don’t have a Google account, follow the <br/>onscreen instructions to create a new account. | [[/images/Configuring-Your-Android-Devices/InstallStep4.jpg]] |
| 5. In the search window of the Google Play app, <br/>type in the words “FTC Robot Controller” to find the <br/>Robot Controller or “FTC Driver Station” to find the <br/>Driver Station. | [[/images/Configuring-Your-Android-Devices/InstallStep5.jpg]] |
| 6. Tap on the app in the Google Play listing to bring <br/>up the installation screen.  Follow the onscreen <br/>instructions to install the appropriate app for your phone.<br/><br/>**Important note:** When you install the FTC apps, **_only install <br/>one FTC app_** (FTC Robot Controller or FTC Driver Station) **_per <br/>phone._**<br/><br/>You should avoid installing both apps onto the same phone. <br/>Doing so can cause Wi-Fi connection problems.  You should <br/>only install the FTC Robot Controller app onto the phone <br/>that will be the Robot Controller and the FTC Driver Station <br/>app onto the phone that will be the Driver Station. | [[/images/Configuring-Your-Android-Devices/InstallStep6.jpg]] |
| 7. After you have successfully installed the app, you should<br/>forget the external wireless network on your phone.<br/><br/>Go to the Android Wi-Fi screen, find the name of the <br/>currently connected network, and tap on the network name <br/>to bring up a pop-up box with info about the network. | [[/images/Configuring-Your-Android-Devices/InstallStep7.jpg]] |
| 8. Click on the **FORGET** button to forget the wireless network. | [[/images/Configuring-Your-Android-Devices/InstallStep8.jpg]] |

### Placing Phones into Airplane Mode with Wi-Fi On
For the FIRST Tech Challenge competitions, it is important that you place your Robot Controller and Driver Station phones into Airplane mode but keep their Wi-Fi radios turned on.  This is important because you do not want any of the cellular telephone functions to be enabled during a match.  The cellular telephone functions could disrupt the function of the robot during a match.

NOTE: it will take an estimated 2.5 minutes per phone to complete this task.  Also note that the screens displayed on your Android devices might differ slightly from the images contained in this wiki.

| Step| Image |
| ----------- | :---: |
| 1. On the main Android screen of each smartphone, use <br/>your finger to slide from the top of the screen down <br/>towards the bottom of the screen to display the quick <br/>configuration screen.<br/><br/>Note that for some smartphones you might have to swipe <br/>down more than once to display the quick configuration <br/>screen, particularly if there are messages or notifications <br/>displayed at the top of your screen.<br/><br/>Look for the Airplane mode icon (which is shaped like an <br/>airplane) and if the icon is not activated, touch the icon <br/>to put the phone into airplane mode. | [[/images/Configuring-Your-Android-Devices/AirplaneStep1.jpg]] |
| 2. Placing the phone into airplane mode will turn off <br/>the Wi-Fi radio.  If the Wi-Fi icon has a diagonal line <br/>through it (see Step 1 above), then the Wi-Fi radio is <br/>disabled.  You will need to touch the **Wi-Fi** icon on the <br/>quick configuration screen to turn the Wi-Fi radio back <br/>on. | [[/images/Configuring-Your-Android-Devices/AirplaneStep2.jpg]] |

### Pairing the Driver Station to the Robot Controller
#### Control Hub Users
The REV Robotics Control Hub should come with the Robot Controller app pre-installed.  Once you have successfully installed the FTC Driver Station on an Android phone, you will want to establish a secure wireless connection between the Control Hub and the Driver Station.  This connection will allow your Driver Station phone to select op modes on your Robot Controller and send gamepad input to these programs.  Likewise, it will allow your op modes running on your Robot Controller to send telemetry data to your Driver Station phone where it can be displayed for your drivers. The process to connect the two devices is known as “pairing.”

NOTE: the Control Hub does not have its own internal battery.  Before you can connect a Driver Station to the Control Hub, you must connect the Control Hub to a 12V battery.

Also note that it will take an estimated 10 minutes to complete this task.

| Step| Image |
| ----------- | :---: |
| 1. Connect an approved 12V battery to the power <br/>switch (REV-31-1387) and make sure the switch <br/>is in the off position.  Connect the switch to an XT30 <br/>port on the Control Hub and turn the switch on. <br/><br/>The LED should initially be blue on the Control Hub. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep1.jpg]] |
| 2. It takes approximately 18 seconds for the <br/>Control Hub to power on. The Control Hub is <br/>ready to pair with the Driver Station when <br/>the LED turns green. <br/><br/>Note: the light blinks blue every ~5 seconds <br/>to indicate that the Control Hub is healthy. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep2.jpg]] |
| 3. On the Driver Station device, browse the <br/>available apps and locate the **FTC Driver Station** <br/>icon. Tap on the icon to launch the Driver Station <br/>app. <br/><br/>Note that the first time you launch the app <br/>your Android device might prompt you for <br/>permissions that the app will need to run properly.  <br/>Whenever prompted, press **Allow** to grant <br/>the requested permission. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep3.jpg]] |
| 4. Touch the three vertical dots on the upper right <br/>hand corner of the main screen of the FTC Driver <br/>Station app.  This will launch a pop-up menu. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep4.jpg]] |
| 5. Select **Settings** from the pop-up menu. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep5.jpg]] |
| 6. From the **Settings** screen, look for and select <br/>**Pairing Method** to launch the **Pairing** <br/>**Method** screen. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep6.jpg]] |
| 7. Touch the words **Control Hub** to indicate <br/> that this Driver Station will be pairing with <br/> a Control Hub. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep7.jpg]] |
| 8. From the **Settings** screen, look for and select <br/>**Pair with Robot Controller** to launch the **Pair** <br/>**with Robot Controller** screen. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep8.jpg]] |
| 9. From **Pair with Robot Controller** screen, <br/>look for and press the **Wifi Settings** button to <br/>launch the device's Android Wifi Settings screen. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep9.jpg]] |
| 10. Find the name of your Control Hub's wireless <br/>network from the list of available WiFi networks.  <br/>Click on the network name to select the network. <br/><br/>If this is the first time you are connecting <br/>to the Control Hub, then the default network <br/>name should begin with the prefix "FTC-" <br/>("FTC-1Ybr" in this example). <br/><br/>The default network name should be listed on a sticker <br/>attached to the bottom side of the Control Hub. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep10.jpg]] |
| 11. When prompted, specify the password <br/>for the Control Hub's WiFi network and press <br/>**Connect** to connect to the Hub.  Note that the <br/>default password for the Control Hub network <br/>is "password". <br/><br/>Also note that when you connect to the <br/>Control Hub's WiFi network successfully, the <br/>Driver Station will not have access to <br/>the Internet. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep11.jpg]] |
| 12. After you successfully connected to <br/>the Hub, use the back arrow to navigate to <br/>the previous screen.  You should see the <br/>name of the WiFi network listed under "Current <br/>Robot Controller:".  Use the back-arrow <br/>key to return to the Settings screen. <br/>Then press the back-arrow key one more time <br/>to return to the main Driver Station screen.  | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep12.jpg]] |
| 13. Verify that the Driver Station screen has <br/>changed and that it now indicates that it is connected <br/>to the Control Hub.<br/><br/>The name of the Control Hub's WiFi network <br/>(“FTC-1Ybr” in this example) should be displayed in the <br/>Network field on the Driver Station. | [[/images/Configuring-Your-Android-Devices/PairingControlHubStep13.jpg]] |

#### Users with Two Android Smartphones
Important Note: If your Driver Station was previously paired to a Control Hub, and you currently would like to connect to an Android smartphone Robot Controller, then before attempting to pair to the Robot Controller, you should forget the Wi-Fi network for the previous Control Hub (using the Android Wifi Settings screen on the Driver Station) and then power cycle the Driver Station phone.  If the previous Control Hub is powered on and if you haven't forgotten this network, then the Driver Station might try and connect to the Control Hub and might be unable to connect to the Robot Controller smartphone.

Once you have successfully installed the FTC apps onto your Android phones, you will want to establish a secure wireless connection between the two devices.  This connection will allow your Driver Station phone to select op modes on your Robot Controller phone and send gamepad input to these programs.  Likewise, it will allow your op modes running on your Robot Controller phone to send telemetry data to your Driver Station phone where it can be displayed for your drivers. The process to connect the two phones is known as “pairing.”

Note that it will take an estimated 10 minutes to complete this task.

| Step| Image |
| ----------- | :---: |
| 1. On the Robot Controller device, browse the <br/>available apps and locate the **FTC Robot Controller** <br/>icon. Tap on the icon to launch the Robot Controller <br/>app. <br/><br/>Note that the first time you launch the app <br/>your Android device might prompt you for <br/>permissions that the app will need to run properly.  <br/>Whenever prompted, press **Allow** to grant <br/>the requested permission. | [[/images/Configuring-Your-Android-Devices/PairingNewStep1.jpg]][[/images/Configuring-Your-Android-Devices/PairingNewStep1b.jpg]]|
| 2. Verify that the Robot Controller app is running.  <br/>The **Robot Status** field should read “running” if it <br/>is working properly. | [[/images/Configuring-Your-Android-Devices/PairingNewStep2.jpg]] |
| 3. On the Driver Station device, browse the <br/>available apps and locate the **FTC Driver Station** <br/>icon. Tap on the icon to launch the Driver Station <br/>app. <br/><br/>Note that the first time you launch the app <br/>your Android device might prompt you for <br/>permissions that the app will need to run properly.  <br/>Whenever prompted, press **Allow** to grant <br/>the requested permission. | [[/images/Configuring-Your-Android-Devices/PairingNewStep3.jpg]]<br/>[[/images/Configuring-Your-Android-Devices/PairingNewStep3b.jpg]] |
| 4. Touch the three vertical dots on the upper right <br/>hand corner of the main screen of the FTC Driver Station <br/>app.  This will launch a pop-up menu. | [[/images/Configuring-Your-Android-Devices/PairingNewStep4.jpg]] |
| 5. Select **Settings** from the pop-up menu. | [[/images/Configuring-Your-Android-Devices/PairingNewStep5.jpg]] |
| 6. From the **Settings** screen, look for and select <br/>**Pairing Method** to launch the **Pairing** <br/>**Method** screen. | [[/images/Configuring-Your-Android-Devices/PairingNewStep6.jpg]] |
| 7. Verify that the **Wifi Direct** mode is selected, which means <br/> that this Driver Station will be pairing with <br/> another Android device. <br/><br/> | [[/images/Configuring-Your-Android-Devices/PairingNewStep7.jpg]] |
| 8. From the **Settings** screen, look for and select <br/>**Pair with Robot Controller** to launch the **Pair**<br/>**with Robot Controller** screen. | [[/images/Configuring-Your-Android-Devices/PairingNewStep8.jpg]] |
| 9. Find the name of your Robot Controller from the <br/>list and select it.<br/><br/>After you have made your selection, use the back-arrow key to return to the Settings <br/>screen.<br/><br/>Then press the back-arrow key one more time to return to the main Driver Station screen. | [[/images/Configuring-Your-Android-Devices/PairingNewStep9.jpg]] |
| 10. When the Driver Station returns to its main <br/>screen, the first time you attempt to connect to the <br/>Robot Controller a prompt should appear on the Robot Controller screen.<br/><br/>Click on the **ACCEPT** button to accept the connection <br/>request from the Driver Station. | [[/images/Configuring-Your-Android-Devices/PairingNewStep10.jpg]] |
| 11. Verify that the Driver Station screen has <br/>changed and that it now indicates that it is connected to the Robot Controller.<br/><br/>The name of the Robot Controller’s remote network <br/>(“9999-C-RC” in this example) should be displayed in the <br/>Network field on the Driver Station. | [[/images/Configuring-Your-Android-Devices/PairingNewStep11.jpg]] |
| 12. Verify that the Robot Controller screen has <br/>changed and that it now indicates that it is connected to the Driver Station.<br/><br/>The Network status should read “active, connected” on the Robot Controller’s main screen. | [[/images/Configuring-Your-Android-Devices/PairingNewStep12.jpg]] |
